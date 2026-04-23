# MuseDAM MCP 工具参数参考

以下为各工具的详细参数说明，便于在需要时查阅。

**重要说明**：所有工具的 `api_key` 和 `region` 参数已移除，这些配置现在通过连接层统一管理（Stdio 模式使用环境变量，HTTP 模式使用 header 和 query parameter）。工具调用时只需传入业务参数。

---

## musedam_search_assets

检索企业空间内的素材。

| 参数 | 类型 | 说明 |
|------|------|------|
| parent_id | int | 父目录 ID（不含根） |
| need_children | bool | 是否包含子孙目录，默认 false |
| extensions | list[str] | 扩展名过滤，如 ["jpg","png"] |
| color | str | 主色过滤 |
| area_threshold, color_threshold | int | 色值相关阈值 |
| min_length, max_length | int | 时长范围（音视频，单位 ms） |
| min_size, max_size | int | 文件大小范围（B） |
| min_height, max_height, min_width, max_width | int | 尺寸范围（px） |
| start_time, end_time | int | 更新时间范围 |
| keyword | str | 单关键词（会转为 keywords 数组） |
| keywords | list[str] | 关键词列表 |
| tags | list[int] | 标签 ID 列表 |
| tag_or_and | bool | **true=标签 AND**，**false=OR**，默认 true（与开放接口一致） |
| create_users | list[int] | 创建人 ID |
| ratings | list[int] | 评分列表（即 scores） |
| has_link, link | bool, str | 是否含链接 / 链接内容 |
| has_desc, desc | bool, str | 是否含备注 / 备注内容 |
| sort_name | str | CREATE_TIME, UPDATE_TIME, NAME, DURATION, SIZE, SCORE |
| sort_type | str | ASC, DESC |
| start_point, end_point | int | 分页，默认 0, 10 |
| custom_field_template_ids, custom_field_id | list[int], int | 自定义字段 |
| current_user_id | int | 仅搜索该用户有权限的资产 |
| spatial_region | list[float] | 对应接口 `region`（区域等） |
| w, h | int | 目标宽高（px），1–6000；影响返回的 publicUrl（需 DAT） |
| mode | str | 与 w/h 同时传：fit / crop |
| q | int | 输出质量 1–100 |
| f | str | 输出格式 jpg / jpeg / png / webp |
| bg | str | 背景色 HEX（可含或不含 #） |

---

## musedam_upload_assets

将素材上传到 DAM（单次最多 50 条）。

- **assets_json**（str，必填）：JSON 数组。每项字段：
  - **url**（必填）、**extension**（必填）
  - 可选：folderIds, name, size, width, height, duration, link, description, **rating**, oldAssetId, **metadatas**（上传：`fieldId` + `value`，与元数据 fields 接口 id 一致）
  - 若使用旧字段 **score**，服务端请求前会映射为 **rating**

---

## musedam_modify_assets

修改素材基本信息。

- **asset_id**（int，必填）
- 可选：name, description, **rating**（评分）, **score**（兼容旧参数，与 rating 同时传时以 rating 为准）, link, tags(list[int])
- **metadatas_json**（str，可选）：JSON 数组，`[{"name":"字段名","value":...}]`（修改接口用 **name+value**，不用 fieldId）

---

## musedam_move_assets_to_folder

将资产移动或添加到目标文件夹（POST `/move-assets-to-folder`）。

- **asset_ids**（list[int]，必填）：资产 ID 列表，**单次最多 200 条**
- **to_folder_id**（int，必填）：目标文件夹 ID，须大于 0
- **from_folder_id**（int，可选）：源文件夹 ID；**operation_type=0（移动）时必填且须大于 0**
- **operation_type**（int，默认 0）：**0**=从源文件夹解除关联后加入目标；**1**=保留源关系并加入目标（添加）

---

## musedam_assets_by_ids

根据素材 ID 列表批量获取详情。

- **asset_ids**（list[int]，必填）
- 团队开启自定义元数据时，条目可能含 metadataList

---

## musedam_folder_subscribe

订阅/取消订阅文件夹内容更新。

- **callback_url**（str，必填）
- **folder_ids**（list[int]，必填）
- **event_type**：默认 FOLDER_CONTENT_UPDATE
- **operation**：ADD=新增订阅，DELETE=取消订阅

---

## musedam_search_share

检索分享链接内的素材。

- **link_token**（str，必填）
- **password**（str）：分享有提取码时必填
- 可选：folder_id, need_children, is_root, keyword, start_point, end_point(默认 40)

---

## musedam_merge_tags

批量合并企业标签。

- **tags_json**（str）：标签树 JSON。每项含 name, id(可选), operation(0 不操作 1 更新 2 创建 3 删除), sort(可选), children(可选)

---

## musedam_set_assets_tags

为素材批量设置标签。

- **tag_ids**（list[int]，必填）
- **asset_ids**（list[int]，必填）
- **remove**（bool）：true=清除历史标签后设置，默认 true

---

## musedam_enterprise_tag_list

分页获取企业标签列表（POST `/enterprise-tag-list`）。

- **page_num**（int，默认 1）、**page_size**（int，默认 500）、**parent_id**（int，默认 0）
- **keyword**（str，可选）
- **tag_type**（int，可选）：0 普通 / 1 智能
- **extra_json**（str，可选）：JSON 对象，合并到请求体（挂载资产数量等以服务端 `EnterpriseTagReq` 字段名为准）

---

## musedam_add_in_app_notify

添加站内消息通知（POST `/add-in-app-notify`）。

- **notification_type**（str，必填）：须与开放服务 `NotificationTypeEnum` 的 **code** 完全一致（如 collaboration、permission_approved、asset_upload 等，完整列表以服务端枚举为准）
- **receiver_id**（int，必填）
- 可选：**sender_id**, **resource_type**（1 文件夹 / 2 资产 / 3 资产组 / 4 团队）, **resource_name**, **content**, **resource_id**, **permission_approved_role_id**

---

## musedam_search_folders

搜索文件夹。

- **parent_id**：不传搜全部，0=根；**parent_id=0 时关键词无效**
- **folder_ids**（list[int]，可选）：非空时按 id 直接拉取，不再按关键词/树检索
- **need_children**, **keywords**, **sort_name**, **sort_type**, **start_point**, **end_point**
- **current_user_id**（int，可选）：仅返回该用户有权限的文件夹

---

## musedam_create_folder

创建文件夹。

- **parent_folder_id**（int，必填，且必须 > 0）
- **name**（str，必填）

---

## musedam_processed_public_links

获取素材原图处理后的公开链接（需开通 DAT）。

- **asset_ids**（list[int]，必填）
- **w, h**：宽高；指定 w 或 h 时才会发送 **mode**
- **mode**：fit=等比缩放，crop=居中裁剪
- **f**：jpg / jpeg / png / webp
- **q**：质量 1–100
- **bg**：背景色 HEX

---

## musedam_org_member_info

获取指定用户的团队成员信息。

- **user_id**（str，必填）

---

## 其他工具

以下工具无额外必填参数，仅需根据业务需求传入可选参数：

- **musedam_query_tag_tree**：获取企业版标签树（开放服务定义为 GET，网关可能仍为 POST，以实际环境为准）
- **musedam_folder_path**：获取指定文件夹的完整路径（需传入 `folder_ids`）
- **musedam_get_sub_folder_ids**：获取指定文件夹的所有子文件夹 ID（需传入 `parent_folder_ids`）
- **musedam_get_asset_analysis_result**：获取素材智能解析结果（需传入 `asset_ids`）
- **musedam_org_info**：获取团队基本信息
