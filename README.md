<div align="center">

# ai-rules-cn

**开箱即用的中文 AI 编程规则库**

让 AI 编程助手说中文、懂规范、不乱改你的代码

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/Mr404-404/ai-rules-cn/pulls)

</div>

---

## 这是什么

一套可直接复制到项目里的**中文 AI 编程规则文件**，适配主流 AI 编程工具：

- **AGENTS.md** —— Antigravity、Kimi Code、Codex 等支持 AGENTS.md 的工具
- **CLAUDE.md** —— Claude Code
- **.cursorrules** —— Cursor

没有规则文件的 AI 助手常见毛病：默认英文回复、注释啰嗦、擅自重构无关代码、提交信息随心所欲。把规则文件放进项目根目录，AI 就会在每次会话中自动遵守其中的约定。

## 快速开始

**方式一：直接使用通用模板（推荐）**

把 `templates/AGENTS.md` 复制到你的项目根目录，按项目情况删改即可：

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/Mr404-404/ai-rules-cn/main/templates/AGENTS.md
```

**方式二：按需组合规则模块**

从 `rules/` 目录挑选你需要的规则文件，把内容合并进项目的 `AGENTS.md`（或 `CLAUDE.md` / `.cursorrules`）：

```text
rules/
├── general/            # 通用规则
│   └── chinese-response.md       # 中文回复与表达规范
├── languages/          # 语言规范
│   ├── python.md                 # Python 编码规范
│   └── javascript-typescript.md  # JS/TS 编码规范
├── frameworks/         # 框架规范
│   └── react.md                  # React 开发规范
└── practices/          # 工程实践
    ├── git-commit.md             # 提交信息规范
    ├── code-review.md            # AI 代码审查清单
    ├── security.md               # 安全红线
    └── testing.md                # 测试规范
```

**方式三：Cursor / Claude Code 专用模板**

`templates/` 下提供了 `.cursorrules` 与 `CLAUDE.md` 的对应版本，复制到项目根目录即可。

## 编写原则

本规则库遵循三条原则，也是你自行扩展时应保持的：

1. **可执行**：每条规则都是 AI 能直接遵守的具体行为，不写"写出好代码"这种空话
2. **有边界**：明确告诉 AI 什么不许做（不擅自重构、不动无关文件），比告诉它做什么更重要
3. **少即是多**：规则总量控制在 AI 上下文能稳定遵守的范围内，单个文件不超过 80 行

## 贡献

欢迎提交 PR 补充新的规则模块（新语言、新框架、新场景），或改进现有规则的表述。
提交前请确认：规则是具体可执行的、与现有模块不重复、中文表述自然。

## License

[MIT](LICENSE) © Mr404-404
