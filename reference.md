# MuseDAM MCP 工具参数参考

以下为各工具的详细参数说明，便于在需要时查阅。

**重要说明**：所有工具的 `api_key` 和 `region` 参数已移除，这些配置现在通过连接层统一管理（Stdio 模式使用环境变量，HTTP 模式使用 header 和 query parameter）。工具调用时只需传入业务参数。

---

## musedam_search_assets

检索企业空间内的素材。

| 参数 | 类型 | 说明 |
|------|------|------|
| parent_id | int | 父目录 ID |
| need_children | bool | 是否包含子目录，默认 false |
| extensions | list[str] | 扩展名过滤，如 ["jpg","png"] |
| color | str | 主色过滤 |
| area_threshold, color_threshold | int | 色值相关阈值 |
| min_length, max_length | int | 时长范围（如视频） |
| min_size, max_size | int | 文件大小范围 |
| min_height, max_height, min_width, max_width | int | 尺寸范围 |
| start_time, end_time | int | 时间范围（时间戳） |
| keywords | list[str] | 关键词 |
| tags | list[int] | 标签 ID 列表 |
| tag_or_and | bool | 标签逻辑，默认 true（OR） |
| create_users | list[int] | 创建人 ID |
| ratings | list[int] | 评分过滤 |
| has_link, link | bool, str | 是否含链接 / 链接内容 |
| has_desc, desc | bool, str | 是否含描述 / 描述内容 |
| sort_name | str | CREATE_TIME, UPDATE_TIME, NAME, DURATION, SIZE, SCORE |
| sort_type | str | ASC, DESC |
| start_point, end_point | int | 分页，默认 0, 10 |
| custom_field_template_ids, custom_field_id | list[int], int | 自定义字段 |
| current_user_id | int | 当前用户 ID |
| w, h, mode, q, f, bg | 见下方 | 缩略/处理相关（与检索结果展示相关） |

---

## musedam_upload_assets

将素材上传到 DAM。

- **assets_json**（str，必填）：JSON 数组。每项字段：
  - **url**（必填）、**extension**（必填）
  - 可选：folderIds, name, size, width, height, duration, link, description, score, oldAssetId

---

## musedam_modify_assets

修改素材基本信息。

- **asset_id**（int，必填）
- 可选：name, description, score(1-5), link, tags(list[int])

---

## musedam_assets_by_ids

根据素材 ID 列表批量获取详情。

- **asset_ids**（list[int]，必填）

---

## musedam_folder_subscribe

订阅/取消订阅文件夹内容更新。

- **callback_url**（str，必填）
- **folder_ids**（list[int]，必填）
- **event_type**：默认 FOLDER_CONTENT_UPDATE
- **operation**：ADD=新增订阅，DELETE=删除订阅

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
- **remove**（bool）：true=先清除历史标签再设置，默认 true

---

## musedam_search_folders

搜索文件夹。

- **parent_id**：不传搜全部，0=根目录
- 可选：need_children, keywords(list[str]), sort_name(CREATE_TIME, UPDATE_TIME, NAME, SIZE, SCORE), sort_type(DESC/ASC), start_point, end_point

---

## musedam_create_folder

创建文件夹。

- **parent_folder_id**（int，必填，且必须 > 0）
- **name**（str，必填）

---

## musedam_processed_public_links

获取素材原图处理后的公开链接（需开通 DAT）。

- **asset_ids**（list[int]，必填）
- **w, h**：宽高
- **mode**：fit=等比缩放，crop=居中裁剪
- **f**：jpg / png / webp
- **q**：质量等
- **bg**：背景色 HEX，不含 #

---

## musedam_org_member_info

获取指定用户的团队成员信息。

- **user_id**（str，必填）

---

## 其他工具

以下工具无额外必填参数，仅需根据业务需求传入可选参数：

- **musedam_query_tag_tree**：获取企业版标签树
- **musedam_folder_path**：获取指定文件夹的完整路径（需传入 `folder_ids`）
- **musedam_get_sub_folder_ids**：获取指定文件夹的所有子文件夹 ID（需传入 `parent_folder_ids`）
- **musedam_get_asset_analysis_result**：获取素材智能解析结果（需传入 `asset_ids`）
- **musedam_org_info**：获取团队基本信息
