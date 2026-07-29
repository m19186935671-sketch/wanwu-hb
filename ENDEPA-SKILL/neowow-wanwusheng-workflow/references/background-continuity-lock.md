# 人物背后背景锁定

Use this reference when a Wanwusheng segmented prompt needs stronger spatial continuity across clips, hard cuts, reverse angles, movement, doorways, hallways, vehicles, or high-speed outdoor motion.

## Core Rule

`人物背后背景锁定` is not a permanent background attached to a character. It is a continuity constraint derived from:

1. 上一段末帧
2. 当前记忆性固定站位
3. 当前镜头方向
4. 人物是静止、普通移动，还是高速移动

Update it for every segment. If a character moves, turns, crosses a doorway, enters a vehicle, exits a vehicle, or the camera changes to a reverse angle, the background lock must update. Do not mechanically reuse an old background.

Use this source priority when deciding the background lock:

1. 用户刚确认或回传视频里的实际末帧
2. 用户最新纠正的剧本锚点
3. 当前段落的固定站位、镜头方向和移动路线
4. 新场景重新建立的空间锚点

If the character has left the previous location, the old location may only be mentioned as the route origin when the movement is still visible. Do not write the old location as the character's current background after the character has already entered a new hallway, elevator, room, street, vehicle, or other scene.

Place it after each relevant character image anchor:

```text
@[{角色名}形象图] 作为{角色名}身份与表情锚定：{身份/姿态/表演状态，不描述服饰，除非用户要求服饰}。
人物背后背景锁定：{角色名}背后应保持{当前镜头方向可见的背景/地标/空间区域}，不得变成{不属于当前地点或当前镜头方向的背景}。
```

## When To Add It

Add `人物背后背景锁定` when the prompt has any of these pre-generation continuity risks:

- 同一场景被拆成多个视频片段
- 多人物固定站位需要跨镜头保持左右、前后、高低关系
- 硬切、反打、过肩、特写后切回中景或全景
- 人物靠近门口、走廊、电梯、楼梯、车窗、街口等容易跳场的位置
- 人物正在走路、追逐、上车、下车、车内移动或户外高速移动
- 上一段末帧对下一段有明确承接
- 用户要求检查关键帧、站位、背景或空间一致性

This is not a claim that the generated video will fail. It is a pre-generation continuity prevention rule based on the script structure and shot design.

## Static Indoor / Outdoor

For static shots, lock the visible direction and landmarks behind the character.

```text
人物背后背景锁定：{角色名}背后应保持{走廊深处/电梯方向/门口暖光/街道路灯/楼门/院墙等当前镜头可见背景}，不得变成{客厅/室外/无关街区/错误方向背景}。
```

## Walking Or Slow Movement

For walking, slow movement, or follow shots, lock the path and the gradual background transition.

```text
人物背后背景锁定：{角色名}沿{移动路线}移动，背后背景从{起点背景}逐渐过渡到{终点背景}；过渡必须连续，不得突然换成其他地点，不得改变人物左右关系。
```

## Outdoor High-Speed Movement

For high-speed outdoor movement, do not lock one static object. Lock the moving background band, route type, movement direction, and continuity.

```text
人物背后背景锁定：本段为户外高速移动，{角色名}背后不锁定单一静态背景，而锁定为“{环境类型}沿{运动方向}连续后掠的背景带”。背景允许高速运动模糊、视差滑动、光影拖影，但必须保持同一路线类型和空间连续性，不得突然跳成{无关地点类型}，不得改变人物左右关系。
```

Examples of `{环境类型}`:

- 城市高架路、路灯、护栏、远处楼群和车流光影
- 城市街道、路边店招、树影、停靠车辆和人行道边线
- 山路、护坡、弯道标识、树线和路面反光
- 海边公路、护栏、海面、路灯和远处建筑轮廓

## Vehicle Interior

For vehicle interiors, lock the window view as a moving background band.

```text
人物背后背景锁定：本段为车内高速行驶，{角色名}背后通过车窗可见连续后掠的{道路类型}光影、护栏、路灯和远处地标。背景允许高速运动模糊和窗外光带拖影，但不得跳场，不得让窗外环境突然变成{无关地点类型}。
```

## Reverse Angles

When the camera reverses angle, update the lock according to the new camera direction.

```text
人物背后背景锁定：本镜头为反打角度，{角色名}背后应从{上一角度背景}更新为{当前反打角度可见背景}；更新必须符合固定站位和镜头方向，不得继续沿用上一镜头的背后背景。
```

## Negative Constraints

Use concrete negatives when background drift is likely:

```text
NOT 背景跳场; NOT 人物背后变成无关地点; NOT 静态背景硬套到移动镜头; NOT 高速移动中背景完全静止; NOT 路线方向反复改变; NOT 人物左右关系互换; NOT 反打后背景与镜头方向矛盾。
```
