# TideStack 元数据 Schema

TideStack/Ouroboros 元数据资源的 JSON Schema 定义。

本目录是一个可独立发布的 schema 包，面向开发者、校验工具、IDE 集成和构建流程，用于为各类元数据 JSON 文件提供稳定的结构契约。

英文版：[README.en.md](README.en.md)

## 目录内容

- `*.schema.json`：每类元数据对应的 JSON Schema Draft 2020-12 定义。
- `index.json`：机器可读的 schema 索引，包含元数据类型、展示名称、文件后缀、schema 文件名和路径。
- `LICENSE`：本 schema 包的 Apache License 2.0 授权文本。

## 使用方式

根据元数据文件后缀选择对应 schema，然后使用兼容 Draft 2020-12 的 JSON Schema 校验器进行校验。

例如，文件名以 `.ui-model.json` 结尾时，应使用 `ui-model.schema.json` 校验。

```bash
npx ajv-cli validate --spec=draft2020 -s ui-model.schema.json -d path/to/example.ui-model.json
```

需要动态发现 schema 的消费者应读取 `index.json`，不要硬编码下方表格。

## Schema 清单

| 类型 | 展示名称 | 文件后缀 | Schema |
| --- | --- | --- | --- |
| `authority` | 权限项模型 | `.authority.json` | `authority.schema.json` |
| `menu` | 菜单模型 | `.menu.json` | `menu.schema.json` |
| `dev-menu` | 开发菜单模型 | `.dev-menu.json` | `dev-menu.schema.json` |
| `ui-model` | UI 模型 | `.ui-model.json` | `ui-model.schema.json` |
| `ui-schema` | UI Schema | `.ui-schema.json` | `ui-schema.schema.json` |
| `business` | 业务模型 | `.business.json` | `business.schema.json` |
| `logicflow` | 逻辑流模型 | `.logicflow.json` | `logicflow.schema.json` |
| `approval-workflow` | 审批流 | `.workflow.json` | `approval-workflow.schema.json` |
| `field-type` | 字段类型 | `.field-type.json` | `field-type.schema.json` |
| `flow-node` | 逻辑流节点 | `.flow-node.json` | `flow-node.schema.json` |
| `widget` | 组件定义 | `.widget.json` | `widget.schema.json` |
| `micro-web` | 微前端 | `.micro-web.json` | `micro-web.schema.json` |
| `rpc` | RPC 模型 | `.rpc.json` | `rpc.schema.json` |
| `rpc-auth` | RPC 认证 | `.rpc.auth.json` | `rpc-auth.schema.json` |
| `webapi` | WebAPI 模型 | `.webapi.json` | `webapi.schema.json` |
| `notification` | 通知模板 | `.notification.json` | `notification.schema.json` |
| `business-log` | 业务日志模板 | `.business-log.json` | `business-log.schema.json` |
| `data-init` | 数据初始化 | `.data-init.json` | `data-init.schema.json` |
| `mq` | MQ 绑定 | `.mq.json` | `mq.schema.json` |
| `schedule` | 定时任务 | `.schedule.json` | `schedule.schema.json` |
| `i18n` | 国际化语言包 | `.i18n.json` | `i18n.schema.json` |
| `data-dict` | 数据字典 | `.dict.json` | `data-dict.schema.json` |
| `position` | 岗位定义 | `.position.json` | `position.schema.json` |
| `error-code` | 错误码 | 无固定后缀 | `error-code.schema.json` |
| `app-metadata` | 应用元数据 | 无固定后缀 | `app-metadata.schema.json` |
| `modules-diff` | 模块树 Diff | 无固定后缀 | `modules-diff.schema.json` |
| `app-module` | 应用模块 | 无固定后缀 | `app-module.schema.json` |
| `configuration` | 配置项 | 无固定后缀 | `configuration.schema.json` |
| `configuration-group` | 配置分组 | 无固定后缀 | `configuration-group.schema.json` |
| `configuration-item` | 配置项 | `.config.json` | `configuration-item.schema.json` |
| `configuration-group-item` | 配置分组 | `.config-group.json` | `configuration-group-item.schema.json` |

## 版本说明

这些 schema 用于描述当前公开的元数据结构契约。发生破坏性变更时，应配套发布清晰的变更说明，便于下游校验器和 IDE 集成有计划地升级。

## 许可证

本 schema 包基于 Apache License 2.0 开源。完整授权文本见 [LICENSE](LICENSE)。
