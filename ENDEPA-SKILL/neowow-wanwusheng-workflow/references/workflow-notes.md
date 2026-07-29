# 万物生-Style Workflow Notes

## Observed Pattern

The public 万物生-style workflow is best understood as an asset-driven canvas pipeline:

1. Build reusable world assets first: characters, scenes, props, mechanical creatures, voice references, and color cards.
2. Convert each asset into a stable reference anchor. In prompts this often appears as an asset token like `@[asset_id]` with a clear role.
3. Define `记忆性固定站位` for each scene: the stable spatial map of character positions, facing directions, height/status, and separator objects.
4. Split the episode into many short video segments. Each segment receives its own shot contract rather than relying on a single global prompt.
5. Keep continuity by repeating anchors, fixed positions, and first-frame/last-frame state.
6. Generate, inspect, revise, stitch, and enhance each segment.

## Canvas Mental Model

Treat the canvas as a production board with these zones:

- World bible: tone, rules, period, materials, recurring camera grammar.
- Character board: one card per character, with identity, posture, expression range, spatial role, props, voice, and defect checks. Do not add clothing descriptions unless explicitly requested.
- Scene board: one card per major location, with geometry, lighting, and reusable background images.
- Object board: vehicles, weapons, animals, mechanical creatures, symbolic props.
- Palette board: a color card image plus text mapping of hex colors to semantic roles.
- Fixed-position board: a scene map describing who stays where and which object defines the power boundary.
- Shot board: one node per generated clip, ordered by timeline.
- Continuity board: accepted first/last frames, rejected attempts, and notes for fixing drift.

## Prompt Anatomy

A strong segment prompt usually contains:

- Style lock: film stock, lens, aspect ratio, camera feel, realism level, art direction.
- Fixed position memory: stable scene coordinates and power relationships.
- Reference anchors: each image/audio reference must say what it controls.
- Color lock: color-card anchor plus explicit hex-to-material mapping.
- Opening frame: the first visible state.
- Camera plan: shot scale, lens, movement, composition, duration.
- Blocking/action: ordered physical beats, not vague emotion.
- Dialogue/audio: exact line, tone, accent, speed, ambience, effects, music constraints.
- Final frame: the state to preserve for continuity.
- Negative constraints: no subtitles, no watermark, no unwanted style, no slow motion, no drift.

## Reference Image Roles

Avoid giving every reference image the same job. Assign a single dominant responsibility:

- Character anchor: face/identity, body language, posture, expression, spatial role, prosthetics, silhouette. Avoid clothing/wardrobe details unless explicitly requested.
- Scene anchor: layout, scale, architecture, terrain, props in space.
- Prop/creature anchor: shape language, material, mechanical parts, eyes, motion constraints.
- Color-card anchor: palette only, not composition.
- Pose/action reference: body position or movement only.
- First/last frame: continuity and transition only.

## Practical Sequence

For a new project, do not start with the final episode. Start with a three-clip calibration:

1. Identity test: one character in a simple shot.
2. Scene test: the same character in the main location.
3. Color test: same setup with the color card enforced.

Only expand into a full shot list after these three tests are stable.

## Research Caveats

Neowow pages, public work pages, and open-source canvas repositories can change. For exact current UI, route names, links, statistics, or project equivalence claims, verify live sources before answering. When unsure, say what is observed and what is inferred.
