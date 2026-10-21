---
name: musedam-open-api
description: 通过 MuseDAM MCP 检索和管理素材、文件夹、标签、团队信息、素材事件、审批及商品库。在用户需要操作 MuseDAM 素材库或商品库时使用。
---

# MuseDAM 开放接口

连接使用 Streamable HTTP：`https://mcp-service.musedam.cc`，Authorization 为 `Bearer <API_KEY>`。默认国内，无需 region；海外使用 `?region=overseas`。密钥与区域属于连接配置，不是工具参数。

## 选择工具

使用 `tools/list` 获取已连接服务的当前工具与 schema，再按任务选择。公开工具参考包含 70 个工具，详见 [reference.md](reference.md) 的名称、用途与参数快照。第三方应用 API Key 创建、刷新、撤销不在此范围。

原有工具使用顶层参数；新增带参数工具使用 `params` 对象，其中字段保持 camelCase。无参数工具使用 `{}`。不要为审批或商品库工具传 `service`，该值由各工具固定。

## 常用流程

- 搜索：`musedam_search_assets`，分页使用 `start_point` / `end_point`；`keyword_search_type` 可选 DEFAULT、PRECISE、DEEP、DEEP_AND_PRECISE。
- 上传：`musedam_upload_assets` 使用顶层 `assets`；异步上传 `musedam_upload_assets_async` 使用 `{"params":{"assets":[{"url":"https://example.com/video.mp4","extension":"mp4"}]}}`。单次最多 50 条。素材所有者可用 `userId` 指定。
- 异步任务：取得 taskId 后用 `musedam_upload_assets_task`，参数 `{"params":{"taskId":"返回的32位任务号"}}`。SUCCESS / FAILED 为终态，进行中采用间隔轮询；失败后先检查 failReason，再决定是否重提。相同团队、API Key 用户和 URL 复用任务，进行中及成功任务不重新上传。
- 修改评分使用 `score`；旧 `rating` 兼容但 score 优先。上传评分使用 `rating`，搜索过滤使用 `ratings`。
- 元数据：先调用 `musedam_metadata_fields` 获取字段，再按上传 schema 使用 fieldId。
- 素材订阅：先查 `musedam_material_automation_event_types`，再用 `musedam_material_automation_subscribe` 订阅需要的事件。
- 团队积分：`musedam_org_point_info` 参数 `{}`，结果为数值，0 也是有效结果。
- 审批：先查模板，再发起审批、查询任务；订阅 ADD 需要 callbackUrl。
- 商品库：API Key 需先成为商品库协作者。列表使用 `musedam_product_list_products` 和 `{"params":{"page":1,"pageSize":20}}`。创建商品为草稿；发布使用独立的 set_product_status 工具。商品素材使用该库已有 FilePath ID，不能将 DAM 素材 ID 直接当作商品库文件 ID。

## 结果处理

检查 MCP isError 和返回内容中的 error；失败不应报告成功。保留数值、布尔、列表和空值的语义。参数、权限、模块未开通错误先修正原因，不盲目重试写入。商品同步跟随 nextCursor，全部完成后保存 syncedUntil，按 id 与 updatedAt 去重。
