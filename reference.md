# MCP 工具参数参考

同步于 2026-10-22，共 72 个公开工具。调用前读取服务端 schema；以下为当前版本快照。

## musedam_search_assets


    检索企业空间内的素材。
    支持 keyword(单字符串) 或 keywords(字符串数组) 作为关键词；部分 MCP 客户端对数组序列化有问题，建议用 keyword。
    排序 sort_name 可选: CREATE_TIME, UPDATE_TIME, NAME, DURATION, SIZE, SCORE；sort_type: ASC, DESC。
    tag_or_and: true 表示标签 AND，false 表示 OR（默认 true，与开放接口一致）。
    keyword_search_type: DEEP 深度（默认）、DEFAULT 默认、PRECISE 精准、DEEP_AND_PRECISE 深度和精准。
    spatial_region: 对应接口 region 字段（区域多边形等，List<Float>）。
    w/h/mode/q/f/bg: 团队开通 DAT 且资产有公开链时用于 publicUrl 的 OSS 处理参数；未开通时可能不生效。


```json
{
  "properties": {
    "parent_id": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Parent Id"
    },
    "need_children": {
      "default": false,
      "title": "Need Children",
      "type": "boolean"
    },
    "extensions": {
      "anyOf": [
        {
          "items": {
            "type": "string"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Extensions"
    },
    "color": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Color"
    },
    "area_threshold": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Area Threshold"
    },
    "color_threshold": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Color Threshold"
    },
    "min_length": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Min Length"
    },
    "max_length": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Max Length"
    },
    "min_size": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Min Size"
    },
    "max_size": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Max Size"
    },
    "min_height": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Min Height"
    },
    "max_height": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Max Height"
    },
    "min_width": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Min Width"
    },
    "max_width": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Max Width"
    },
    "start_time": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Start Time"
    },
    "end_time": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "End Time"
    },
    "keyword": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Keyword"
    },
    "keywords": {
      "anyOf": [
        {
          "items": {
            "type": "string"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Keywords"
    },
    "tags": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Tags"
    },
    "tag_or_and": {
      "default": true,
      "title": "Tag Or And",
      "type": "boolean"
    },
    "create_users": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Create Users"
    },
    "ratings": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Ratings"
    },
    "has_link": {
      "anyOf": [
        {
          "type": "boolean"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Has Link"
    },
    "link": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Link"
    },
    "has_desc": {
      "anyOf": [
        {
          "type": "boolean"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Has Desc"
    },
    "desc": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Desc"
    },
    "sort_name": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Sort Name"
    },
    "sort_type": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Sort Type"
    },
    "start_point": {
      "default": 0,
      "title": "Start Point",
      "type": "integer"
    },
    "end_point": {
      "default": 10,
      "title": "End Point",
      "type": "integer"
    },
    "custom_field_template_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Custom Field Template Ids"
    },
    "custom_field_id": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Custom Field Id"
    },
    "current_user_id": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Current User Id"
    },
    "spatial_region": {
      "anyOf": [
        {
          "items": {
            "type": "number"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Spatial Region"
    },
    "keyword_search_type": {
      "anyOf": [
        {
          "enum": [
            "DEEP",
            "DEFAULT",
            "PRECISE",
            "DEEP_AND_PRECISE"
          ],
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Keyword Search Type"
    },
    "w": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "W"
    },
    "h": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "H"
    },
    "mode": {
      "default": "fit",
      "title": "Mode",
      "type": "string"
    },
    "q": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Q"
    },
    "f": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "F"
    },
    "bg": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Bg"
    }
  },
  "title": "musedam_search_assetsArguments",
  "type": "object"
}
```

## musedam_upload_assets


    将素材上传到 DAM。assets 为数组（单次最多 50 条），每项含 url(必填)、extension(必填)；
    可选 folderIds、name、size、width、height、duration、link、description、rating、oldAssetId、metadatas（上传用 fieldId+value）、skipDuplicateByEtag、userId、licenseAgreementIds、startTime、endTime、isPermanent。
    若仍使用旧字段 score，会自动映射为接口的 rating。返回每条可含 uploadResult（NEW / DUPLICATE_BY_ETAG）；其余与开放接口一致。
    示例: [{"folderIds":[23015],"url":"https://...","name":"测试图片","extension":"jpeg"}]


```json
{
  "properties": {
    "assets": {
      "items": {
        "additionalProperties": false,
        "properties": {
          "url": {
            "description": "可直接下载的素材 URL",
            "pattern": "^https?://[^\\s/]+(?:[/?#].*)?$",
            "type": "string"
          },
          "extension": {
            "description": "文件扩展名，如 jpg、mp4",
            "minLength": 1,
            "type": "string"
          },
          "folderIds": {
            "description": "目标文件夹；每个文件夹均需上传权限",
            "items": {
              "description": "",
              "type": "integer"
            },
            "type": "array"
          },
          "name": {
            "description": "",
            "type": "string"
          },
          "size": {
            "description": "",
            "type": "integer"
          },
          "width": {
            "description": "",
            "type": "integer"
          },
          "height": {
            "description": "",
            "type": "integer"
          },
          "duration": {
            "description": "视频时长，毫秒",
            "type": "integer"
          },
          "link": {
            "description": "",
            "type": "string"
          },
          "description": {
            "description": "",
            "type": "string"
          },
          "rating": {
            "description": "上传评分（上传接口使用 rating）",
            "type": "integer"
          },
          "userId": {
            "description": "素材所有者；默认当前 API Key 用户；须属于当前团队",
            "type": "integer"
          },
          "oldAssetId": {
            "description": "上传新版本时指定原素材 ID",
            "minimum": 1,
            "type": "integer"
          },
          "metadatas": {
            "items": {
              "additionalProperties": false,
              "properties": {
                "fieldId": {
                  "description": "",
                  "type": "string"
                },
                "value": {}
              },
              "required": [
                "fieldId"
              ],
              "type": "object"
            },
            "type": "array"
          },
          "skipDuplicateByEtag": {
            "description": "",
            "type": "boolean"
          },
          "licenseAgreementIds": {
            "description": "版权协议 ID 列表",
            "items": {
              "type": "integer"
            },
            "minItems": 1,
            "type": "array"
          },
          "startTime": {
            "description": "关闭版权管理时生效的素材有效期开始时间",
            "type": "string"
          },
          "endTime": {
            "description": "关闭版权管理时生效的素材有效期结束时间",
            "type": "string"
          },
          "isPermanent": {
            "description": "",
            "type": "boolean"
          }
        },
        "required": [
          "url",
          "extension"
        ],
        "type": "object"
      },
      "maxItems": 50,
      "minItems": 1,
      "title": "Assets",
      "type": "array"
    }
  },
  "required": [
    "assets"
  ],
  "title": "musedam_upload_assetsArguments",
  "type": "object"
}
```

## musedam_modify_assets

修改素材基本信息。score 为评分；rating 仅兼容旧 MCP 调用，与 score 同时传时以 score 为准。
    metadatas: 元数据数组，元素为 {"name":"字段名","value":...}（修改接口用 name+value，非上传场景的 fieldId）。


```json
{
  "properties": {
    "asset_id": {
      "default": 0,
      "title": "Asset Id",
      "type": "integer"
    },
    "name": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Name"
    },
    "description": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Description"
    },
    "rating": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Rating"
    },
    "score": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Score"
    },
    "link": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Link"
    },
    "tags": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Tags"
    },
    "metadatas": {
      "anyOf": [
        {
          "items": {
            "additionalProperties": true,
            "type": "object"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Metadatas"
    }
  },
  "title": "musedam_modify_assetsArguments",
  "type": "object"
}
```

## musedam_move_assets_to_folder


    将一批资产移动或添加到目标文件夹（POST /move-assets-to-folder）。asset_ids 单次最多 200 条。
    operation_type: 0=移动（从 from_folder_id 解除后加入 to_folder_id，此时 from_folder_id 必填且大于 0）；
    1=添加（保留源文件夹关系并加入目标，from_folder_id 可不传）。


```json
{
  "properties": {
    "asset_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Asset Ids"
    },
    "to_folder_id": {
      "default": 0,
      "title": "To Folder Id",
      "type": "integer"
    },
    "from_folder_id": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "From Folder Id"
    },
    "operation_type": {
      "default": 0,
      "title": "Operation Type",
      "type": "integer"
    }
  },
  "title": "musedam_move_assets_to_folderArguments",
  "type": "object"
}
```

## musedam_assets_by_ids

根据素材 ID 列表批量获取素材详细信息。

```json
{
  "properties": {
    "asset_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Asset Ids"
    }
  },
  "title": "musedam_assets_by_idsArguments",
  "type": "object"
}
```

## musedam_folder_subscribe

订阅或取消订阅文件夹内容更新。operation: ADD=新增订阅, DELETE=删除订阅。

```json
{
  "properties": {
    "callback_url": {
      "title": "Callback Url",
      "type": "string"
    },
    "folder_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Folder Ids"
    },
    "event_type": {
      "default": "FOLDER_CONTENT_UPDATE",
      "title": "Event Type",
      "type": "string"
    },
    "operation": {
      "default": "ADD",
      "title": "Operation",
      "type": "string"
    }
  },
  "required": [
    "callback_url"
  ],
  "title": "musedam_folder_subscribeArguments",
  "type": "object"
}
```

## musedam_search_share

检索分享链接内的素材。若分享设置了提取码则必填 password。

```json
{
  "properties": {
    "link_token": {
      "default": "",
      "title": "Link Token",
      "type": "string"
    },
    "password": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Password"
    },
    "folder_id": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Folder Id"
    },
    "need_children": {
      "default": false,
      "title": "Need Children",
      "type": "boolean"
    },
    "is_root": {
      "default": false,
      "title": "Is Root",
      "type": "boolean"
    },
    "keyword": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Keyword"
    },
    "start_point": {
      "default": 0,
      "title": "Start Point",
      "type": "integer"
    },
    "end_point": {
      "default": 40,
      "title": "End Point",
      "type": "integer"
    }
  },
  "title": "musedam_search_shareArguments",
  "type": "object"
}
```

## musedam_merge_tags


    批量合并企业标签。tags 为标签树数组，每项含 name, id(可选), operation(0不操作 1更新 2创建 3删除), sort(可选), children(可选)。


```json
{
  "properties": {
    "tags": {
      "anyOf": [
        {
          "items": {
            "additionalProperties": true,
            "type": "object"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Tags"
    }
  },
  "title": "musedam_merge_tagsArguments",
  "type": "object"
}
```

## musedam_set_assets_tags

为指定素材批量设置标签。remove=true 表示清除历史标签后设置新标签。

```json
{
  "properties": {
    "tag_ids": {
      "items": {
        "type": "integer"
      },
      "title": "Tag Ids",
      "type": "array"
    },
    "asset_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Asset Ids"
    },
    "remove": {
      "default": true,
      "title": "Remove",
      "type": "boolean"
    }
  },
  "required": [
    "tag_ids"
  ],
  "title": "musedam_set_assets_tagsArguments",
  "type": "object"
}
```

## musedam_query_tag_tree

获取企业版标签树。

```json
{
  "properties": {},
  "title": "musedam_query_tag_treeArguments",
  "type": "object"
}
```

## musedam_folder_path

获取指定文件夹的完整路径信息，返回 folderId -> 路径字符串。

```json
{
  "properties": {
    "folder_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Folder Ids"
    }
  },
  "title": "musedam_folder_pathArguments",
  "type": "object"
}
```

## musedam_get_sub_folder_ids

获取指定文件夹的所有子文件夹 ID（递归）。

```json
{
  "properties": {
    "parent_folder_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Parent Folder Ids"
    }
  },
  "title": "musedam_get_sub_folder_idsArguments",
  "type": "object"
}
```

## musedam_get_asset_analysis_result

获取素材智能解析结果（AI 标签、描述等）。

```json
{
  "properties": {
    "asset_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Asset Ids"
    }
  },
  "title": "musedam_get_asset_analysis_resultArguments",
  "type": "object"
}
```

## musedam_org_member_info

获取指定用户的团队成员信息。

```json
{
  "properties": {
    "user_id": {
      "default": "",
      "title": "User Id",
      "type": "string"
    }
  },
  "title": "musedam_org_member_infoArguments",
  "type": "object"
}
```

## musedam_search_folders

搜索文件夹。parent_id 不传搜全部，0 表示根；folder_ids 非空时按 id 直接拉取（不再按关键词树检索）。
    parent_id=0 时关键词无效（与现网一致）。sort_name: CREATE_TIME, UPDATE_TIME, NAME, SIZE, SCORE。

```json
{
  "properties": {
    "parent_id": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Parent Id"
    },
    "need_children": {
      "default": false,
      "title": "Need Children",
      "type": "boolean"
    },
    "folder_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Folder Ids"
    },
    "keywords": {
      "anyOf": [
        {
          "items": {
            "type": "string"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Keywords"
    },
    "sort_name": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Sort Name"
    },
    "sort_type": {
      "default": "DESC",
      "title": "Sort Type",
      "type": "string"
    },
    "start_point": {
      "default": 0,
      "title": "Start Point",
      "type": "integer"
    },
    "end_point": {
      "default": 10,
      "title": "End Point",
      "type": "integer"
    },
    "current_user_id": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Current User Id"
    }
  },
  "title": "musedam_search_foldersArguments",
  "type": "object"
}
```

## musedam_create_folder

创建文件夹，parent_folder_id 必须大于 0。

```json
{
  "properties": {
    "parent_folder_id": {
      "title": "Parent Folder Id",
      "type": "integer"
    },
    "name": {
      "default": "",
      "title": "Name",
      "type": "string"
    }
  },
  "required": [
    "parent_folder_id"
  ],
  "title": "musedam_create_folderArguments",
  "type": "object"
}
```

## musedam_processed_public_links


    获取素材原图处理后的公开链接（需开通 DAT）。指定 w/h 时才会附带 mode（fit=等比缩放, crop=居中裁剪）。
    f: jpg/jpeg/png/webp。bg 为 HEX（可含或不含 #，与服务端一致）。


```json
{
  "properties": {
    "asset_ids": {
      "anyOf": [
        {
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Asset Ids"
    },
    "w": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "W"
    },
    "h": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "H"
    },
    "mode": {
      "default": "fit",
      "title": "Mode",
      "type": "string"
    },
    "q": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Q"
    },
    "f": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "F"
    },
    "bg": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Bg"
    }
  },
  "title": "musedam_processed_public_linksArguments",
  "type": "object"
}
```

## musedam_enterprise_tag_list


    分页获取企业标签列表（POST /enterprise-tag-list）。tag_type: 0 普通 / 1 智能（与开放接口 EnterpriseTagReq 一致）。
    extra: 可选，额外的请求参数字典，合并到请求体（挂载数量等字段以服务端 EnterpriseTagReq 为准）。


```json
{
  "properties": {
    "page_num": {
      "default": 1,
      "title": "Page Num",
      "type": "integer"
    },
    "page_size": {
      "default": 500,
      "title": "Page Size",
      "type": "integer"
    },
    "parent_id": {
      "default": 0,
      "title": "Parent Id",
      "type": "integer"
    },
    "keyword": {
      "anyOf": [
        {
          "type": "string"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Keyword"
    },
    "tag_type": {
      "anyOf": [
        {
          "type": "integer"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Tag Type"
    },
    "extra": {
      "anyOf": [
        {
          "additionalProperties": true,
          "type": "object"
        },
        {
          "type": "null"
        }
      ],
      "default": null,
      "title": "Extra"
    }
  },
  "title": "musedam_enterprise_tag_listArguments",
  "type": "object"
}
```

## musedam_search_by_image

以图搜图，仅付费团队可用。至少提供一个图片来源；优先级 imageBase64 > searchMaterialId > imagePublicUrl。base64 支持纯内容或 data:image/xxx;base64, 前缀。筛选、分页、响应与素材检索一致，按相似度排序；endPoint > 1000 返回空结果。region 为图中框选区域。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "anyOf": [
        {
          "properties": {
            "imageBase64": {
              "minLength": 1,
              "type": "string"
            }
          },
          "required": [
            "imageBase64"
          ]
        },
        {
          "properties": {
            "searchMaterialId": {
              "minimum": 1,
              "type": "integer"
            }
          },
          "required": [
            "searchMaterialId"
          ]
        },
        {
          "properties": {
            "imagePublicUrl": {
              "minLength": 1,
              "type": "string"
            }
          },
          "required": [
            "imagePublicUrl"
          ]
        }
      ],
      "properties": {
        "parentId": {
          "description": "指定搜索目录（不包括根目录），包含所有子孙",
          "type": "integer"
        },
        "needChildren": {
          "description": "是否需要子级目录下的素材，默认 false",
          "type": "boolean"
        },
        "extensions": {
          "description": "文件类型扩展名",
          "items": {
            "type": "string"
          },
          "type": "array"
        },
        "color": {
          "description": "颜色",
          "type": "string"
        },
        "areaThreshold": {
          "description": "颜色占比，默认 20",
          "type": "integer"
        },
        "colorThreshold": {
          "description": "颜色精准度，默认 20",
          "type": "integer"
        },
        "minLength": {
          "description": "最小时长（视频、音频），单位 ms",
          "type": "integer"
        },
        "maxLength": {
          "description": "最大时长（视频、音频），单位 ms",
          "type": "integer"
        },
        "minSize": {
          "description": "最小文件大小，单位 B",
          "type": "integer"
        },
        "maxSize": {
          "description": "最大文件大小，单位 B",
          "type": "integer"
        },
        "minHeight": {
          "description": "最小图片高度，单位 px",
          "type": "integer"
        },
        "maxHeight": {
          "description": "最大图片高度，单位 px",
          "type": "integer"
        },
        "minWidth": {
          "description": "最小图片宽度，单位 px",
          "type": "integer"
        },
        "maxWidth": {
          "description": "最大图片宽度，单位 px",
          "type": "integer"
        },
        "startTime": {
          "description": "开始时间（更新时间范围）",
          "type": "integer"
        },
        "endTime": {
          "description": "结束时间（更新时间范围）",
          "type": "integer"
        },
        "keywords": {
          "description": "搜索关键字",
          "items": {
            "type": "string"
          },
          "type": "array"
        },
        "tags": {
          "description": "标签 ID 列表",
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        "tagOrAnd": {
          "description": "标签筛选 or/and，true=and，默认 true",
          "type": "boolean"
        },
        "createUsers": {
          "description": "创建人 ID 列表",
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        "ratings": {
          "description": "评分列表（即 scores）",
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        "hasLink": {
          "description": "是否有链接",
          "type": "boolean"
        },
        "link": {
          "description": "输入链接",
          "type": "string"
        },
        "hasDesc": {
          "description": "是否有备注",
          "type": "boolean"
        },
        "desc": {
          "description": "输入备注",
          "type": "string"
        },
        "startPoint": {
          "description": "分页开始索引，默认 0",
          "type": "integer"
        },
        "endPoint": {
          "description": "分页结束索引，默认 10",
          "type": "integer"
        },
        "region": {
          "description": "查询图上的框选区域，不是连接的国内/海外 region。",
          "items": {
            "type": "number"
          },
          "type": "array"
        },
        "customFieldTemplateIds": {
          "description": "自定义字段模板 ID 列表",
          "items": {
            "type": "integer"
          },
          "type": "array"
        },
        "customFieldId": {
          "description": "自定义字段 ID",
          "type": "integer"
        },
        "currentUserId": {
          "description": "仅搜索该用户有权限的素材",
          "type": "integer"
        },
        "w": {
          "description": "目标宽度（px），范围 1–6000；用于生成返回中的 publicUrl； 超过原图参数无效",
          "type": "integer"
        },
        "h": {
          "description": "目标高度（px），范围 1–6000；用于生成返回中的 publicUrl； 超过原图参数无效",
          "type": "integer"
        },
        "mode": {
          "description": "缩放模式：fit-等比缩放，crop-居中裁剪；用于生成 publicUrl，默认 fit",
          "type": "string"
        },
        "q": {
          "description": "输出质量，范围 1–100；用于生成 publicUrl",
          "type": "integer"
        },
        "f": {
          "description": "输出格式：jpg / png / webp；用于生成 publicUrl",
          "type": "string"
        },
        "bg": {
          "description": "背景填充色（HEX，不含 #）；用于生成 publicUrl",
          "type": "string"
        },
        "keywordSearchType": {
          "description": "搜索类型：*DEEP(深度搜索 默认)，DEFAULT（站内默认搜索)，PRECISE（精准搜索） DEEP_AND_PRECISE(深度和精准)*",
          "type": "string"
        },
        "sort": {
          "additionalProperties": false,
          "properties": {
            "sortName": {
              "type": "string"
            },
            "sortType": {
              "type": "string"
            }
          },
          "required": [
            "sortName"
          ],
          "type": "object"
        },
        "searchMaterialId": {
          "type": "integer"
        },
        "imagePublicUrl": {
          "type": "string"
        },
        "imageBase64": {
          "type": "string"
        }
      },
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_search_by_imageArguments",
  "type": "object"
}
```

## musedam_role_members_query

查询角色成员，默认 page=1/pageSize=10；响应 records/total/current/size，成员含 roleId，手机号脱敏。仅管理员类型 API Key 可调用：企业版对应角色 code 为 content；非企业版 API Key 视为管理员。不满足条件返回 50083。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "roleId": {
          "description": "",
          "type": "integer"
        },
        "keyWord": {
          "description": "",
          "type": "string"
        },
        "page": {
          "description": "页码，默认 1",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "description": "每页数量",
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "roleId"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_role_members_queryArguments",
  "type": "object"
}
```

## musedam_upload_assets_async

按 URL 异步上传素材，超过 20 MB 推荐使用。立即返回 tasks[].taskId；随后调用 musedam_upload_assets_task。相同团队/API Key 用户/原始 URL 复用任务（userId 不参与）；成功或进行中不会重新入库，失败重提使用新参数重试。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "assets": {
          "items": {
            "additionalProperties": false,
            "properties": {
              "url": {
                "description": "可直接下载的素材 URL",
                "pattern": "^https?://[^\\s/]+(?:[/?#].*)?$",
                "type": "string"
              },
              "extension": {
                "description": "文件扩展名，如 jpg、mp4",
                "minLength": 1,
                "type": "string"
              },
              "folderIds": {
                "description": "目标文件夹；每个文件夹均需上传权限",
                "items": {
                  "description": "",
                  "type": "integer"
                },
                "type": "array"
              },
              "name": {
                "description": "",
                "type": "string"
              },
              "size": {
                "description": "",
                "type": "integer"
              },
              "width": {
                "description": "",
                "type": "integer"
              },
              "height": {
                "description": "",
                "type": "integer"
              },
              "duration": {
                "description": "视频时长，毫秒",
                "type": "integer"
              },
              "link": {
                "description": "",
                "type": "string"
              },
              "description": {
                "description": "",
                "type": "string"
              },
              "rating": {
                "description": "上传评分（上传接口使用 rating）",
                "type": "integer"
              },
              "userId": {
                "description": "素材所有者；默认当前 API Key 用户；须属于当前团队",
                "type": "integer"
              },
              "oldAssetId": {
                "description": "上传新版本时指定原素材 ID",
                "minimum": 1,
                "type": "integer"
              },
              "metadatas": {
                "items": {
                  "additionalProperties": false,
                  "properties": {
                    "fieldId": {
                      "description": "",
                      "type": "string"
                    },
                    "value": {}
                  },
                  "required": [
                    "fieldId"
                  ],
                  "type": "object"
                },
                "type": "array"
              },
              "skipDuplicateByEtag": {
                "description": "",
                "type": "boolean"
              },
              "licenseAgreementIds": {
                "description": "版权协议 ID 列表",
                "items": {
                  "type": "integer"
                },
                "minItems": 1,
                "type": "array"
              },
              "startTime": {
                "description": "关闭版权管理时生效的素材有效期开始时间",
                "type": "string"
              },
              "endTime": {
                "description": "关闭版权管理时生效的素材有效期结束时间",
                "type": "string"
              },
              "isPermanent": {
                "description": "",
                "type": "boolean"
              },
              "callbackUrl": {
                "description": "可选；成功或失败后 POST 一次，正文是查询结果对象，无 result 包装；失败不重试",
                "pattern": "^https?://[^\\s/]+(?:[/?#].*)?$",
                "type": "string"
              }
            },
            "required": [
              "url",
              "extension"
            ],
            "type": "object"
          },
          "maxItems": 50,
          "minItems": 1,
          "type": "array"
        }
      },
      "required": [
        "assets"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_upload_assets_asyncArguments",
  "type": "object"
}
```

## musedam_upload_assets_task

查询当前团队和 API Key 用户的上传任务。返回 stage、progress、transferredBytes、totalBytes、failReason 及成功后的 materialId/storePath/name/accessUrl。WAITING/DOWNLOADING/SAVING/INGESTING 为进行中，SUCCESS/FAILED 为终态。总大小未知时下载进度为 0；成功链接每次查询重新签发，有效 1 天。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "taskId": {
          "description": "异步上传返回的 32 位无横线任务号",
          "maxLength": 32,
          "minLength": 32,
          "type": "string"
        }
      },
      "required": [
        "taskId"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_upload_assets_taskArguments",
  "type": "object"
}
```

## musedam_metadata_records_by_ids

按素材 ID 查询自定义元数据；仅返回已有记录的素材，字段使用 name。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "materialIds": {
          "description": "素材 ID 列表",
          "items": {
            "type": "integer"
          },
          "maxItems": 50,
          "minItems": 1,
          "type": "array"
        }
      },
      "required": [
        "materialIds"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_metadata_records_by_idsArguments",
  "type": "object"
}
```

## musedam_metadata_fields

查询团队元数据字段定义；上传时使用返回的 fieldId。未开通时返回空列表。

```json
{
  "properties": {},
  "title": "musedam_metadata_fieldsArguments",
  "type": "object"
}
```

## musedam_check_transferred_materials

批量判断素材是否由成员资源转移产生；返回 ID 到 Boolean 的映射。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "assetIds": {
          "description": "素材 ID 列表",
          "items": {
            "type": "integer"
          },
          "minItems": 1,
          "type": "array"
        }
      },
      "required": [
        "assetIds"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_check_transferred_materialsArguments",
  "type": "object"
}
```

## musedam_material_access_users_query

分页查询素材下载/分享的取用者及次数、最近操作时间；operationTypes 1 下载，2 分享。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "assetId": {
          "description": "",
          "type": "integer"
        },
        "operationTypes": {
          "items": {
            "enum": [
              1,
              2
            ],
            "type": "integer"
          },
          "type": "array"
        },
        "page": {
          "description": "页码，默认 1",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "description": "每页数量",
          "maximum": 100,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "assetId"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_material_access_users_queryArguments",
  "type": "object"
}
```

## musedam_folder_auto_tags

批量读取文件夹自身配置的自动标签，不包含祖先文件夹。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "folderIds": {
          "description": "文件夹 ID",
          "items": {
            "type": "integer"
          },
          "maxItems": 50,
          "minItems": 1,
          "type": "array"
        }
      },
      "required": [
        "folderIds"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_folder_auto_tagsArguments",
  "type": "object"
}
```

## musedam_create_folder_tree

批量创建文件夹树。nodes 为递归节点，每个节点含 name、可选 children。

```json
{
  "$defs": {
    "FolderNode": {
      "additionalProperties": false,
      "properties": {
        "name": {
          "minLength": 1,
          "title": "Name",
          "type": "string"
        },
        "children": {
          "anyOf": [
            {
              "items": {
                "$ref": "#/$defs/FolderNode"
              },
              "type": "array"
            },
            {
              "type": "null"
            }
          ],
          "default": null,
          "title": "Children"
        }
      },
      "required": [
        "name"
      ],
      "title": "FolderNode",
      "type": "object"
    },
    "FolderTree": {
      "additionalProperties": false,
      "properties": {
        "parentFolderId": {
          "minimum": 0,
          "title": "Parentfolderid",
          "type": "integer"
        },
        "nodes": {
          "items": {
            "$ref": "#/$defs/FolderNode"
          },
          "minItems": 1,
          "title": "Nodes",
          "type": "array"
        }
      },
      "required": [
        "parentFolderId",
        "nodes"
      ],
      "title": "FolderTree",
      "type": "object"
    }
  },
  "properties": {
    "params": {
      "$ref": "#/$defs/FolderTree"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_create_folder_treeArguments",
  "type": "object"
}
```

## musedam_asset_derivative_versions

批量获取素材衍生版本，需开通素材衍生能力。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "assetIds": {
          "description": "素材 ID 列表",
          "items": {
            "type": "integer"
          },
          "minItems": 1,
          "type": "array"
        }
      },
      "required": [
        "assetIds"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_asset_derivative_versionsArguments",
  "type": "object"
}
```

## musedam_org_info

读取当前 API Key 所属团队的基本信息。

```json
{
  "properties": {},
  "title": "musedam_org_infoArguments",
  "type": "object"
}
```

## musedam_org_point_info

读取当前团队剩余积分余额；结果为数值，可包含小数。

```json
{
  "properties": {},
  "title": "musedam_org_point_infoArguments",
  "type": "object"
}
```

## musedam_org_members_query

分页查询团队成员；默认 page=1/pageSize=10，支持部门和成员状态筛选。仅管理员类型 API Key 可调用：企业版对应角色 code 为 content；非企业版 API Key 视为管理员。不满足条件返回 50083。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "keyword": {
          "description": "",
          "type": "string"
        },
        "page": {
          "description": "页码，默认 1",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "description": "每页数量",
          "minimum": 1,
          "type": "integer"
        },
        "accountStatusEnumList": {
          "description": "PendingActivation/normal/resigned",
          "items": {
            "type": "string"
          },
          "type": "array"
        },
        "departmentId": {
          "description": "",
          "type": "integer"
        },
        "needChildMember": {
          "description": "",
          "type": "boolean"
        },
        "needUserUseMemorySize": {
          "description": "",
          "type": "boolean"
        },
        "addType": {
          "description": "",
          "type": "integer"
        },
        "isSale": {
          "description": "",
          "type": "integer"
        }
      },
      "required": [],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_org_members_queryArguments",
  "type": "object"
}
```

## musedam_org_whitelist_query

分页查询团队白名单成员，支持关键字和群组筛选。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "keyword": {
          "description": "",
          "type": "string"
        },
        "page": {
          "description": "页码，默认 1",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "description": "每页数量",
          "minimum": 1,
          "type": "integer"
        },
        "groupId": {
          "description": "",
          "type": "integer"
        },
        "addType": {
          "description": "",
          "type": "integer"
        }
      },
      "required": [],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_org_whitelist_queryArguments",
  "type": "object"
}
```

## musedam_org_departments_query

查询团队部门列表。仅管理员类型 API Key 可调用：企业版对应角色 code 为 content；非企业版 API Key 视为管理员。不满足条件返回 50083。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "parentId": {
          "description": "父部门 ID，默认 0",
          "type": "integer"
        }
      },
      "required": [],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_org_departments_queryArguments",
  "type": "object"
}
```

## musedam_org_groups_query

查询团队群组列表。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "parentId": {
          "description": "父群组 ID，默认 0",
          "type": "integer"
        }
      },
      "required": [],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_org_groups_queryArguments",
  "type": "object"
}
```

## musedam_department_members_query

按部门查询成员；needChildMember 指定是否含子部门，默认 false。仅管理员类型 API Key 可调用：企业版对应角色 code 为 content；非企业版 API Key 视为管理员。不满足条件返回 50083。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "departmentId": {
          "description": "",
          "type": "integer"
        },
        "needChildMember": {
          "description": "",
          "type": "boolean"
        }
      },
      "required": [
        "departmentId"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_department_members_queryArguments",
  "type": "object"
}
```

## musedam_group_members_query

分页查询群组成员；搜索参数为 keyWord，默认 page=1/pageSize=10。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "groupId": {
          "description": "",
          "type": "integer"
        },
        "keyWord": {
          "description": "",
          "type": "string"
        },
        "needChildMember": {
          "description": "",
          "type": "boolean"
        },
        "page": {
          "description": "页码，默认 1",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "description": "每页数量",
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "groupId"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_group_members_queryArguments",
  "type": "object"
}
```

## musedam_material_automation_event_types

查询当前公开的素材事件类型及当前 API Key 订阅状态。

```json
{
  "properties": {},
  "title": "musedam_material_automation_event_typesArguments",
  "type": "object"
}
```

## musedam_material_automation_subscribe

订阅或取消团队素材事件，服务端向 callbackUrl 发送 Webhook；与文件夹订阅独立。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "callbackUrl": {
          "description": "可访问的 HTTP/HTTPS 地址",
          "pattern": "^https?://[^\\s/]+(?:[/?#].*)?$",
          "type": "string"
        },
        "eventTypes": {
          "items": {
            "enum": [
              "MATERIAL_INBOUND_COMPLETED",
              "MATERIAL_ADDED_TO_FOLDER",
              "MATERIAL_METADATA_UPDATED",
              "MATERIAL_VERSION_CHANGED",
              "MATERIAL_DELETED"
            ],
            "type": "string"
          },
          "minItems": 1,
          "type": "array"
        },
        "operation": {
          "description": "ADD 订阅；DELETE 取消订阅，默认 ADD",
          "enum": [
            "ADD",
            "DELETE"
          ],
          "type": "string"
        }
      },
      "required": [
        "callbackUrl",
        "eventTypes"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_material_automation_subscribeArguments",
  "type": "object"
}
```

## musedam_approval_list_templates

查询审批模板，需开通审批中心扩展模块。

```json
{
  "properties": {},
  "title": "musedam_approval_list_templatesArguments",
  "type": "object"
}
```

## musedam_approval_create_approval

发起审批任务，需开通审批中心扩展模块。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "templateId": {
          "description": "",
          "type": "string"
        },
        "createdBy": {
          "description": "",
          "type": "string"
        },
        "assets": {
          "items": {
            "additionalProperties": false,
            "properties": {
              "name": {
                "description": "",
                "type": "string"
              },
              "url": {
                "description": "可访问的 HTTP/HTTPS 地址",
                "pattern": "^https?://[^\\s/]+(?:[/?#].*)?$",
                "type": "string"
              },
              "size": {
                "description": "",
                "type": "number"
              },
              "mimeType": {
                "description": "",
                "type": "string"
              },
              "extension": {
                "description": "",
                "type": "string"
              }
            },
            "required": [
              "name",
              "url"
            ],
            "type": "object"
          },
          "minItems": 1,
          "type": "array"
        },
        "sourceContext": {
          "type": "object"
        },
        "reason": {
          "description": "",
          "type": "string"
        }
      },
      "required": [
        "templateId",
        "createdBy",
        "assets"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_approval_create_approvalArguments",
  "type": "object"
}
```

## musedam_approval_task_status_query

查询审批任务状态。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "taskId": {
          "description": "审批任务 ID（正整数）",
          "pattern": "^[1-9][0-9]*$",
          "type": "string"
        }
      },
      "required": [
        "taskId"
      ],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_approval_task_status_queryArguments",
  "type": "object"
}
```

## musedam_approval_subscription_query

查询审批事件订阅状态。

```json
{
  "properties": {},
  "title": "musedam_approval_subscription_queryArguments",
  "type": "object"
}
```

## musedam_approval_subscription_change

变更审批事件订阅，ADD（默认）必须有 callbackUrl；DELETE 取消订阅。

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "operation": {
          "description": "ADD 订阅；DELETE 取消订阅，默认 ADD",
          "enum": [
            "ADD",
            "DELETE"
          ],
          "type": "string"
        },
        "callbackUrl": {
          "description": "可访问的 HTTP/HTTPS 地址",
          "pattern": "^https?://[^\\s/]+(?:[/?#].*)?$",
          "type": "string"
        }
      },
      "required": [],
      "title": "Params",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_approval_subscription_changeArguments",
  "type": "object"
}
```

## musedam_product_list_brands

List brands. Returns public metadata ordered by sortOrder then id. Raw logo URLs are excluded. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "page": {
          "default": 1,
          "description": "Ordinary page number. Not allowed when sync=true. Excessive offset causing integer overflow is rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "default": 20,
          "description": "Page size; values above 100 are capped at 100. Nonpositive/noninteger values are rejected.",
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [],
      "title": "List brands",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_list_brandsArguments",
  "type": "object"
}
```

## musedam_product_create_brand

Create brand. Creates a brand; duplicate names are allowed and code is generated by the server. See BrandCreate for logo host restrictions. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "name": {
          "description": "Trimmed before validation.",
          "maxLength": 128,
          "minLength": 1,
          "type": "string"
        },
        "description": {
          "maxLength": 512,
          "type": "string"
        },
        "logoUrl": {
          "description": "Empty string clears. Only HTTP(S), no credentials, allowlisted MuseDAM CDN or configured storage host; query and fragment removed before storage. No upload; not echoed in reads.",
          "maxLength": 512,
          "type": "string"
        }
      },
      "required": [
        "name"
      ],
      "title": "Create brand",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_create_brandArguments",
  "type": "object"
}
```

## musedam_product_get_brand

Read brand. Returns the specified brand’s public metadata. Raw logo URLs are excluded. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Read brand",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_get_brandArguments",
  "type": "object"
}
```

## musedam_product_update_brand

Update brand. Updates the provided metadata fields; omitted properties remain unchanged. No file upload or generic asset replacement. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "minProperties": 2,
      "properties": {
        "name": {
          "description": "Trimmed before validation.",
          "maxLength": 128,
          "minLength": 1,
          "type": "string"
        },
        "description": {
          "maxLength": 512,
          "type": "string"
        },
        "logoUrl": {
          "description": "Empty string clears. Only HTTP(S), no credentials, allowlisted MuseDAM CDN or configured storage host; query and fragment removed before storage. No upload; not echoed in reads.",
          "maxLength": 512,
          "type": "string"
        },
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Update brand",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_update_brandArguments",
  "type": "object"
}
```

## musedam_product_delete_brand

Delete brand. Deletes only a brand with no live categories or products. Returns 409 otherwise; never cascades into products. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Delete brand",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_delete_brandArguments",
  "type": "object"
}
```

## musedam_product_list_categorys

List categorys. Returns a flat live tree ordered by brandId, parentId, sortOrder and id. Optional brand filter; no implicit subtree expansion. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "page": {
          "default": 1,
          "description": "Ordinary page number. Not allowed when sync=true. Excessive offset causing integer overflow is rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "default": 20,
          "description": "Page size; values above 100 are capped at 100. Nonpositive/noninteger values are rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "brandId": {
          "description": "Filter by brand ID within this library.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [],
      "title": "List categorys",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_list_categorysArguments",
  "type": "object"
}
```

## musedam_product_create_category

Create category. Creates a live node in the specified brand. Parent must be live in the same brand/library. Max depth 10 and max 5000 live nodes per brand. Sibling names must be unique. The library default template is explicitly bound only when it has no brand bindings or includes this brand; otherwise creation succeeds without an explicit binding, preserving ancestor, brand, then library-default template resolution. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "brandId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "name": {
          "description": "Exact value, not trimmed. Must contain non-whitespace and no slash; unique among live siblings.",
          "maxLength": 64,
          "minLength": 1,
          "pattern": "^(?=.*\\S)[^/]+$",
          "type": "string"
        },
        "parentId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "sortOrder": {
          "description": "Sibling insertion index, no greater than destination sibling count. Omitted: append on create/move, preserve for same parent.",
          "maximum": 5000,
          "minimum": 0,
          "type": "integer"
        },
        "description": {
          "type": "string"
        },
        "iconEmoji": {
          "maxLength": 16,
          "type": "string"
        },
        "iconAssetId": {
          "description": "Existing same-library CategoryIconAsset ID, not FilePath ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "isEnabled": {
          "type": "boolean"
        }
      },
      "required": [
        "brandId",
        "name"
      ],
      "title": "Create category",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_create_categoryArguments",
  "type": "object"
}
```

## musedam_product_get_category

Read category. Returns the specified nondeleted category. A missing category or one outside the current library returns 404. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Read category",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_get_categoryArguments",
  "type": "object"
}
```

## musedam_product_update_category

Update category. Updates or moves a node within its existing brand; brandId is immutable. Rejects cycles/depth/node limits and invalid sort index. Updates descendant paths atomically. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "minProperties": 2,
      "properties": {
        "name": {
          "description": "Exact value, not trimmed. Must contain non-whitespace and no slash; unique among live siblings.",
          "maxLength": 64,
          "minLength": 1,
          "pattern": "^(?=.*\\S)[^/]+$",
          "type": "string"
        },
        "parentId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "sortOrder": {
          "description": "Sibling insertion index, no greater than destination sibling count. Omitted: append on create/move, preserve for same parent.",
          "maximum": 5000,
          "minimum": 0,
          "type": "integer"
        },
        "description": {
          "type": "string"
        },
        "iconEmoji": {
          "maxLength": 16,
          "type": "string"
        },
        "iconAssetId": {
          "description": "Existing same-library CategoryIconAsset ID, not FilePath ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "isEnabled": {
          "type": "boolean"
        },
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Update category",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_update_categoryArguments",
  "type": "object"
}
```

## musedam_product_delete_category

Delete category. Soft-deletes the entire category subtree only if no live products reference any descendant. Does not delete or demote products. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Delete category",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_delete_categoryArguments",
  "type": "object"
}
```

## musedam_product_list_templates

List templates. Returns live template metadata, bindings and ordered groups/fields, including preview-only configuration. Ordered by createdAt descending then id. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "page": {
          "default": 1,
          "description": "Ordinary page number. Not allowed when sync=true. Excessive offset causing integer overflow is rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "default": 20,
          "description": "Page size; values above 100 are capped at 100. Nonpositive/noninteger values are rejected.",
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [],
      "title": "List templates",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_list_templatesArguments",
  "type": "object"
}
```

## musedam_product_create_template

Create template. Creates a template and an immutable version. syncStrategy is optional and only newOnly is supported. Allows at most 200 fields and leaves existing products unchanged. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "description": "Trim name/description. At most 200 fields across all groups. Bindings must be same-library, replace the provided binding set, and may move a binding from another template. When selected brands are nonempty, selected categories must belong to those brands. Only newOnly is supported; never bulk-repin existing products.",
      "properties": {
        "name": {
          "maxLength": 30,
          "minLength": 1,
          "type": "string"
        },
        "description": {
          "maxLength": 50,
          "type": "string"
        },
        "enabled": {
          "type": "boolean"
        },
        "groups": {
          "items": {
            "additionalProperties": false,
            "description": "Name is trimmed. Existing ID must belong to this template. Existing groups retain their stored order; new groups append in supplied order. No isDefault or sortOrder input.",
            "properties": {
              "id": {
                "maxLength": 128,
                "minLength": 1,
                "type": "string"
              },
              "name": {
                "maxLength": 128,
                "minLength": 1,
                "type": "string"
              },
              "fields": {
                "items": {
                  "additionalProperties": false,
                  "description": "New fields require key/name/type. Existing IDs must belong to this group; preserve their key and system identity. System fields cannot be created. Type changes need typeChangeConfirmed where the existing batch rules require it. Omitted new-field defaults: required=false, placeholder=null, config={}, sortOrder=array index.",
                  "properties": {
                    "id": {
                      "maxLength": 128,
                      "minLength": 1,
                      "type": "string"
                    },
                    "key": {
                      "description": "Required for new fields; valid identifier. Immutable for existing fields.",
                      "maxLength": 64,
                      "minLength": 1,
                      "type": "string"
                    },
                    "name": {
                      "maxLength": 128,
                      "minLength": 1,
                      "type": "string"
                    },
                    "type": {
                      "enum": [
                        "text",
                        "textarea",
                        "email",
                        "phone",
                        "url",
                        "color",
                        "richtext",
                        "number",
                        "currency",
                        "date",
                        "dateRange",
                        "select",
                        "radio",
                        "checkbox",
                        "image",
                        "file"
                      ],
                      "type": "string"
                    },
                    "required": {
                      "type": "boolean"
                    },
                    "placeholder": {
                      "maxLength": 255,
                      "type": "string"
                    },
                    "sortOrder": {
                      "minimum": 0,
                      "type": "integer"
                    },
                    "config": {
                      "additionalProperties": true,
                      "description": "Validated using the resolved field type/system identity, including existing field identity on updateTemplate. See x-config-by-field-type and SystemFieldConfig; existing system field settings (type, required, config) are immutable through this API. Unknown properties are rejected by empty/system configs and stripped by other config validators.",
                      "type": "object",
                      "x-config-by-field-type": {
                        "checkbox": {
                          "additionalProperties": true,
                          "description": "Option values must be unique. Unknown config/option properties are stripped by validation.",
                          "properties": {
                            "options": {
                              "items": {
                                "additionalProperties": true,
                                "properties": {
                                  "value": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "label": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "sortOrder": {
                                    "minimum": 0,
                                    "type": "integer"
                                  },
                                  "archived": {
                                    "type": "boolean"
                                  }
                                },
                                "required": [
                                  "value",
                                  "label",
                                  "sortOrder"
                                ],
                                "type": "object"
                              },
                              "minItems": 1,
                              "type": "array"
                            }
                          },
                          "required": [
                            "options"
                          ],
                          "type": "object"
                        },
                        "color": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "currency": {
                          "additionalProperties": true,
                          "properties": {
                            "code": {
                              "minLength": 1,
                              "type": "string"
                            },
                            "symbol": {
                              "minLength": 1,
                              "type": "string"
                            },
                            "decimals": {
                              "maximum": 4,
                              "minimum": 0,
                              "type": "integer"
                            }
                          },
                          "required": [
                            "code",
                            "symbol",
                            "decimals"
                          ],
                          "type": "object"
                        },
                        "date": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "dateRange": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "email": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "file": {
                          "additionalProperties": true,
                          "properties": {
                            "maxCount": {
                              "minimum": 1,
                              "type": "integer"
                            },
                            "maxSizeMB": {
                              "exclusiveMinimum": true,
                              "minimum": 0,
                              "type": "number"
                            },
                            "accept": {
                              "items": {
                                "type": "string"
                              },
                              "type": "array"
                            }
                          },
                          "type": "object"
                        },
                        "image": {
                          "additionalProperties": true,
                          "properties": {
                            "maxCount": {
                              "minimum": 1,
                              "type": "integer"
                            },
                            "maxSizeMB": {
                              "exclusiveMinimum": true,
                              "minimum": 0,
                              "type": "number"
                            },
                            "accept": {
                              "items": {
                                "type": "string"
                              },
                              "type": "array"
                            }
                          },
                          "type": "object"
                        },
                        "number": {
                          "additionalProperties": true,
                          "properties": {
                            "unit": {
                              "type": "string"
                            }
                          },
                          "type": "object"
                        },
                        "phone": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "radio": {
                          "additionalProperties": true,
                          "description": "Option values must be unique. Unknown config/option properties are stripped by validation.",
                          "properties": {
                            "options": {
                              "items": {
                                "additionalProperties": true,
                                "properties": {
                                  "value": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "label": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "sortOrder": {
                                    "minimum": 0,
                                    "type": "integer"
                                  },
                                  "archived": {
                                    "type": "boolean"
                                  }
                                },
                                "required": [
                                  "value",
                                  "label",
                                  "sortOrder"
                                ],
                                "type": "object"
                              },
                              "minItems": 1,
                              "type": "array"
                            }
                          },
                          "required": [
                            "options"
                          ],
                          "type": "object"
                        },
                        "richtext": {
                          "additionalProperties": true,
                          "properties": {
                            "mode": {
                              "enum": [
                                "html",
                                "delta"
                              ],
                              "type": "string"
                            }
                          },
                          "required": [
                            "mode"
                          ],
                          "type": "object"
                        },
                        "select": {
                          "additionalProperties": true,
                          "description": "Option values must be unique. Unknown config/option properties are stripped by validation.",
                          "properties": {
                            "options": {
                              "items": {
                                "additionalProperties": true,
                                "properties": {
                                  "value": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "label": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "sortOrder": {
                                    "minimum": 0,
                                    "type": "integer"
                                  },
                                  "archived": {
                                    "type": "boolean"
                                  }
                                },
                                "required": [
                                  "value",
                                  "label",
                                  "sortOrder"
                                ],
                                "type": "object"
                              },
                              "minItems": 1,
                              "type": "array"
                            }
                          },
                          "required": [
                            "options"
                          ],
                          "type": "object"
                        },
                        "text": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "textarea": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "url": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        }
                      },
                      "x-system-config": {
                        "additionalProperties": false,
                        "properties": {
                          "customPlaceholder": {
                            "maxLength": 255,
                            "type": "string"
                          }
                        },
                        "type": "object"
                      }
                    },
                    "isSystemField": {
                      "type": "boolean"
                    },
                    "systemKey": {
                      "enum": [
                        "name",
                        "sku",
                        "brand",
                        "category",
                        "description",
                        "mainImage"
                      ],
                      "type": "string"
                    },
                    "typeChangeConfirmed": {
                      "type": "boolean"
                    }
                  },
                  "type": "object"
                },
                "maxItems": 200,
                "type": "array"
              }
            },
            "required": [
              "name",
              "fields"
            ],
            "type": "object"
          },
          "maxItems": 200,
          "minItems": 1,
          "type": "array"
        },
        "boundBrandIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 10000,
          "type": "array"
        },
        "boundCategoryIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 10000,
          "type": "array"
        },
        "isLibraryDefault": {
          "type": "boolean"
        },
        "syncStrategy": {
          "default": "newOnly",
          "enum": [
            "newOnly"
          ],
          "type": "string"
        }
      },
      "required": [
        "name",
        "groups"
      ],
      "title": "Create template",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_create_templateArguments",
  "type": "object"
}
```

## musedam_product_get_template

Read template. Returns the specified nondeleted template’s metadata, bindings, and groups/fields, including preview-only configuration. Groups and fields are ordered by sortOrder then id, ascending. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Opaque template ID; do not assume UUID syntax.",
          "maxLength": 128,
          "minLength": 1,
          "type": "string"
        }
      },
      "required": [
        "id"
      ],
      "title": "Read template",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_get_templateArguments",
  "type": "object"
}
```

## musedam_product_update_template

Update template. Uses the shared browser batch operation. Supplied groups/fields are a complete replacement; omitted groups are preserved. Stable IDs and protected system/default fields are validated. Creates a new immutable version without migrating existing product pins or values; bindings/default changes affect future template resolution. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "description": "Omitted groups are preserved; supplied groups replace the entire live set. Preserve stable group/field IDs. Omitted groups/fields are deleted, subject to protected default/system fields. Every successful write creates a new immutable version, including metadata-only updates.",
      "minProperties": 2,
      "properties": {
        "name": {
          "maxLength": 30,
          "minLength": 1,
          "type": "string"
        },
        "description": {
          "maxLength": 50,
          "type": "string"
        },
        "enabled": {
          "type": "boolean"
        },
        "groups": {
          "items": {
            "additionalProperties": false,
            "description": "Name is trimmed. Existing ID must belong to this template. Existing groups retain their stored order; new groups append in supplied order. No isDefault or sortOrder input.",
            "properties": {
              "id": {
                "maxLength": 128,
                "minLength": 1,
                "type": "string"
              },
              "name": {
                "maxLength": 128,
                "minLength": 1,
                "type": "string"
              },
              "fields": {
                "items": {
                  "additionalProperties": false,
                  "description": "New fields require key/name/type. Existing IDs must belong to this group; preserve their key and system identity. System fields cannot be created. Type changes need typeChangeConfirmed where the existing batch rules require it. Omitted new-field defaults: required=false, placeholder=null, config={}, sortOrder=array index.",
                  "properties": {
                    "id": {
                      "maxLength": 128,
                      "minLength": 1,
                      "type": "string"
                    },
                    "key": {
                      "description": "Required for new fields; valid identifier. Immutable for existing fields.",
                      "maxLength": 64,
                      "minLength": 1,
                      "type": "string"
                    },
                    "name": {
                      "maxLength": 128,
                      "minLength": 1,
                      "type": "string"
                    },
                    "type": {
                      "enum": [
                        "text",
                        "textarea",
                        "email",
                        "phone",
                        "url",
                        "color",
                        "richtext",
                        "number",
                        "currency",
                        "date",
                        "dateRange",
                        "select",
                        "radio",
                        "checkbox",
                        "image",
                        "file"
                      ],
                      "type": "string"
                    },
                    "required": {
                      "type": "boolean"
                    },
                    "placeholder": {
                      "maxLength": 255,
                      "type": "string"
                    },
                    "sortOrder": {
                      "minimum": 0,
                      "type": "integer"
                    },
                    "config": {
                      "additionalProperties": true,
                      "description": "Validated using the resolved field type/system identity, including existing field identity on updateTemplate. See x-config-by-field-type and SystemFieldConfig; existing system field settings (type, required, config) are immutable through this API. Unknown properties are rejected by empty/system configs and stripped by other config validators.",
                      "type": "object",
                      "x-config-by-field-type": {
                        "checkbox": {
                          "additionalProperties": true,
                          "description": "Option values must be unique. Unknown config/option properties are stripped by validation.",
                          "properties": {
                            "options": {
                              "items": {
                                "additionalProperties": true,
                                "properties": {
                                  "value": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "label": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "sortOrder": {
                                    "minimum": 0,
                                    "type": "integer"
                                  },
                                  "archived": {
                                    "type": "boolean"
                                  }
                                },
                                "required": [
                                  "value",
                                  "label",
                                  "sortOrder"
                                ],
                                "type": "object"
                              },
                              "minItems": 1,
                              "type": "array"
                            }
                          },
                          "required": [
                            "options"
                          ],
                          "type": "object"
                        },
                        "color": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "currency": {
                          "additionalProperties": true,
                          "properties": {
                            "code": {
                              "minLength": 1,
                              "type": "string"
                            },
                            "symbol": {
                              "minLength": 1,
                              "type": "string"
                            },
                            "decimals": {
                              "maximum": 4,
                              "minimum": 0,
                              "type": "integer"
                            }
                          },
                          "required": [
                            "code",
                            "symbol",
                            "decimals"
                          ],
                          "type": "object"
                        },
                        "date": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "dateRange": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "email": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "file": {
                          "additionalProperties": true,
                          "properties": {
                            "maxCount": {
                              "minimum": 1,
                              "type": "integer"
                            },
                            "maxSizeMB": {
                              "exclusiveMinimum": true,
                              "minimum": 0,
                              "type": "number"
                            },
                            "accept": {
                              "items": {
                                "type": "string"
                              },
                              "type": "array"
                            }
                          },
                          "type": "object"
                        },
                        "image": {
                          "additionalProperties": true,
                          "properties": {
                            "maxCount": {
                              "minimum": 1,
                              "type": "integer"
                            },
                            "maxSizeMB": {
                              "exclusiveMinimum": true,
                              "minimum": 0,
                              "type": "number"
                            },
                            "accept": {
                              "items": {
                                "type": "string"
                              },
                              "type": "array"
                            }
                          },
                          "type": "object"
                        },
                        "number": {
                          "additionalProperties": true,
                          "properties": {
                            "unit": {
                              "type": "string"
                            }
                          },
                          "type": "object"
                        },
                        "phone": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "radio": {
                          "additionalProperties": true,
                          "description": "Option values must be unique. Unknown config/option properties are stripped by validation.",
                          "properties": {
                            "options": {
                              "items": {
                                "additionalProperties": true,
                                "properties": {
                                  "value": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "label": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "sortOrder": {
                                    "minimum": 0,
                                    "type": "integer"
                                  },
                                  "archived": {
                                    "type": "boolean"
                                  }
                                },
                                "required": [
                                  "value",
                                  "label",
                                  "sortOrder"
                                ],
                                "type": "object"
                              },
                              "minItems": 1,
                              "type": "array"
                            }
                          },
                          "required": [
                            "options"
                          ],
                          "type": "object"
                        },
                        "richtext": {
                          "additionalProperties": true,
                          "properties": {
                            "mode": {
                              "enum": [
                                "html",
                                "delta"
                              ],
                              "type": "string"
                            }
                          },
                          "required": [
                            "mode"
                          ],
                          "type": "object"
                        },
                        "select": {
                          "additionalProperties": true,
                          "description": "Option values must be unique. Unknown config/option properties are stripped by validation.",
                          "properties": {
                            "options": {
                              "items": {
                                "additionalProperties": true,
                                "properties": {
                                  "value": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "label": {
                                    "minLength": 1,
                                    "type": "string"
                                  },
                                  "sortOrder": {
                                    "minimum": 0,
                                    "type": "integer"
                                  },
                                  "archived": {
                                    "type": "boolean"
                                  }
                                },
                                "required": [
                                  "value",
                                  "label",
                                  "sortOrder"
                                ],
                                "type": "object"
                              },
                              "minItems": 1,
                              "type": "array"
                            }
                          },
                          "required": [
                            "options"
                          ],
                          "type": "object"
                        },
                        "text": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "textarea": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        },
                        "url": {
                          "additionalProperties": false,
                          "properties": {},
                          "type": "object"
                        }
                      },
                      "x-system-config": {
                        "additionalProperties": false,
                        "properties": {
                          "customPlaceholder": {
                            "maxLength": 255,
                            "type": "string"
                          }
                        },
                        "type": "object"
                      }
                    },
                    "isSystemField": {
                      "type": "boolean"
                    },
                    "systemKey": {
                      "enum": [
                        "name",
                        "sku",
                        "brand",
                        "category",
                        "description",
                        "mainImage"
                      ],
                      "type": "string"
                    },
                    "typeChangeConfirmed": {
                      "type": "boolean"
                    }
                  },
                  "type": "object"
                },
                "maxItems": 200,
                "type": "array"
              }
            },
            "required": [
              "name",
              "fields"
            ],
            "type": "object"
          },
          "maxItems": 200,
          "minItems": 1,
          "type": "array"
        },
        "boundBrandIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 10000,
          "type": "array"
        },
        "boundCategoryIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 10000,
          "type": "array"
        },
        "isLibraryDefault": {
          "type": "boolean"
        },
        "syncStrategy": {
          "default": "newOnly",
          "enum": [
            "newOnly"
          ],
          "type": "string"
        },
        "id": {
          "description": "Opaque template ID; do not assume UUID syntax.",
          "maxLength": 128,
          "minLength": 1,
          "type": "string"
        }
      },
      "required": [
        "id"
      ],
      "title": "Update template",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_update_templateArguments",
  "type": "object"
}
```

## musedam_product_delete_template

Delete template. Soft-deletes the live template while retaining immutable versions used by existing products. Current library default requires an explicit replacement or null; default/system protections still apply. Removes bindings without rewriting existing product pins. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "description": "Optional business property. If deleting the current library default, replacementForLibraryDefault must be a different live same-library template ID. Historical versions remain available to pinned products.",
      "properties": {
        "replacementForLibraryDefault": {
          "maxLength": 128,
          "minLength": 1,
          "type": "string"
        },
        "id": {
          "description": "Opaque template ID; do not assume UUID syntax.",
          "maxLength": 128,
          "minLength": 1,
          "type": "string"
        }
      },
      "required": [
        "id"
      ],
      "title": "Delete template",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_delete_templateArguments",
  "type": "object"
}
```

## musedam_product_list_products

List or synchronize products. Ordinary pagination orders updatedAt/id descending. sync=true uses ascending (updatedAt,id), inclusive lower and exclusive fixed upper bound (server clock minus 30 seconds). A full scan omits updatedAfter; continue every nextCursor, even with an empty data page. Cursor binds key/role/library/filters/pageSize/bounds. Save syncedUntil verbatim only after exhaustion; replay/deduplicate by id and updatedAt. Transactions longer than the 30-second safety window are an accepted v1 limitation. view_only/usable see only published products. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "page": {
          "default": 1,
          "description": "Ordinary page number. Not allowed when sync=true. Excessive offset causing integer overflow is rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "default": 20,
          "description": "Page size; values above 100 are capped at 100. Nonpositive/noninteger values are rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "search": {
          "description": "Trimmed case-insensitive substring matching product name or spu.",
          "type": "string"
        },
        "brandId": {
          "description": "Filter by brand ID within this library.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "categoryId": {
          "description": "Filter by exact category ID, not its descendants.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "status": {
          "description": "Requested product status; does not widen role visibility.",
          "enum": [
            "draft",
            "published"
          ],
          "type": "string"
        },
        "sync": {
          "default": "false",
          "description": "true selects bounded keyset synchronization; false is ordinary pagination.",
          "enum": [
            "true",
            "false"
          ],
          "type": "string"
        },
        "updatedAfter": {
          "description": "Only with sync=true. Inclusive lower bound; RFC3339 Z/offset, 0..6 fractional digits, valid calendar/offset. Save and reuse syncedUntil as a string. Omit for a full scan.",
          "format": "date-time",
          "type": "string"
        },
        "cursor": {
          "description": "Opaque continuation token, only with sync=true. Binds key, role, library, bounds, filters and page size. On continuation omit other parameters or repeat equivalent values. Supply each body property only once.",
          "maxLength": 8192,
          "minLength": 1,
          "type": "string"
        }
      },
      "required": [],
      "title": "List or synchronize products",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_list_productsArguments",
  "type": "object"
}
```

## musedam_product_create_product

Create a draft product. Creates draft only. Resolves and pins a template version at creation; template fields validate against that immutable definition. Attach existing same-library FilePath IDs; no upload, remote import or provider write-back. Requires Product Library API Key collaborator access; roles: editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "description": "Always creates draft. Explicit templateId must be a live same-library template and takes precedence. When templateId is omitted and a categoryId is supplied, resolution follows category or ancestor binding, then that category's brand binding, then library default. When categoryId is omitted, only the library default is considered, even if brandId is supplied. If no template resolves, the product has no template. Category must match resulting brand; owner must be a same-team member and defaults to null, not key creator. At most 100 total references across cover/images/related/custom media. Image slots require images; custom media must satisfy pinned count/size/type limits.",
      "properties": {
        "name": {
          "description": "Trimmed; optional/empty for draft.",
          "maxLength": 255,
          "type": "string"
        },
        "spu": {
          "description": "Trimmed; blank clears. Unique within the library, including soft-deleted products.",
          "maxLength": 64,
          "type": "string"
        },
        "description": {
          "description": "Empty string clears to null.",
          "type": "string"
        },
        "brandId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "categoryId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "ownerUserId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "templateId": {
          "maxLength": 128,
          "minLength": 1,
          "type": "string"
        },
        "templateFields": {
          "additionalProperties": {
            "oneOf": [
              {
                "type": "string"
              },
              {
                "type": "number"
              },
              {
                "type": "boolean"
              },
              {
                "items": {},
                "type": "array"
              },
              {
                "additionalProperties": true,
                "type": "object"
              }
            ]
          },
          "description": "Map keyed by stable custom field ID from the resolved template version. Unknown/system IDs rejected. Types/options validated even for drafts. image/file values are arrays of FilePath IDs, not URL/object snapshots. Richtext documents may contain internal nulls.",
          "type": "object"
        },
        "coverAssetId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "imageAssetIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 100,
          "type": "array"
        },
        "relatedAssetIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 100,
          "type": "array"
        }
      },
      "required": [],
      "title": "Create a draft product",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_create_productArguments",
  "type": "object"
}
```

## musedam_product_get_product

Read a product and its pinned definition. Returns an accessible live product with its pinned immutable template definition, even after the live template changes or is deleted. Does not require templates:read. Media preview/download is authorized on every response; download requires products:read plus products:download and role usable or higher. Drafts are invisible to view_only/usable. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Read a product and its pinned definition",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_get_productArguments",
  "type": "object"
}
```

## musedam_product_update_product

Partially update a product. Merges scalar/custom fields and replaces submitted media lists. Uses the immutable pinned definition, including when the live template is deleted. Published products additionally require products:publish and stay published; full resulting-state validation must pass atomically. Status/template switching is not accepted here. Requires Product Library API Key collaborator access; roles: editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "description": "Omitted fields remain unchanged; empty strings and [] retain their existing clear behavior. templateFields merges; media arrays replace their slot. If imageAssetIds is provided without coverAssetId, first image becomes cover. Published products require products:publish and remain published, with full resulting-state validation. templateId, templateVersionId and status are rejected.",
      "minProperties": 2,
      "properties": {
        "name": {
          "description": "Trimmed; optional/empty for draft.",
          "maxLength": 255,
          "type": "string"
        },
        "spu": {
          "description": "Trimmed; blank clears. Unique within the library, including soft-deleted products.",
          "maxLength": 64,
          "type": "string"
        },
        "description": {
          "description": "Empty string clears to null.",
          "type": "string"
        },
        "brandId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "categoryId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "ownerUserId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "templateFields": {
          "additionalProperties": {
            "oneOf": [
              {
                "type": "string"
              },
              {
                "type": "number"
              },
              {
                "type": "boolean"
              },
              {
                "items": {},
                "type": "array"
              },
              {
                "additionalProperties": true,
                "type": "object"
              }
            ]
          },
          "description": "Shallow merge by stable custom field ID; omitted values remain unchanged. Unknown/system IDs rejected. Types/options validated even for drafts. image/file values are arrays of FilePath IDs, not URL/object snapshots. Richtext documents may contain internal nulls. PATCH validates against the pinned version, even if its live template was deleted.",
          "type": "object"
        },
        "coverAssetId": {
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        },
        "imageAssetIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 100,
          "type": "array"
        },
        "relatedAssetIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 100,
          "type": "array"
        },
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Partially update a product",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_update_productArguments",
  "type": "object"
}
```

## musedam_product_delete_product

Soft-delete a product. Soft-deletes a visible live product. Draft requires delete; published requires delete and publish. Leaves historical template versions intact. No provider synchronization. A repeated delete returns 404. Requires Product Library API Key collaborator access; roles: editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Soft-delete a product",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_delete_productArguments",
  "type": "object"
}
```

## musedam_product_set_product_status

Publish or return a product to draft. Always requires both update and publish grants. Publishing validates all pinned required/type/option/media rules; invalid state returns 422 with field details and makes no changes. Repeated published keeps publishedAt, returning to draft clears it. No approval workflow is started. Requires Product Library API Key collaborator access; roles: editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "description": "Both products:update and products:publish required for either transition, including same-status requests. Publish validates all required pinned fields and current media; failure is atomic. publishedAt is set on first publication, retained on repeated publication and cleared on draft.",
      "properties": {
        "status": {
          "enum": [
            "draft",
            "published"
          ],
          "type": "string"
        },
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "status",
        "id"
      ],
      "title": "Publish or return a product to draft",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_set_product_statusArguments",
  "type": "object"
}
```

## musedam_product_check_product_visibility

Reconcile known product IDs. Checks up to 100 known IDs under current key visibility. Keeps order and duplicates, accepts an empty array. not_visible does not distinguish deleted, missing, foreign-library and role-hidden items. Use periodically to remove stale local entries because sync has no deletion tombstones. Requires Product Library API Key collaborator access; roles: view_only, usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "description": "0..100 IDs. Output preserves input order and duplicates; [] returns [].",
      "properties": {
        "ids": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 100,
          "type": "array"
        }
      },
      "required": [
        "ids"
      ],
      "title": "Reconcile known product IDs",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_check_product_visibilityArguments",
  "type": "object"
}
```

## musedam_product_list_assets

Find existing library assets. Lists live non-directory FilePath assets in the key library, ordered by id. Requires either products:create or products:update under editable/manage role, not products:read. Returns previews only, never original download fields. Use FilePath id in product writes; uploads are outside v1. Requires Product Library API Key collaborator access; roles: editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "page": {
          "default": 1,
          "description": "Ordinary page number. Not allowed when sync=true. Excessive offset causing integer overflow is rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "default": 20,
          "description": "Page size; values above 100 are capped at 100. Nonpositive/noninteger values are rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "search": {
          "description": "Trimmed case-insensitive substring matching library asset name.",
          "type": "string"
        },
        "mimeType": {
          "description": "Trimmed case-insensitive MIME prefix, for example image/ or application/pdf.",
          "type": "string"
        }
      },
      "required": [],
      "title": "Find existing library assets",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_list_assetsArguments",
  "type": "object"
}
```

## musedam_product_get_asset

Read an existing library asset. Returns a live same-library FilePath with preview-only media metadata. Same create-or-update gate as listing. Requires Product Library API Key collaborator access; roles: editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Positive signed 32-bit resource ID.",
          "maximum": 2147483647,
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [
        "id"
      ],
      "title": "Read an existing library asset",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_get_assetArguments",
  "type": "object"
}
```

## musedam_product_list_product_shares

List team share history. Lists records from every browser actor and API key in the current team, newest first by createdAt and id. Optional productId returns complete matching operations; omission selects all team records. Only productId, page and pageSize are accepted; unknown business parameters return 422. The current API key or creator never implicitly narrows the list. Requires manage plus products:history, without products:read. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "productId": {
          "allOf": [
            {
              "maximum": 2147483647,
              "minimum": 1,
              "type": "integer"
            }
          ],
          "description": "Filter matching shares by one product ID. The full share record is returned, including all products in that share. Omit for all records in the current team."
        },
        "page": {
          "default": 1,
          "description": "Ordinary page number. Not allowed when sync=true. Excessive offset causing integer overflow is rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "default": 20,
          "description": "Page size; values above 100 are capped at 100. Nonpositive/noninteger values are rejected.",
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [],
      "title": "List team share history",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_list_product_sharesArguments",
  "type": "object"
}
```

## musedam_product_create_product_share

Create product share. Creates a fixed selection of published products with a 7/30/90-day lifetime. accessCode is optional and exactly four digits. allowDownload additionally requires products:download. The recipient needs no login or API key; unpublished/deleted products disappear from the live share. Creator-key changes do not revoke the independent team share. Requires Product Library API Key collaborator access; roles: usable, editable, manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "productIds": {
          "items": {
            "maximum": 2147483647,
            "minimum": 1,
            "type": "integer"
          },
          "maxItems": 100,
          "minItems": 1,
          "type": "array"
        },
        "expiresInDays": {
          "enum": [
            7,
            30,
            90
          ],
          "type": "integer"
        },
        "accessCode": {
          "pattern": "^[0-9]{4}$",
          "type": "string"
        },
        "allowDownload": {
          "type": "boolean"
        }
      },
      "required": [
        "productIds",
        "expiresInDays",
        "allowDownload"
      ],
      "title": "Create product share",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_create_product_shareArguments",
  "type": "object"
}
```

## musedam_product_revoke_product_share

Revoke product share. Revokes any share in the current team. Requires manage and products:share, without products:read. Repeating a revocation returns the original revokedAt. Unknown or foreign-team IDs return 404. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "description": "Opaque share identifier.",
          "maxLength": 128,
          "minLength": 1,
          "type": "string"
        }
      },
      "required": [
        "id"
      ],
      "title": "Revoke product share",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_revoke_product_shareArguments",
  "type": "object"
}
```

## musedam_product_list_product_downloads

List team download history. Lists records from every browser actor and API key in the current team, newest first by createdAt and id. Optional productId returns complete matching operations; omission selects all team records. Only productId, page and pageSize are accepted; unknown business parameters return 422. The current API key or creator never implicitly narrows the list. Requires manage plus products:history, without products:read. Requires Product Library API Key collaborator access; roles: manage

```json
{
  "properties": {
    "params": {
      "additionalProperties": false,
      "properties": {
        "productId": {
          "allOf": [
            {
              "maximum": 2147483647,
              "minimum": 1,
              "type": "integer"
            }
          ],
          "description": "Filter matching activity by one product ID. The full operation is returned, including other products and files. Omit for all records in the current team."
        },
        "page": {
          "default": 1,
          "description": "Ordinary page number. Not allowed when sync=true. Excessive offset causing integer overflow is rejected.",
          "minimum": 1,
          "type": "integer"
        },
        "pageSize": {
          "default": 20,
          "description": "Page size; values above 100 are capped at 100. Nonpositive/noninteger values are rejected.",
          "minimum": 1,
          "type": "integer"
        }
      },
      "required": [],
      "title": "List team download history",
      "type": "object"
    }
  },
  "required": [
    "params"
  ],
  "title": "musedam_product_list_product_downloadsArguments",
  "type": "object"
}
```
