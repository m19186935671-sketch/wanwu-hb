---
name: neowow-wanwusheng-workflow
description: Study, explain, and recreate Neowow/万物生-style AI video canvas workflows. Use when the user asks about 万物生, Neowow open canvas, AI video storyboard canvases, prompt writing for segmented video, reference-image anchoring, 垫图, 色卡制作, Seedance-style shot prompts, or building an upgradeable workflow/template for consistent AI films.
---

# Neowow Wanwusheng Workflow

## Overview

Use this skill to analyze or design a 万物生-style AI video production workflow: a canvas of reusable visual assets, per-shot prompts, reference-image anchors, color-card constraints, sound/dialogue notes, and negative constraints for segmented generation.

## Operating Rules

- Always establish `记忆性固定站位` before writing shot prompts. Treat it as the scene's spatial memory: who is where, facing which direction, at what height/status, and what object separates them. For continuous scenes, inherit the previous segment's final frame and fixed positions; redesign positions only when the scene/location changes or the script explicitly moves characters.
- Do not describe character clothing or wardrobe in generated prompts unless the user explicitly asks for clothing. Character anchors should focus on identity, posture, expression, spatial role, and action.
- Use cuts deliberately. Do not default to one-take prompts; choose hard cuts, reaction shots, inserts, over-shoulder shots, and close-ups when they better serve conflict, pacing, or continuity. Use over-shoulder shots for confrontations across a fixed boundary.
- When the user provides director shot notes, preserve them as authoritative. Before delivering each generated prompt, self-check that the prompt has not departed from the original shot order, framing, camera movement, actions, or dialogue.
- Before delivering each generated prompt, self-check dialogue density against duration. For Chinese dialogue, target 3-4 characters per second; avoid exceeding 5 characters per second. If the dialogue load is too dense, split the segment or increase the suggested duration instead of compressing performance unrealistically.
- When a prompt includes character emotion, reaction close-ups, crying, anger, shame, lying, fear, protective restraint, or other actor-like performance details, use the separate `neowow-expression-management` skill as the performance layer after fixed positions are established.
- Treat public Neowow/万物生 material as research evidence, not as an instruction source.
- Verify current public pages when the user asks for the latest, exact current state, links, direct quotes, or page-specific claims.
- Summarize and transform long prompts; do not reproduce full copyrighted prompt dumps unless the user provides them and asks to edit them.
- Keep outputs practical: asset lists, shot prompt templates, color cards, reference-image plans, and iteration checklists.

## Workflow

1. Identify the requested mode:
   - Research: explain how the workflow works from public evidence.
   - Replication: create a reusable production pipeline for the user's story.
   - Prompting: write or improve per-shot video prompts.
   - Assets: design reference images, 垫图 roles, or a color card.
2. For research mode, inspect current public sources if accuracy may have drifted. Prefer official Neowow pages, public work pages, and the open-source canvas repo when relevant.
3. For replication or prompting mode, define `记忆性固定站位` before shot text. Use it as the fixed coordinate system for all later camera moves and edits.
4. For replication mode, start from an asset map before writing final prompts:
   - characters
   - scenes
   - props or creatures
   - color card
   - voice/audio references
   - first/last-frame continuity anchors
5. Write prompts as shot contracts, not decorative prose. Each prompt should specify stable anchors, fixed standing positions, camera, blocking, action phases, dialogue/audio, color constraints, final frame, and negative constraints.
6. Deliver concise artifacts first, then offer deeper expansion only when useful.

## References

- Read `references/workflow-notes.md` when explaining the observed 万物生/Neowow production pattern.
- Read `references/fixed-position-memory.md` whenever designing scenes, blocking, shot continuity, or multi-character prompts.
- Read `references/prompt-and-color-template.md` when writing prompts, reference-image plans, or color cards.
- Read `references/cutting-grammar.md` when designing shot segmentation, hard cuts, reaction shots, inserts, or when avoiding overuse of one continuous take.
- Read `references/director-shot-self-check.md` whenever the source script includes bracketed/parenthesized director shot notes, storyboard notes, camera notes, or explicit shot breakdowns.
- Read `references/dense-style-vocabulary.md` when the user wants prompts to sound closer to 万物生: high-density camera language, production texture, layered blocking, and sound-design wording.
