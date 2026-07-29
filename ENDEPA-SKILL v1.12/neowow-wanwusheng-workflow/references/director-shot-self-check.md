# Director Shot Self-Check

Use this reference whenever the user provides explicit director shot notes, such as bracketed or parenthesized camera instructions, shot sizes, movement, angles, or storyboard beats. These notes are authoritative.

## Priority Rule

Do not creatively redesign a director-shot passage. Preserve:

- shot order
- shot size: close-up, medium, wide, insert, POV, high angle, low angle
- camera movement: pan, shift, push, fixed, orbit, handheld, tracking
- camera position and angle
- action beat timing
- object/action inserts
- dialogue exactly as written
- required silence or pauses

Only add supportive details that do not alter the shot: texture, light, sound, continuity, fixed positions, reference anchors, and negative constraints.

If a rule conflicts with explicit director shot notes, use this priority:

1. 剧本原文、台词、动作和剧情顺序
2. 用户给出的导演分镜、括号机位、景别、角度、△动作
3. 已确认视频末帧、固定站位、人物背后背景和道具连续性
4. 台词语速与单段时长限制
5. 30 度风险、镜头丰富度、画面美感和其他优化

Do not force 30-degree variation or a more "cinematic" angle when it changes the director note. If the director note may create a cross-segment jump cut, keep the shot's core function and adjust only supportive variables such as shot scale, foreground layer, insert/reaction bridge, camera height, or opening object detail.

## When No Director Notes Exist

Do not create a separate director-shot sub-skill until the user provides enough director-shot material to build one. For now, infer shots from story function:

- power shift: hard cut or low/high angle contrast
- wounded line: reaction close-up
- important object: insert shot
- action beat: medium shot or action detail
- spatial confusion risk: re-establishing wide
- emotional turn: close-up with actor-like micro-expression
- public pressure or crowd reaction: cutaway/reaction shot

## Required Self-Check Before Final Answer

Before delivering the prompt, compare it against the source shot notes:

1. Did every original shot note appear in the same order?
2. Did I add any camera angle or movement not requested?
3. Did I remove or weaken any required close-up, insert, POV, high-angle, low-angle, or fixed shot?
4. Did I preserve all actions and object beats?
5. Did I preserve all dialogue exactly, with no rewrites?
6. Did I avoid generating subtitles when the script only includes subtitle metadata?
7. Did I check Chinese dialogue density against duration, targeting 3-4 characters per second and avoiding more than 5 characters per second?
8. Did I avoid clothing descriptions unless explicitly requested?
9. Does the segment end on a frame that cuts cleanly into the next segment?

If any answer fails, revise before responding.

## Optional Output Note

When useful, add a short note after the prompt:

```text
自检：已按原分镜顺序保留镜头；未改台词；未新增会改变导演意图的镜头；末帧可接下一段。
```
