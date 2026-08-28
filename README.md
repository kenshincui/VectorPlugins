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
| Impeccable | 高审美网站、产品界面设计、重构、评审和质量检查 | Node.js；浏览器能力按任务使用 |
| PPT Master | 高质量原生可编辑 PPTX、模板、动画、旁白和视觉 QA | Python 3.10+；按需安装 `requirements.txt`；推荐 LibreOffice |
| Doc Co-authoring | 共同撰写 PRD、RFC、技术方案、提案和决策文档 | 无强制外部依赖 |
| Internal Comms | 周报、向上汇报、3P、项目进展和内部公告 | 无强制外部依赖 |
| Diagram Maker | 架构图、流程图、SVG/HTML 与 Excalidraw 白板 | 浏览器用于预览验证 |
| Deep Research | 来源治理、证据映射、反向审查和引用校验 | 需要可用的搜索、浏览器或连接器能力 |
| Frontend Design | 为网站、Dashboard 和产品界面建立鲜明、非模板化的视觉方向并完成实现 | 无强制外部依赖；推荐浏览器截图能力 |
| Frontend Slides | 创建、转换、优化和导出单文件动画 HTML 演示文稿 | Python 3 用于 PPTX 提取；PDF 导出与部署按需使用对应脚本依赖 |

## 目录约定

```text
.agents/plugins/marketplace.json
plugins/<plugin-name>/.codex-plugin/plugin.json
plugins/<plugin-name>/skills/<skill-name>/SKILL.md
```

插件必须使用 MIT 或其他明确允许再分发的许可证。不得提交凭据、Cookie、访问令牌、用户数据或来源不明的第三方代码。安装插件不等于授予外部服务权限；涉及账号或写操作时仍需由对应工具完成认证并遵循 Vector 的审批策略。

第三方 Skill 的来源、固定版本和 Vector 适配说明记录在
[`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md) 以及各插件的
`UPSTREAM.md` 中。PPT Master 的 Vector 包为满足安装大小和文件数限制，
精简了可替代的图标与音效素材库，但保留完整核心工作流、脚本、模板和参考资料。

Anthropic 的 `docx`、`xlsx` 和 `pdf` Skill 属于 source-available
材料，其许可证明确禁止复制、创建衍生作品和向第三方分发，因此本仓库不收录。
Vector 已有可再分发的 Office/PDF 插件；如需使用 Anthropic 原版，应通过
Anthropic 官方服务和其适用协议使用。

## 本地验证

```bash
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/plugin-creator/scripts/validate_plugin.py" plugins/<plugin-name>
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py" plugins/<plugin-name>/skills/<skill-name>
```

## 贡献

新增插件时同步更新 marketplace，保持目录名、manifest 的 `name` 和 marketplace 条目一致。Skill 应描述真实可执行的工作流、依赖检查、失败边界和结果验证；不要只提供提示词合集。
