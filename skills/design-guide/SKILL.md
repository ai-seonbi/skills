---
name: design-guide
description: >
  Guides a person through an AI-assisted design task when they need to research references,
  compare design directions, choose one, refine it, and record reusable criteria. It does not
  choose a visual direction for the person or claim support for a particular AI product.
---

# AI-Assisted Design Guide

Use this skill when the design direction is still open, or when several options need to be compared, refined, and reused against consistent criteria. It does not assume a particular app, command, or file location. Do not use it for one-off image generation, straightforward implementation of an already finalized screen, or automated aesthetic judgment that replaces a person's choice.

## Boundaries

- A person chooses the direction. Record their reason exactly when they provide one; otherwise record `Reason not provided`. An AI recommendation is input to the choice, not the choice itself.
- Research only publicly accessible sources. Do not bypass sign-in, reuse sessions, or evade access restrictions.
- By default, record only links to references and interpretations of them. Before saving or redistributing images or screenshots, verify the terms of use and license.
- Do not modify files, product interfaces, or external services outside the scope the user asked you to write to.
- Do not present examples, drafts, or reconstructions as actual user choices or execution results.

## Workflow

1. At the start, open [starter-brief.md](references/starter-brief.md) and fill in what is already known. Ask the necessary questions together only when the decision to make or the intended audience is unclear.
2. If existing deliverables, style rules, or approved decision records are available, read them first and extract the constraints that must be preserved. When researching, follow [process.md](references/process.md) and separate observations, elements to adopt, elements to avoid, and application hypotheses for every reference.
3. If no direction has been chosen yet, narrow the comparison to one differentiating axis and propose two or three options using the same content. When file creation and browser inspection are available, create a self-contained HTML comparison with no external dependencies and show all options in one view. Otherwise, provide comparison prompts and a manual review sequence, and report that rendering could not be verified.
4. For a small refinement to an already chosen direction, do not force new alternatives. Separate what to preserve from what to change, and make the before and after versions comparable side by side. If you can create HTML, inspect it visually in a browser before delivery.
5. Record the option the person chose and their reason in [decision-record.md](references/decision-record.md). If they gave no reason, write `Reason not provided`, and do not mix it with the AI's interpretation. Open [request-examples.md](references/request-examples.md) for sample request wording.
6. Before presenting the result, perform the visual review in [qa-recovery.md](references/qa-recovery.md). Reuse only approved records as input to the next task.

## Pre-completion checks

- Facts from references are separated from my interpretation.
- When a new direction was chosen, at least two options were offered and the person's choice was recorded. Do not reapply this condition to a small refinement of an existing choice.
- Record a person's reason only when they provide one; otherwise use `Reason not provided`.
- The scope of the refinement and the elements to preserve are clear.
- Typography, contrast, clipping, and overlap have been checked on both small and large screens.
- If HTML was created in an environment with file and browser access, it has been inspected visually in an actual browser. If that environment was unavailable, the lack of rendering verification has been reported.
- Criteria passed to the next task were extracted only from an approved choice.

## Failure signals and responses

| Signal | Response |
| --- | --- |
| Attempting to reproduce a single reference directly | Abstract its characteristics, retain only the link and interpretation, and propose a new design using the new content and constraints. |
| Treating an AI recommendation as a person's decision | Split the record into `AI proposal` and `Person-confirmed choice`, then ask for the reason behind the choice. |
| Offering one option and applying it immediately | First create at least one alternative using the same content. |
| Forcing multiple alternatives for a small refinement to an existing choice | Present only the preserved and changed elements and a before-and-after comparison. |
| Providing only a text description when file and browser access are available | Create a self-contained HTML comparison with no external dependencies and inspect it in an actual browser. |
| Claiming rendering was verified without file or browser access | Provide comparison prompts and a manual review sequence, and report that rendering was not verified. |
| Producing options that are hard to read or contain overlapping elements | Continue the review and follow the cause-specific repair sequence in [qa-recovery.md](references/qa-recovery.md). |
| The deliverable, audience, or constraints are unspecified | Do not make plausible-sounding assumptions; resolve the empty fields in the starter brief first. |
| The license or access permission is unclear | Do not save or redistribute the asset; record only the link and observation. |

## Termination conditions

- Success: the person's choice and either their stated reason or `Reason not provided` are recorded, along with the comparison, refinement, visual-review results, and criteria for the next task.
- Abstain: the essential brief, choice, permissions, or license cannot be confirmed, so a reliable result cannot be produced.
- Escalate: ask the person to decide when a new request conflicts with approved criteria or when the authorized decision-maker defers the choice.
