# MCP 常见错误与解决方法

## 1 安全策略阻断错误 403 Invocation is blocked on safety
此错误表示当前操作因安全策略被阻断。常见于尝试对 private 仓库执行写入操作。

解决方式：在 public 仓库中执行写入，或让模型输出内容后人工复制到 private 仓库。

## 2 无权限错误 403 Resource not accessible by integration
通常在尝试创建 GitHub 仓库时出现。GitHub Connector 没有创建仓库的权限。

## 3 分支已存在错误 422 Reference already exists
说明要创建的分支已经存在。可以改名或直接使用已有分支。

## 4 JSON 格式错误或控制字符错误
内容中包含未转义的特殊字符或过复杂结构可能导致工具调用失败。建议使用纯文本形式或拆分写入。