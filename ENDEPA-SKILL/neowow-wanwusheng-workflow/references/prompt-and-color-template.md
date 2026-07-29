# Prompt And Color Templates

## Pre-Prompt Content Fact Lock

Before writing the user-facing prompt, silently extract the current segment facts from the script. Do not show this block unless the user asks to inspect it.

```text
[内容事实锁定 - 内部自检，不默认输出]
场景：{场景名 / 日夜 / 内外}
本段人物：{只写本段实际出场人物}
本段起点：{从哪句台词/哪个△动作开始}
本段终点：{到哪句台词/哪个△动作为止}
核心动作：{本段必须发生的动作，按剧本顺序}
核心道具：{本段出现并有叙事作用的道具}
人物状态：{谁站/坐/蹲/倒下/扶着谁/看向谁}
原文台词：{逐字列出本段要进入提示词的台词}
```

Write the final prompt only from these facts. Do not add absent characters, future props, future actions, or off-script plot.

## STYLE LOCK Generation Rule

Keep the structure of `STYLE LOCK` stable, but generate its content from the current script. Do not mechanically reuse a family living-room, warm-gray, or any previous scene style for unrelated scenes.

Required fields:

- 镜头质感: choose from the current genre and situation, such as family realism, medical realism, urban night realism, tense handheld realism, or restrained office realism.
- 色彩方向: derive from scene emotion and location; do not default to one palette.
- 光线来源: use plausible sources from the scene, such as window daylight, corridor light, desk lamp, practical light, street light, vehicle interior light.
- 场景空间: match the current script location exactly.
- 画幅: default to 2.39:1 unless the user requests otherwise.
- 音轨: only include plausible ambient sound, action sound, prop sound, and dialogue.
- 禁止项: no subtitles, no BGM, no watermark.

## Segment Decision Tree

Use this order before writing shot text:

1. If the user works one segment at a time, output only the next segment.
2. If using Seedance 2.0 / 万物生, keep each segment at 15 seconds or less; split instead of compressing performance.
3. If director shot notes exist, preserve their order, shot scale, angle, action, and dialogue.
4. If no director shot notes exist, infer shots from story function: space setup, line impact, reaction, action beat, prop reveal, spatial reset, or emotional turn.
5. If a key prop appears, give it an insert shot or final-frame anchor.
6. If the beat has pain, shame, lying, anger, suppressed emotion, silence, or crying, include a reaction close-up with actor-like visible cues.
7. If blocking is complex or more than two characters confront each other, establish space before close-ups.
8. If the next segment opening would match the previous final frame with the same subject, shot scale, and angle, change the opening shot function.

## Segment Prompt Template

Use this as the user-facing prompt shell. Fill the fields from the current
segment's content fact lock; do not expose template instructions or alternate
formats in the final prompt.

```text
【[STYLE LOCK]
{根据当前剧本生成的现实主义影像风格}，{根据当前场景生成的色彩方向}，{画面质感}，{当前场景成立的真实光线来源}。{当前场景名称}空间，{当前场景中的空间锚点、人物位置、行动路线和前景遮挡关系；只有存在明确权力关系时，才补充高位、分界物和低位/弱势区域}。画幅 2.39:1，严格按照原剧本顺序和导演分镜执行，不额外改写镜头，不添加新剧情，不生成字幕，不配 BGM。

音轨：仅{当前场景环境音}、{本段动作声}、{关键道具声}、人声对白，不配 BGM。

[记忆性固定站位 - 最高优先级]
本段是{新场景第一段 / 严格承接上一段末帧}。

{空间锚点}位于{具体位置}，作为本段空间坐标基准。
{人物名}位于{具体位置}，面朝{方向}，保持{站立/坐着/蹲下/扶着谁/被谁遮挡}状态。
{人物名}位于{具体位置}，面朝{方向}，保持{姿态、动作和叙事功能}。
{人物名}位于{具体位置}，面朝{方向}，保持{姿态、动作和叙事功能}。
继续列出本段实际出场且需要定位的人物。
未在本段明确参与行动或开口的人物，只能作为背景存在；不得抢镜、不得提前行动、不得提前揭示后文信息。
{分界物/核心道具，如有}位于{具体位置}，作为{空间边界/动作触发点/叙事道具}。

除非剧本文字明确写出移动，人物不得换边、不得瞬移、不得改变前后关系，不得改变人物与空间锚点的相对位置。剧本明确写出移动时，必须按照动作顺序更新站位、镜头方向和人物背后背景。

[参考锚点]
仅添加本段实际出场且已有参考图的人物：
@[{人物名形象图}] 作为{人物名}身份、面部和表演状态锚定，控制{当前剧情中的可见表演反应}。
@[{人物名形象图}] 作为{人物名}身份、面部和表演状态锚定，控制{当前剧情中的可见表演反应}。
……

@[{场景图}] 作为空间锚定，锁定{场景布局、动线、关键物件、前景遮挡关系}。
@[{核心道具图，如有}] 作为道具锚定，控制{形状/材质/位置/叙事作用}。
@[{色卡图，如有}] 作为色彩锚定：{根据当前场景生成的8-13个颜色锚点}。

镜头一：
{景别、机位、构图和镜头功能}。{主体人物或主体道具}。{按照剧本原文发生的物理动作}。{人物可见的表演反应和空间关系}。
{如有台词：人物名}说：“{剧本原文台词}”台词必须一字不改。
{如无台词：只拍{剧本原文动作、反应或道具}，不新增台词。}

HARD CUT

镜头二：
{景别、机位、构图和镜头功能}。{主体人物或主体道具}。{按照剧本原文发生的物理动作}。{人物可见的表演反应和空间关系}。
{如有台词：人物名}说：“{剧本原文台词}”台词必须一字不改。
{如无台词：只拍{剧本原文动作、反应或道具}，不新增台词。}

HARD CUT

镜头三至镜头N：
继续按照剧本顺序和导演分镜生成。导演备注、括号动作、△动作必须完整保留。每个镜头必须交代景别、机位、主体、物理动作、可见表演反应和空间连续关系。长台词不得强行压缩；重要情绪、动作转折和关键道具需要单独镜头。连续正反打不强制每次改变30度，但不得出现无理由的相同构图跳切。如剧本明确连续跟随，保留连续运动；无剧本依据时不得强行一镜到底。

末帧：
{清楚交代本段最后画面中所有实际出场人物的位置、姿态、表演状态、关键道具和空间背景，并说明为下一段哪个动作或台词衔接。}

[负面约束]
NOT 改变剧本顺序；NOT 修改台词；NOT 添加新剧情；NOT 添加未出场人物；NOT 漏掉导演备注；NOT 漏掉括号动作；NOT 漏掉△动作；NOT 人物换边；NOT 越轴；NOT 人物瞬移；NOT 背景跳场；NOT 道具提前出现；NOT 主角提前完成后文动作；NOT 非主体人物抢镜；NOT 无理由一镜到底；NOT 生成字幕或屏幕文字；NOT 描述人物服饰；NOT BGM；无字幕；无水印。

视频时长：根据台词量、动作量和镜头数量生成，不超过当前模型版本上限；默认 Seedance 2.0 / 万物生最高 15 秒，超过则拆分为下一段。】
```

## Reference-Image Plan Template

```text
Character anchors:
- {character}: {image needed}, controls {identity/posture/expression/spatial role/silhouette}, not responsible for {color/clothing/background}.

Scene anchors:
- {location}: {image needed}, controls {layout/material/lighting}, not responsible for {character identity}.

Object anchors:
- {object/creature}: {image needed}, controls {shape/material/moving parts}.

Color anchors:
- {palette name}: {13-color card}, controls palette only.

Continuity anchors:
- {shot number}: first frame from {previous accepted clip}; last frame for {next clip}.
```

## 13-Color Card Template

Use a neutral dark or mid-gray background. Create 8-13 swatches. Label each swatch with hex and semantic purpose.

```text
Direct light: #F0B670 warm sunset key light
Shadow fill: #4A5870 cool blue-gray shadow
Main environment: #6B4830 worn deck wood
Skin: #A86A4A bronze skin tone
Cloth accent: #8B2F2F blood-red scarf
Leather: #5C1F1F dark wine leather
Fabric: #D4B896 beige woven cloth
Machine dark: #2D2A2A cold prosthetic dark metal
Panel black: #1A1A1A matte black machine panel
Tech glow: #4FC3D9 cyan mechanical eye glow
Oxidized bronze: #7A6845 greenish bronze armor
Polished copper: #8E6F3D copper highlight
Dust haze: #C8A87A desert atmospheric haze
```

## Writing Heuristics

- Prefer physical instructions over adjectives: "left hand taps the mast twice" beats "confident".
- Use `内容事实锁定` as the content guardrail before filling the prompt template; the prompt may be stylish, but the facts must stay literal.
- Map every reference to a job: "as face anchor", "as scene layout", "as palette anchor".
- Do not describe character clothing or wardrobe unless the user explicitly asks for it.
- Keep prompt structure stable and style content dynamic. Fixed fields do not mean fixed color palette, fixed genre, or fixed scene mood.
- Repeat critical constraints in both image anchors and text when consistency matters.
- Put `记忆性固定站位` before detailed camera movement for all multi-character scenes.
- Choose cut grammar before writing action beats. Do not default to one continuous take.
- Use time phases for clips longer than 6 seconds.
- Self-check Chinese dialogue density before finalizing duration: best range is 3-4 characters per second; avoid more than 5 characters per second. If the line count is too high, split into another segment or increase duration.
- Define the final frame for multi-clip continuity.
- Use negative constraints only for likely failure modes; keep them concrete.

## Silent Self-Check Output

Do not ask the user routine self-check questions. Ask only when the segment start/end is unclear, the confirmed final frame conflicts with the script, dialogue cannot fit the current model limit, director notes conflict with script order, or missing asset names would make the prompt unusable.

After the formal prompt, include only a compact external note:

```text
台词自检｜不放入万物生：{台词逐字一致/差异说明}；{字数/秒数/语速判断}。
```
