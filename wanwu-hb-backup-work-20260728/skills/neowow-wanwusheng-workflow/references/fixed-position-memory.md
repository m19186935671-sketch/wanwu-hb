# 记忆性固定站位

This is a highest-priority rule. Define fixed positions before writing the shot prompt. Use the fixed positions as the scene's coordinate memory so the model has a stable map to preserve across cuts, camera moves, and character reactions.

For continuous剧情, fixed positions are inherited from the previous segment's final frame. Do not redesign the scene map just because a new prompt begins. Redesign fixed positions only when the story moves to a new scene/location, when a time jump resets the blocking, or when the script explicitly describes characters moving.

## Why It Works

`记忆性固定站位` reduces three common video-generation failures:

- character drift: people swap sides, teleport, or face the wrong direction
- relationship drift: power hierarchy weakens because the camera forgets who is above/below or near/far
- continuity drift: later hard cuts contradict earlier spatial layout

It also strengthens drama. In 万物生-style prompting, spatial memory is not just technical continuity; it carries story meaning. Who is high, low, blocked, centered, cornered, separated by a table, or entering from the edge tells the model what conflict to preserve.

## Required Placement

Put this block near the top of a prompt, after `[STYLE LOCK]` and before reference anchors or detailed shot text:

```text
[记忆性固定站位 - 最高优先级]
若本段承接上一段同一场景，则严格继承上一段末帧站位；只有切换新场景/新地点，或剧本文字明确写出人物移动时，才允许重新设计站位。
本场空间关系固定不变，后续镜头、硬切、推拉、环绕均不得擅自改变人物相对位置。
{scene anchor/object} 是空间坐标基准。
{character A} 位于 {position}, 面朝 {direction}, 身体高度/姿态为 {status}.
{character B} 位于 {position}, 面朝 {direction}, 身体高度/姿态为 {status}.
{object separator} 位于 {between whom}, 作为视觉分界线/权力边界。
除非文字明确写出移动，所有人物不得换边、不得瞬移、不得改变前后关系。
```

## What To Specify

Always define:

- anchor object: sofa, table, bed, cliff, door, vehicle, mast, throne, hallway
- screen side: frame-left, frame-right, center, foreground, midground, background
- world position: near window, by door, behind coffee table, on carpet, at sofa center
- facing direction: toward camera, toward sibling, toward father, toward bedroom door
- height/status: standing, kneeling, sitting on sofa, sitting on floor, lying down
- separator: coffee table, doorway, table edge, cliff wall, distance, crowd, vehicle
- allowed movement: who may cross the boundary, who must remain fixed

## Domestic Power Example

```text
[记忆性固定站位 - 最高优先级]
陈建国家客厅空间关系固定不变。真皮沙发沿画面后方横向摆放，是高位权力区；茶几位于画面中线，是成年人和兄妹之间的硬分界线；地毯位于画面前方，是被迫坐下的低位区。

何佳丽固定在沙发正中间高位，面朝画面前方和茶几方向，翘腿俯视兄妹。
陈建国固定在何佳丽旁边偏画面右侧，身体略向何佳丽倾斜，眼神经常躲向茶具。
陈峰和陈念固定在茶几前方地毯上，低于沙发视线；陈峰靠画面左前方，陈念靠他身后半步。
陈小宝固定在茶几边地毯另一侧，盘腿抱玩具车，位置比兄妹更靠近沙发但同样在地上，用挑衅笑制造羞辱对照。
除非明确写出起身或被拉走，所有人不得换边、不得改变沙发/茶几/地毯的高低权力关系。
```

## Shot Writing Rule

Every shot description should reference the fixed-position block:

- "本段承接上一段末帧"
- "保持上述固定站位"
- "同一场景连续剧情不得重新摆放人物"
- "切换到新地点后重新建立固定站位"
- "镜头只改变景别，不改变人物相对位置"
- "硬切后仍保持沙发在后方高位、兄妹在前方地毯低位"
- "环绕只围绕茶几边界运动，不让角色换边"

## Negative Constraints

Add concrete negatives when the scene has many people:

```text
NOT 人物换边; NOT 陈峰坐到沙发; NOT 何佳丽离开沙发中心; NOT 茶几消失; NOT 地毯与沙发高度关系被抹平; NOT 陈小宝站到兄妹身后; NOT 镜头把成年人和兄妹拍成平等高度。
```
