# MCP 使用方法总结

本文件整理了今日调试中确认的 GitHub MCP（Model Context Protocol）能力与限制。

## 1. 公有仓库可写入
- 成功通过 push_files 创建测试文件。
- 说明 MCP 可以在 public repo 中正常执行写入操作。

## 2. 私有仓库写入被阻断
- 对私有仓库执行 create_or_update_file / push_files 会触发安全策略阻断。
- 返回错误：403 Invocation is blocked on safety。

## 3. 无法通过 MCP 创建新仓库
- GitHub 返回：403 Resource not accessible by integration。
- 说明连接器没有 repo 创建权限。

## 4. 最佳实践
- 在 public repo 中测试自动写入功能。
- 私有仓库内容建议由用户手动粘贴更新。

## 5. 后续可测试内容
- 自动生成文档并 push。
- 自动创建 PR。
- 自动生成代码示例。