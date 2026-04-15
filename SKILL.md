---
name: musedam-open-api
description: 通过 MCP 工具调用 MuseDAM 开放接口，完成素材检索/上传/修改、标签与文件夹管理、分享搜索、团队信息等。在用户或任务涉及 MuseDAM、DAM、素材库、企业资源管理、图片/视频检索与上传时使用。
---

# MuseDAM 开放接口（MCP 工具使用指南）

本 Skill 指导 Agent 正确调用 **MuseDAM MCP Server** 暴露的工具，对接 MuseDAM 开放 API。

## 前置条件

当前环境已配置 MuseDAM MCP（Stdio 或 Streamable HTTP），且已提供有效的认证信息：

- **Stdio 模式**：通过环境变量 `API_KEY`（或 `MUSEDAM_API_KEY`）和 `REGION`（或 `MUSEDAM_REGION`）配置
- **Streamable HTTP 模式**：通过 HTTP `Authorization` header 和 URL query parameter `region` 配置

## 通用约定

- **认证与配置**：所有工具的 API Key 和 Region 配置已从工具参数中移除，统一通过连接配置管理，调用时无需传入
- **region**：可选值 `cn`（国内，默认）、`cn_test`（国内测试）、`overseas`（海外），由连接配置统一指定
- **返回格式**：工具返回均为 **JSON 字符串**；若 API 报错，返回中会包含 `error` 字段

## 工具速查

| 能力 | 工具名 | 典型用途 |
|------|--------|----------|
| 素材检索 | `musedam_search_assets` | 按目录、关键词、标签、尺寸、时间等检索素材 |
| 素材上传 | `musedam_upload_assets` | 通过 URL 将素材写入 DAM（需 `assets_json`） |
| 素材修改 | `musedam_modify_assets` | 改名称、描述、评分(1-5)、链接、标签 |
| 素材详情 | `musedam_assets_by_ids` | 按素材 ID 列表批量取详情 |
| 分享检索 | `musedam_search_share` | 按分享链接查素材（需 `link_token`，有提取码时传 `password`） |
| 标签树 | `musedam_query_tag_tree` | 获取企业标签树 |
| 标签合并 | `musedam_merge_tags` | 批量创建/更新/删除标签（`tags_json`） |
| 设置标签 | `musedam_set_assets_tags` | 为素材批量设置标签（`tag_ids`+`asset_ids`，`remove` 是否先清空） |
| 文件夹路径 | `musedam_folder_path` | 根据 `folder_ids` 取完整路径 |
| 子文件夹 | `musedam_get_sub_folder_ids` | 递归取某文件夹下所有子文件夹 ID |
| 搜索文件夹 | `musedam_search_folders` | 按父目录、关键词搜索文件夹 |
| 创建文件夹 | `musedam_create_folder` | 在 `parent_folder_id`(>0) 下创建，需 `name` |
| 文件夹订阅 | `musedam_folder_subscribe` | 订阅/取消订阅文件夹内容更新（需 `callback_url`、`folder_ids`，`operation`: ADD/DELETE） |
| 智能解析 | `musedam_get_asset_analysis_result` | 按 `asset_ids` 取 AI 标签、描述等 |
| 团队信息 | `musedam_org_info` | 团队基本信息 |
| 成员信息 | `musedam_org_member_info` | 指定 `user_id` 的成员信息 |
| 处理链接 | `musedam_processed_public_links` | 取素材处理后公开链接（需开通 DAT），可指定宽高、mode(fit/crop)、格式等 |

## 常用调用模式

### 1. 检索素材（关键词 + 分页）

- 使用 `musedam_search_assets`。
- 必填无；常用：`keyword`（关键字）、`parent_id`（目录）、`start_point`/`end_point`（分页，默认 0~10）。
- 排序：`sort_name` 取 `CREATE_TIME`/`UPDATE_TIME`/`NAME`/`DURATION`/`SIZE`/`SCORE`，`sort_type` 取 `ASC`/`DESC`。

### 2. 上传素材（URL 入库）

- 使用 `musedam_upload_assets`，参数 `assets_json` 为 **JSON 数组字符串**。
- 每项至少包含：`url`（必填）、`extension`（必填）；可选：`folderIds`、`name`、`size`/`width`/`height`/`duration`、`link`、`description`、`score`、`oldAssetId`。
- 示例：`[{"folderIds":[23015],"url":"https://example.com/img.jpg","name":"示例图","extension":"jpeg"}]`

### 3. 修改素材

- 使用 `musedam_modify_assets`，必填 `asset_id`；可选 `name`、`description`、`score`(1-5)、`link`、`tags`(标签 ID 数组)。

### 4. 分享链接内检索

- 使用 `musedam_search_share`，必填 `link_token`；若分享有提取码则必填 `password`。可选 `folder_id`、`keyword`、`need_children`、`is_root`、`start_point`/`end_point`。

### 5. 标签与素材

- 先 `musedam_query_tag_tree` 拿到标签树与 ID，再 `musedam_set_assets_tags` 传入 `tag_ids` 与 `asset_ids`；`remove=true` 表示先清空再设置。

### 6. 文件夹结构

- 根目录/某目录下文件夹列表：`musedam_search_folders`（`parent_id` 不传或 0 表示根）。
- 某文件夹完整路径：`musedam_folder_path`（`folder_ids`）。
- 递归子文件夹 ID：`musedam_get_sub_folder_ids`（`parent_folder_ids`）。
- 新建：`musedam_create_folder`（`parent_folder_id` 必须 > 0，`name` 必填）。

## 错误与注意

- 工具返回的 JSON 中若含 `"error": "..."`，表示调用或 API 失败，应解析后向用户说明或重试。
- `assets_json`、`tags_json` 必须是合法 JSON 字符串；复杂结构建议先构建对象再 `JSON.stringify`。
- 分页时 `start_point`/`end_point` 为左闭右开区间；单次不宜请求过多条（如 `end_point - start_point` 建议不超过几十）。

## 更多参数说明

各工具完整参数以 MCP 协议返回的 schema 为准；详细列表与可选值见 [reference.md](reference.md)。
