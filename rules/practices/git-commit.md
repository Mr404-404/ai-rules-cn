# 提交信息规范

## 格式

采用 Conventional Commits，描述部分使用简体中文：

```text
<type>(<scope>): <一句话概述>

[可选的正文，说明动机与取舍]

[可选的脚注：BREAKING CHANGE / 关联 issue]
```

## type 取值

- `feat`：新功能
- `fix`：缺陷修复
- `docs`：仅文档变更
- `style`：不影响逻辑的格式调整
- `refactor`：不改变行为的重构
- `perf`：性能优化
- `test`：测试相关
- `chore`：构建、依赖、工具链等杂项

## 要求

- 概述不超过 50 字，使用祈使句（"添加""修复""移除"），结尾不加句号
- 概述说不清楚的动机与背景写在正文，正文解释"为什么改"，而不是复述 diff
- 破坏性变更必须在脚注标注 `BREAKING CHANGE:` 并说明迁移方式
- 一次提交只做一件事；不相关的改动拆成多个提交
- 禁止提交：调试用的 console.log / print、被注释掉的死代码、`.env` 等含密钥的文件

## 分支

- 分支命名：`feat/简述`、`fix/简述`、`chore/简述`
- 不直接向 main / master 提交，通过 Pull Request 合并（个人小项目可放宽）
