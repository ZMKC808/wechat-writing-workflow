# 公众号工作区 Agent 规则

## 基本原则

- 先读 [[Home]]、[[WORKFLOW.md]] 和 [[系统/写作流程]]。
- Ob 只放内容资产、项目稿件、复盘和 SOP。工具源码、虚拟环境等不进 Ob，详见 [[系统/工具索引]]。
- 不直接改写 `资料库/语料库/` 里的原文。历史文章只做学习参考和风格模仿。
- 公众号链接要实际读取，不能凭印象总结。
- 不确定资料、口径、语气或账号定位时，先列出具体问题问用户。
- 模型发布类文章不要单独写「我的判断」段落，判断要融合到正文结构里。

## Cline 分工

本机可通过终端命令 `cline` 调用 Cline CLI（省 token，适合简单任务）。

适合交给 Cline 的任务：

- 统计文件数量、字数、目录结构
- 搬运、归档、生成索引
- 跑格式检查、简单脚本、依赖安装验证
- 对大量文件做机械性扫描

不交给 Cline 的任务：

- 选题判断
- 文章观点和结构
- 标题方向
- 正文写作
- 最终质量把关

推荐调用格式：

```bash
cline --cwd /Users/zmkc808/Documents/Zoey知识库/公众号 --json --timeout 120 "执行一个明确、低风险、可验证的小任务。不要改写正文，不要做选题判断。完成后只汇报结果和修改过的文件。"
```

原则：Cline 是执行助手，不是主笔。规划、判断、写作和最终验收仍由 Codex 完成。

## 写作流程

详细步骤见 [[WORKFLOW.md]]，核心顺序：

1. 链接/截图/热点 → 调研（`wechat-article-to-markdown` / `agent-reach`）
2. 在 `文章/` 新建项目，写 `文章.md`（参考风格手册）
3. `dbs-content` 诊断 + `dbs-ai-check` 检测
4. 配图（优先截图，其次 `ian-xiaohei-illustrations`）
5. 输出 `发布版.md` + 图片
6. 发布后读阅读数，更新 `复盘/`

## 本机工具环境规则

工具索引见：

[[系统/工具索引]]

安装和调用规则：

- Python CLI 优先用 `uv tool install <tool>`。
- Node CLI 优先用 `npm install -g <tool>`，npm prefix 应为 `/Users/zmkc808/.npm-global`。
- macOS 系统工具优先用 `brew install <tool>`。
- Agent Reach 平台后端优先用 `agent-reach install --env local --channels <channel>`。
- 不把专用 venv 整体加入 PATH，只把明确命令软链接到 `~/.local/bin`。
- 新增长期服务必须提供 health 检查命令和文档。
- 环境异常先跑 `agent-tools-doctor`，不要先重装。
