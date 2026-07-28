# Dense Style Vocabulary

Use this reference when a prompt feels structurally correct but too plain. 万物生-style prompts often work because they stack precise production vocabulary with spatial blocking, reference anchors, and sound cues.

## Density Rule

For important shots, avoid one-line style tags. Build density in layers:

1. medium and texture: film stock, lens, grain, halation, contrast, color temperature
2. genre and staging tradition: disaster, road escape, family realism, noir, wuxia, workplace documentary
3. camera/editing grammar: low angle, over-shoulder shot, reverse over-shoulder, reaction close-up, insert shot, lateral orbit, fast zoom, movement reveal, hard cut
4. light and atmosphere: top light, hard shadow, haze, dust, window spill, practical lamp, softened background contrast
5. spatial hierarchy: foreground frame, midground action, background chaos, who is high/low in frame
6. motion choreography: edge entry, partial reveal, freeze, recoil, glance, hand detail, prop movement
7. sound design: room tone, kettle hiss, cloth drip, voice entering offscreen, sudden silence, diegetic effects only

## Style Lock Phrases

Use specific combinations rather than generic "cinematic":

- 35mm film texture, Kodak low-saturation warm tone, fine organic grain
- analog film grain visible, slight halation on highlights, photochemical print feel
- low-contrast middle-gray tonality, restrained palette, tactile real-world materials
- 2.39:1 anamorphic widescreen, shallow depth of field, compressed background
- handheld micro-shake, breathing camera, hard cut, reaction close-up, insert detail, slow lateral orbit, steady dolly back
- Steven Spielberg-style movement reveal: low-angle looking up, subject enters from frame edge
- Christopher Doyle-style practical-light interior, painterly desaturation, humid color cast
- domestic realist blocking, cramped apartment power hierarchy, naturalistic restrained acting

## Spatial Blocking Vocabulary

Describe who controls the frame:

- foreground left edge only shows a shoulder/back-of-head sliver
- sofa occupies the upper half of frame like a raised platform
- two children sit below the coffee table sightline, visually lower than the adults
- adult's knees and crossed legs dominate the foreground, child's face is framed below them
- character freezes mid-sit, hips suspended, knees bent, body caught in humiliation
- camera stays at floor height, making the sofa figures loom above
- over-shoulder from the children's low side across the coffee table toward the adult on the sofa
- reverse over-shoulder from the adult's high side down toward the children, preserving eyeline and left-right orientation
- hard cut from public living-room confrontation to closed bedroom-door private threat
- door slam turns the soundscape from open room tone into muffled interior pressure

## Sound Vocabulary

Tie sound to visible action:

- kettle low hiss under the dialogue
- wet clothes dripping onto carpet with tiny taps
- leather sofa creak as the adult settles into the center
- porcelain cup clink, hot water splash, abrupt hand tremor
- toy car plastic wheel rattle on carpet
- offscreen voice cuts in before the camera reveals the speaker
- no BGM, only room tone, fabric rustle, breath, small domestic object sounds

## Example Domestic Style Lock

```text
[STYLE LOCK]
35mm domestic realist film texture, Kodak low-saturation warm-gray palette, fine grain, shallow depth of field, natural window spill mixed with weak practical interior light. Cramped family living-room blocking with visible class pressure: sofa as raised authority position, carpet as lowered humiliation zone. Handheld micro-shake, restrained acting, no melodramatic push music.

Camera grammar: floor-height low angle, over-coffee-table sightline, slow push-in only when emotional pressure rises, hard cuts reserved for power shifts. Light is cold daytime from window-left; sofa faces receive warmer bounce, children on carpet fall into cooler gray shadow.

Sound track: room tone, kettle hiss, wet fabric drip, leather sofa creak, porcelain cup clink, toy car rattle, human dialogue only, no BGM.
```

## Upgrade Checklist

When upgrading a plain prompt into dense 万物生 style, add:

- one exact lens/frame/film texture line
- one spatial hierarchy sentence
- one foreground/midground/background sentence
- one motion reveal or cut rule
- one atmosphere/light contrast sentence
- three diegetic sound details
- concrete negative constraints for the likely failure modes
