# AI seonbi · Agent Skills

English · [한국어](README.ko.md)

This repository publishes and maintains reusable agent skills and installation and usage guides. The currently available skill is `design-guide`.

## Available skills

| Skill | Purpose | Guides |
| --- | --- | --- |
| [design-guide](skills/design-guide/SKILL.md) | Research design references, compare and refine options, and record criteria approved by a person | [Getting started (Korean)](guides/start-here.md) · [Request examples](skills/design-guide/references/request-examples.md) |

[Browse on skills.sh](https://skills.sh/ai-seonbi/skills) · [Versioned downloads and SHA-256 checksums](https://github.com/ai-seonbi/skills/releases)

## Languages and distribution versions

The default README and current skill instructions and references for skills.sh are in English. A [Korean README](README.ko.md) and existing Korean usage guides are also available. The terminal commands below install the English `design-guide` package from current `main`. The `v0.1.0` ZIP files are fixed releases that preserve the Korean instruction bodies distributed at that time.

## Using design-guide

If you have a visual direction in mind but find it hard to describe, ask AI to find design references and show several options using the same content. You review and choose; AI helps refine the result and record the criteria.

`design-guide` is a freely distributed skill that makes this workflow reusable.

[Official resource guide (Korean)](https://ai-seonbi.github.io/skills/design-guide/)

### Getting started

1. Choose the instructions for your AI tool in [Getting started (Korean)](guides/start-here.md).
2. For the historical Korean release, download the [complete resource ZIP](https://github.com/ai-seonbi/skills/releases/download/v0.1.0/ai-design-guide.zip), which includes the skill, guides, actual requests, and comparison images. For the current English skill, use the terminal commands below.
3. Start with the [request examples](skills/design-guide/references/request-examples.md). A [first-request template in Korean](guides/start-here.md#첫-작업-요청) is also available.

You can also [try the workflow in a conversation (Korean)](guides/try-in-chat.md) before installing. For the Claude app, use the historical Korean [skill-only ZIP](https://github.com/ai-seonbi/skills/releases/download/v0.1.0/design-guide-v0.1.0.zip). The getting-started guide states the support and verification limits for each app.

### Install from the terminal

Run the command for your tool from the project directory where you will work.

```sh
# Codex
npx skills add ai-seonbi/skills --skill design-guide --agent codex --copy

# Claude Code
npx skills add ai-seonbi/skills --skill design-guide --agent claude-code --copy
```

After installation, invoke `$design-guide` in Codex or `/design-guide` in Claude Code. If a skill with the same name already exists, compare it before overwriting. These commands use the external skills CLI; they do not upload a skill to an app.

### What does it do?

Research design references → compare options using the same content → let a person choose → refine while separating what to preserve from what to change → record approved criteria.

The [skill instructions](skills/design-guide/SKILL.md) and [comparison and refinement examples (Korean)](examples/README.md) are public. This is not a copy of the entire personal setup used during production, and it does not guarantee identical results. The examples distinguish actual production material from illustrative reconstructions.
