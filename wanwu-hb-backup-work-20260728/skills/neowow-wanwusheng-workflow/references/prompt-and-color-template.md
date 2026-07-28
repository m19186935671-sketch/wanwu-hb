# Prompt And Color Templates

## Segment Prompt Template

```text
[STYLE LOCK]
{film/look/style} + {lens/aspect ratio} + {realism level} + {texture} + {global tone}.

[记忆性固定站位 - 最高优先级]
If this segment continues the same scene, inherit the previous segment's final frame and fixed positions. Redesign positions only after a scene/location change or explicit scripted movement.
{scene/object anchor} is the coordinate baseline. Keep all relative positions fixed unless movement is explicitly written.
{character A}: {screen/world position}, facing {direction}, {height/status}.
{character B}: {screen/world position}, facing {direction}, {height/status}.
{separator object}: between {sides/characters}, functioning as {power boundary/visual divider}.
No side-swapping, teleporting, or hierarchy flattening.

{reference anchors}
@[character_asset] as {character name}'s identity anchor: {face/body language/posture/expression details to preserve}.
@[scene_asset] as the scene anchor: {layout/materials/scale to preserve}.
@[palette_asset] as the color-card anchor: all colors follow the listed palette.

{color lock}
Key colors:
{hex} = {light/material/skin/cloth/metal/glow role}
{hex} = {role}
{hex} = {role}

Opening frame:
{exact first visual state, character positions, camera distance, light direction}.

Camera:
{shot scale} + {focal length/lens feel} + {movement or cut grammar} + {composition rule} + {duration}.

Editing:
HARD CUT / INSERT SHOT / REACTION CLOSE-UP / RE-ESTABLISHING WIDE as needed. Do not default to one continuous take.

Action beats:
0-{x}s: {specific physical action}.
{x}-{y}s: {specific physical action or reaction}.
Final seconds: {settling beat and final frame state}.

Dialogue/audio:
{exact dialogue if any} + {voice tone/accent/speed}.
Ambient sound: {wind/room tone/mechanical noise}.
SFX: {specific sound tied to visible action}.
Music: {none or exact type}.

Final frame:
{state that should hold for continuity into the next clip}.

Negative constraints:
NOT {unwanted style/action/drift}; no subtitles; no watermark.
Video duration: {seconds}s.
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
