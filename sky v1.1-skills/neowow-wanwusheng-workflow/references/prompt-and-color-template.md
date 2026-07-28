# Prompt And Color Templates

## Segment Prompt Template

```text
【[STYLE LOCK]
{镜头风格}，{色彩风格}，{画面质感}，{光线设定}。{场景名称}空间，{核心空间物件/区域}形成清晰空间关系与权力层级：{高位区域}，{分界线/阻隔物}，{低位区域/弱势区域}。画幅 {画幅比例}，严格按照剧本顺序和导演备注执行，不额外改写剧情，不生成字幕，不配 BGM。

音轨：仅{环境音}、{动作声}、{道具声}、人声对白，不配 BGM。

[记忆性固定站位 - 最高优先级]
本段是{新场景第一段 / 承接上一段}，{重新建立 / 严格继承}固定站位。{核心空间物件/场景锚点}是空间坐标基准。后续所有硬切、反打、特写、插入、跟随、推拉镜头，只改变景别和观察角度，不得擅自改变人物相对位置。

按本段实际出场人物建立固定站位：
{人物名}：{位置}，面朝{方向}，{姿态/情绪/状态/叙事功能}。
{人物名}：{位置}，面朝{方向}，{姿态/情绪/状态/叙事功能}。
{人物名}：{位置}，面朝{方向}，{姿态/情绪/状态/叙事功能}。
……
未在本段明确参与行动或开口的人物，只能作为背景存在；不得抢镜、不得提前行动、不得提前揭示后文信息。
{核心道具/分界物}位于{位置}，作为{空间边界/羞辱道具/权力象征/动作触发点}。

除非剧本文字明确写出移动，所有人物不得换边、不得瞬移、不得改变前后关系、不得抹平高低权力关系。

[参考锚点]
按本段实际出现的人物自动添加形象锚点：
@[{人物名形象图}] 作为{人物名}身份与表情锚定，控制{表情/心理/姿态/动作状态}。
@[{人物名形象图}] 作为{人物名}身份与表情锚定，控制{表情/心理/姿态/动作状态}。
……

@[{场景图}] 作为空间锚定，锁定{场景布局、动线、关键物件、前景遮挡关系}。
@[{核心道具图，如有}] 作为道具锚定，控制{形状/材质/位置/叙事作用}。
@[{色卡图}] 作为色彩锚定：{色彩名称1}{HEX}，{色彩名称2}{HEX}，{色彩名称3}{HEX}，{色彩名称4}{HEX}，{色彩名称5}{HEX}。

[镜头拆分规则]
根据剧本内容自适应镜头数量，不固定镜头个数；根据本段实际出场人物自适应人物锚点，不固定人物数量。
每一个镜头必须服务一个明确功能：建立空间、角色开口、权力压迫、反应特写、道具插入、动作转折、离场衔接。
有导演备注、括号动作、△动作时，必须按原顺序保留。
长台词可独立成一个镜头；情绪受伤、撒谎、压怒、羞辱、沉默停顿必须给反应镜头。
重要道具必须给插入镜头。
对峙场面优先使用过肩、反打、中近景和反应特写；空间关系混乱前必须切回重建广角。
不强行一镜到底，不为了镜头数量或人物数量添加无意义镜头。

镜头一：
{根据剧本生成：景别 / 机位 / 构图 / 镜头功能}。{主体人物或主体道具}。{动作、表情、空间关系}。
{如有台词：人物名}说：“{台词}”台词必须一字不改。
{如无台词：只拍{动作/反应/道具}，不新增台词。}

HARD CUT

镜头二：
{根据剧本生成：景别 / 机位 / 构图 / 镜头功能}。{主体人物或主体道具}。{动作、表情、空间关系}。
{如有台词：人物名}说：“{台词}”台词必须一字不改。
{如无台词：只拍{动作/反应/道具}，不新增台词。}

HARD CUT

镜头三至镜头N：
继续根据剧本顺序自适应生成镜头。每个镜头必须包含：
景别与机位；主体人物或主体道具；动作与表情；是否有台词；与固定站位的连续关系；是否 HARD CUT 到下一镜。

末帧：
{本段最后一个画面必须清楚交代：本段实际出现人物各自位置、情绪状态，核心道具/门/桌/沙发/边界是否仍然保留，为下一段什么剧情做衔接。}

[负面约束]
NOT 固定人物数量；NOT 固定镜头数量；NOT 为了凑人物添加未出场角色；NOT 为了凑镜头添加新剧情；NOT 改变剧本顺序；NOT 改写台词；NOT 漏掉导演备注；NOT 漏掉括号动作；NOT 漏掉△动作；NOT 人物换边；NOT 越轴；NOT 硬切后人物位置漂移；NOT 非主体人物抢镜；NOT 提前揭示后文动作；NOT 生成字幕或屏幕文字；NOT 描述人物服饰；NOT BGM；无字幕；无水印。

视频时长：根据台词量、人物数量与镜头数量设置为 {建议时长}，不得超过当前模型版本上限；默认 Seedance 2.0 / 万物生最高 15 秒，若超过则拆分为下一段。】
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
- Map every reference to a job: "as face anchor", "as scene layout", "as palette anchor".
- Do not describe character clothing or wardrobe unless the user explicitly asks for it.
- Repeat critical constraints in both image anchors and text when consistency matters.
- Put `记忆性固定站位` before detailed camera movement for all multi-character scenes.
- Choose cut grammar before writing action beats. Do not default to one continuous take.
- Use time phases for clips longer than 6 seconds.
- Self-check Chinese dialogue density before finalizing duration: best range is 3-4 characters per second; avoid more than 5 characters per second. If the line count is too high, split into another segment or increase duration.
- Define the final frame for multi-clip continuity.
- Use negative constraints only for likely failure modes; keep them concrete.
