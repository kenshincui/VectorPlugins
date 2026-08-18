# Vector Community Plugins

面向 Vector 的社区插件目录，兼容 Codex 插件目录结构。仓库中的插件以 Skills 为主，可由 Vector 自有插件管理器安装，不要求用户安装 Codex CLI。

## 首批插件

| 插件 | 能力 | 主要依赖 |
| --- | --- | --- |
| 飞书 Skills | 文档、云盘、Wiki、多维表格、表格、日历、消息等飞书操作 | `lark-cli` 与用户授权 |
| Office Skills | 创建、读取和转换 DOCX/XLSX 等办公文件 | Python 3；推荐 LibreOffice |
| PPT Skills | 创建、修改、渲染和检查 `.pptx` | Python 3；推荐 `python-pptx` 与 LibreOffice |
| 中文 OCR | 提取图片或扫描件中的中文文本与表格 | PaddleOCR、Tesseract 或可用 OCR 服务 |
| 会议纪要 Skills | 从转写稿整理决策、行动项、风险和待确认项 | 无强制外部依赖 |
| 思维导图 Skills | 生成 Mermaid mindmap/flowchart 和可编辑源文件 | 可选 Mermaid CLI |
| PDF 工具 Skills | 提取、OCR、合并、拆分、旋转和转换 PDF | Poppler、PyMuPDF、pypdf 等按任务选择 |

## 目录约定

```text
.agents/plugins/marketplace.json
plugins/<plugin-name>/.codex-plugin/plugin.json
plugins/<plugin-name>/skills/<skill-name>/SKILL.md
```

插件必须使用 MIT 或其他明确允许再分发的许可证。不得提交凭据、Cookie、访问令牌、用户数据或来源不明的第三方代码。安装插件不等于授予外部服务权限；涉及账号或写操作时仍需由对应工具完成认证并遵循 Vector 的审批策略。

## 本地验证

```bash
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/plugin-creator/scripts/validate_plugin.py" plugins/<plugin-name>
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py" plugins/<plugin-name>/skills/<skill-name>
```

## 贡献

新增插件时同步更新 marketplace，保持目录名、manifest 的 `name` 和 marketplace 条目一致。Skill 应描述真实可执行的工作流、依赖检查、失败边界和结果验证；不要只提供提示词合集。
