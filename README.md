# YLM 论文写作 Skills

[English](README.en.md) · [MIT 许可](LICENSE)

五个用于中英文学术文章的 Codex skill，分别处理语言、模板表达、论述结构和全文一致性，并提供一个按需协调这些任务的入口。适用于粘贴文本、LaTeX 片段和本地论文工程。

## 选择入口

| Skill | 使用场景 | 边界 |
| --- | --- | --- |
| `ylm-paper-language` | 语法、措辞、清晰度、句内顺序 | 不自行重组段落 |
| `ylm-paper-deai` | 空泛评价、机械连接、重复铺陈、正文中的回复口吻 | 不判断作者身份，不提供检测分数 |
| `ylm-paper-flow` | 段落功能、信息顺序、主张与证据衔接 | 不补造推理或证据；章节重排默认只建议 |
| `ylm-paper-check` | 术语、符号、跨章节主张、引用、交叉引用、编译 | 检查范围取决于提供的工程与材料 |
| `ylm-paper-polish` | 同时处理多项问题 | 按需读取前四个模块，不要求每次全跑 |

## 安装

推荐一次安装五个模块。在支持 `$skill-installer` 的 Codex 中输入：

```text
$skill-installer 从 https://github.com/ylimingtju/ylm-paper-skills 安装以下五个 skill，使用 v0.1.0 标签：
skills/ylm-paper-language
skills/ylm-paper-deai
skills/ylm-paper-flow
skills/ylm-paper-check
skills/ylm-paper-polish
```

四个专用模块可以分别安装。综合入口会按任务需要查找其他模块；缺少模块时应说明未覆盖部分，不将其当作已完成。同一套模块需安装在同级目录。已有同名 skill 时先比较版本，不覆盖已有修改。

也可将选定目录复制到宿主支持的 skill 位置；Codex 的项目位置为 `.agents/skills/`，用户位置为 `~/.agents/skills/`。保留每个 skill 内的 `SKILL.md`、`agents/` 和 `references/`。发现不到新 skill 时重启 Codex。安装位置与发现规则参见 [OpenAI 官方说明](https://learn.chatgpt.com/docs/build-skills)。

## 使用

```text
$ylm-paper-language 只润色下面的英文段落。先给诊断和代表性改法，不改文件。

$ylm-paper-deai 检查 main.tex 引言的模板表达，只给建议，保留技术术语。

$ylm-paper-flow 检查方法介绍的信息顺序。先给段落调整方案，不调整章节。

$ylm-paper-check 检查这份 LaTeX 工程的术语、符号、引用和编译，报告已覆盖与未覆盖范围。

$ylm-paper-polish 综合润色 main.tex。先给诊断和修改方案，确认后再编辑。
```

英文请求示例及自编 LaTeX 示例见 [示例与行为检查](examples/README.md)。示例中的数值均为演示材料，不代表研究结果。

默认先给诊断和方案，获得一次确认后编辑；当次明确授权直接修改或已批准相同范围时沿用授权。“只审查”不写源文件。科学含义不清的内容保留并标注，不由模型自行选择正确结论。

## 依赖与限制

- 文本审查不需要 Python 包、API 密钥或指定期刊模板；运行依赖宿主模型和文件工具。
- LaTeX 编译需要论文工程已有的 TeX 引擎、宏包、字体和构建工具。优先原有构建方式；未编译应明确报告，缺依赖不等于源码错误。
- 支持中英文输入；skill 指令正文和界面元数据目前为中文。英文 README 不代表另有一套英文规则。
- 独立回归复查仅在宿主支持且任务允许委派时使用；没有委派能力时顺序完成并说明限制。外层系统及用户的授权约束始终优先。
- 保留公式、符号、标签、引用键、数值、适用条件和结论强度。涉及科学内容的修改需要单独说明与授权。
- 不补造文献或实验，不保证通过任何 AI 检测，不把编译或一致性检查当作数学证明核验；未读外部文献时不声称已验证引文支持关系。

## 目录与维护

每个模块位于 `skills/` 下，包含 `SKILL.md`、界面元数据和必要参考文件。`examples/` 提供自编输入、修订示例及检查场景。

本仓库的首发标签为 `v0.1.0`，各 skill 保留原有内部版本。问题反馈请附 skill 名称、最小匿名输入、期望行为和实际行为；提交前去除未公开论文内容与个人信息。

作者：[Liming Yang](https://github.com/ylimingtju)。本项目为个人工作流；[MIT 许可](LICENSE)。
