# YLM Paper Writing Skills

[简体中文](README.md) · [MIT license](LICENSE)

Five Codex skills for Chinese and English academic writing: language editing, removal of formulaic wording, argument organization, manuscript consistency checks, and a coordinator that selects the relevant tasks. Inputs may be pasted text, LaTeX fragments, or local manuscript projects.

## Choose a skill

| Skill | Use it for | Boundary |
| --- | --- | --- |
| `ylm-paper-language` | Grammar, wording, clarity, sentence structure | Does not reorganize paragraphs on its own |
| `ylm-paper-deai` | Empty praise, mechanical transitions, repeated framing, reply-style prose in a manuscript | Does not identify authorship or assign detection scores |
| `ylm-paper-flow` | Paragraph roles, information order, links between claims and evidence | Does not invent reasoning or evidence; section reordering is a suggestion by default |
| `ylm-paper-check` | Terms, notation, claims across sections, citations, cross-references, compilation | Coverage depends on the project and sources provided |
| `ylm-paper-polish` | Requests that need several of these tasks | Reads selected modules; does not run every module for every request |

## Install

Install all five modules together. In Codex with `$skill-installer`, enter:

```text
$skill-installer Install these five skills from https://github.com/ylimingtju/ylm-paper-skills at tag v0.1.0:
skills/ylm-paper-language
skills/ylm-paper-deai
skills/ylm-paper-flow
skills/ylm-paper-check
skills/ylm-paper-polish
```

The four specialist skills also work separately. The coordinator looks for the modules needed by the request. When a module is missing, it must report the missing coverage. Install the modules as sibling directories. If a skill with the same name already exists, compare versions before replacing local changes.

You may also copy selected directories into a skill location supported by your host. Codex uses `.agents/skills/` for a project and `~/.agents/skills/` for a user. Keep each skill's `SKILL.md`, `agents/`, and `references/` together. Restart Codex if the new skills do not appear. See the [official OpenAI instructions](https://learn.chatgpt.com/docs/build-skills) for discovery rules.

## Use

```text
$ylm-paper-language Review the English paragraph below. Give a diagnosis and representative edits first; do not edit files.

$ylm-paper-deai Review formulaic wording in the introduction of main.tex. Suggest edits only and preserve technical terms.

$ylm-paper-flow Review the information order in the method section. Propose paragraph changes without reordering sections.

$ylm-paper-check Check this LaTeX project's terms, notation, citations, and compilation. State what you could and could not check.

$ylm-paper-polish Edit main.tex for language, wording, organization, and consistency. Give a diagnosis and plan before editing files.
```

See [examples and behavior checks](examples/README.md) for synthetic LaTeX inputs and English requests. All numbers in the examples are illustrative and are not research results.

The default is a diagnosis and plan followed by one approval before editing. An explicit request to edit directly, or existing approval for the same scope, remains valid. Review-only requests must not edit source files. Keep scientifically ambiguous statements and flag them rather than selecting a conclusion on the author's behalf.

## Requirements and limits

- Text review needs no Python packages, API keys, or journal template. It uses the host model and file tools.
- Compilation requires the manuscript's existing TeX engine, packages, fonts, and build tools. Use the existing build method. State when compilation was not run; a missing dependency is not a source-code error.
- Chinese and English inputs are supported. Skill instructions and UI metadata are currently in Chinese; this English README does not define a second rule set.
- An independent regression reviewer is used only when the host supports delegation and the task permits it. Otherwise, run sequentially and state that limitation. Host and user authorization rules take priority.
- Preserve formulas, notation, labels, citation keys, values, conditions, and claim strength. Changes to scientific content need a separate explanation and authorization.
- Do not invent sources or experiments, promise detector outcomes, or treat compilation and consistency checks as proof verification. Do not claim that citation support was verified without reading the external sources.

## Layout and maintenance

Each directory under `skills/` contains instructions, UI metadata, and any needed references. `examples/` contains synthetic inputs, edited examples, and review scenarios.

The initial repository tag is `v0.1.0`. Existing version numbers inside individual skills are preserved. For an issue, include the skill name, a small anonymized input, expected behavior, and observed behavior. Remove unpublished manuscript text and personal information before posting.

Author: [Liming Yang](https://github.com/ylimingtju). A personal workflow project, released under the [MIT license](LICENSE).
