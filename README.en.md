# TideStack Metadata Schema

JSON Schema definitions for TideStack/Ouroboros metadata resources.

This directory is a standalone schema bundle for developers, validators, IDE integrations, and build tools that need a stable contract for metadata JSON files.

Chinese version: [README.md](README.md)

## Contents

- `*.schema.json`: JSON Schema Draft 2020-12 definitions for each metadata type.
- `index.json`: machine-readable catalog with metadata type, display name, file suffix, schema file, and path.
- `LICENSE`: Apache License 2.0 for this schema bundle.

## Usage

Pick the schema that matches a metadata file's suffix, then validate the JSON with any Draft 2020-12 compatible JSON Schema validator.

For example, a file ending in `.ui-model.json` is validated with `ui-model.schema.json`.

```bash
npx ajv-cli validate --spec=draft2020 -s ui-model.schema.json -d path/to/example.ui-model.json
```

Consumers that need to discover schemas dynamically should read `index.json` instead of hardcoding the table below.

## Schema Catalog

| Type | Description | File Suffix | Schema |
| --- | --- | --- | --- |
| `authority` | Authority item model | `.authority.json` | `authority.schema.json` |
| `menu` | Menu model | `.menu.json` | `menu.schema.json` |
| `dev-menu` | Developer menu model | `.dev-menu.json` | `dev-menu.schema.json` |
| `ui-model` | UI model | `.ui-model.json` | `ui-model.schema.json` |
| `ui-schema` | UI schema | `.ui-schema.json` | `ui-schema.schema.json` |
| `business` | Business model | `.business.json` | `business.schema.json` |
| `logicflow` | Logic flow model | `.logicflow.json` | `logicflow.schema.json` |
| `approval-workflow` | Approval workflow | `.workflow.json` | `approval-workflow.schema.json` |
| `field-type` | Field type | `.field-type.json` | `field-type.schema.json` |
| `flow-node` | Logic flow node | `.flow-node.json` | `flow-node.schema.json` |
| `widget` | Widget definition | `.widget.json` | `widget.schema.json` |
| `micro-web` | Micro frontend | `.micro-web.json` | `micro-web.schema.json` |
| `rpc` | RPC model | `.rpc.json` | `rpc.schema.json` |
| `rpc-auth` | RPC authentication | `.rpc.auth.json` | `rpc-auth.schema.json` |
| `webapi` | Web API model | `.webapi.json` | `webapi.schema.json` |
| `notification` | Notification template | `.notification.json` | `notification.schema.json` |
| `business-log` | Business log template | `.business-log.json` | `business-log.schema.json` |
| `data-init` | Data initialization | `.data-init.json` | `data-init.schema.json` |
| `mq` | Message queue binding | `.mq.json` | `mq.schema.json` |
| `schedule` | Scheduled task | `.schedule.json` | `schedule.schema.json` |
| `i18n` | Internationalization language pack | `.i18n.json` | `i18n.schema.json` |
| `data-dict` | Data dictionary | `.dict.json` | `data-dict.schema.json` |
| `position` | Position definition | `.position.json` | `position.schema.json` |
| `error-code` | Error code | No fixed suffix | `error-code.schema.json` |
| `app-metadata` | Application metadata | No fixed suffix | `app-metadata.schema.json` |
| `modules-diff` | Module tree diff | No fixed suffix | `modules-diff.schema.json` |
| `app-module` | Application module | No fixed suffix | `app-module.schema.json` |
| `configuration` | Configuration | No fixed suffix | `configuration.schema.json` |
| `configuration-group` | Configuration group | No fixed suffix | `configuration-group.schema.json` |
| `configuration-item` | Configuration item | `.config.json` | `configuration-item.schema.json` |
| `configuration-group-item` | Configuration group item | `.config-group.json` | `configuration-group-item.schema.json` |

## Versioning

The schemas describe the current public metadata contract. When a schema changes in a breaking way, publish it with a clear release note so downstream validators and IDE integrations can update deliberately.

## License

This schema bundle is licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for the full license text.
