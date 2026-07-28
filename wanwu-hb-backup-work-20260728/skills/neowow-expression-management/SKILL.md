---
name: Neowow 之ai表情管理
description: Convert Wanwusheng/Neowow-style drama emotions into visible actor-like micro-expression prompts. Use when writing or improving AI video prompts that include character emotions, reaction close-ups, anger, grievance, fear, shame, smugness, protective restraint, lying, guilt, crying, confrontation, or any prompt where vague emotion words need to become controllable facial, gaze, breath, hand, and body details.
---

# Neowow 之ai表情管理

## Overview

Use this skill as the performance layer for Wanwusheng-style short-drama prompts. It turns abstract emotion labels into visible, filmable actor behavior without changing the user's story, dialogue, shot order, blocking, or wardrobe.

## Core Rules

- Do not let an emotion word carry the shot by itself. "Angry", "wronged", "sad", "nervous", or "smug" must be translated into visible cues.
- Build expression from: mouth state, gaze direction, brow/eye movement, face tension, breath rhythm, hand action, body posture, and sightline.
- Avoid single-symbol shortcuts. Do not use "face turns red" as the main way to show anger or grievance.
- Match detail to shot size. Close-ups can hold 2-3 micro cues; medium shots should prioritize posture, hands, shoulders, and sightline; wide shots should use blocking and body attitude.
- Preserve the director's camera notes and the exact dialogue. Add performance detail only where it supports the given shot.
- Do not add actions that change fixed positions unless the script explicitly says the character moves.
- Prefer a before-to-after transition when emotion changes: "smile holds half a beat, then mouth flattens and eyes harden" is better than "suddenly angry".
- Keep performance playable by a real actor. Avoid exaggerated cartoon faces, extreme crying, theatrical overacting, or generic "cinematic emotion".

## Expression Formula

Use this compact pattern inside shot descriptions:

```text
{emotion label only if helpful}: {mouth state}; {gaze direction/change}; {brow/eye detail}; {breath or face tension}; {hand/body cue if visible}.
```

Example:

```text
委屈但忍住：嘴角轻轻下压，视线短暂躲开又抬回去，眼皮微颤，呼吸卡住一拍，手指抓紧身边人的衣角。
```

## Common Drama States

Use these as starting points and adapt them to the character, shot size, and power relationship.

- 委屈: mouth corners press down slightly; eyes moisten or hold focus too long; eyelids tremble; breath catches; shoulders draw inward.
- 生气: mouth flattens or tightens; gaze locks on the target; brow compresses; jaw tightens; shoulders and neck become rigid.
- 压怒: lips press into a line; eyes stay steady; jaw muscle holds; breath pauses before speaking; hands stay controlled instead of flailing.
- 害怕: mouth parts slightly; eyes widen but do not settle; brow lifts or pinches; body leans back or shrinks; hands seek a protector or object.
- 紧张: lips press or briefly wet; gaze flicks away and returns; brow tightens; fingers rub, grip, or hover; shoulders rise.
- 心虚/撒谎: gaze checks the listener before finishing the line; blink rate changes; mouth shape overworks the excuse; hand touches a nearby object or body edge.
- 得意: mouth corner lifts very slightly; eyes glance sideways; chin raises a fraction; body relaxes into the higher-status position.
- 嫌弃: upper lip lifts or mouth pulls to one side; eyes narrow or look sideways; nose bridge tightens; body angles away.
- 恼羞成怒: face freezes for a beat; eyes dodge, then snap back; brow drops; voice pressure rises; hand points or cuts the air.
- 护短: body shifts between the accused person and the accuser; eyes harden; hand stays on the protected person; speech becomes clipped.
- 保护性克制: torso angles toward the protected person; one hand steadies them; gaze stays on the threat; mouth stays closed before a controlled line.
- 崩溃前忍哭: mouth opens then closes; lower lip or eyelid trembles; breath becomes shallow; gaze loses focus; shoulders fold inward.
- 冷漠/决裂: mouth is flat; gaze does not chase approval; chin steadies; movements slow down; silence lands before the line.

## Writing Workflow

1. Identify the true beat: accusation, humiliation, fear, defense, lie, guilt, contempt, collapse, or reversal.
2. Choose only the cues visible in the shot size.
3. Tie gaze to the scene map: who looks at whom, who avoids whom, and which object carries the conflict.
4. Add one hand/body cue only when it clarifies the emotion or relationship.
5. Check the result: if the prompt could still be replaced by one abstract emotion word, rewrite it with concrete visible behavior.

## Negative Constraints

Add concrete negatives when the model tends to overact or misunderstand:

```text
NOT 只用脸红表达情绪; NOT 夸张哭喊; NOT 卡通表情; NOT 表演过火; NOT 情绪和台词不匹配; NOT 眼神方向错乱; NOT 反应特写里加入新动作; NOT 因表情动作改变固定站位。
```
