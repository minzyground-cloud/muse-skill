# Video Production Sound Effects

Sound effects for sungkil's video work come from one designated library, mixed with the ffmpeg-skill.

## Source

- **効果音ラボ (soundeffect-lab.info)** — sungkil's designated SFX library (2026-10-27, "웬만한 거 다 있음"). MP3 downloads by category (daily life, machine/vehicle, animals, nature, UI, etc.).
- Respect the site's terms of use for every effect (attribution/commercial-use conditions as stated on the site).

## Workflow

1. Identify the scenes in the edit that need effects (door, footsteps, sparkle, whoosh, animal sounds, and so on).
2. Pick scene-appropriate effects from 効果音ラボ and download the MP3s into the project's working folder.
3. Mix with the **ffmpeg-skill** (`~/workspace/custom-skills/ffmpeg-skill/`): probe first, plan with `--dry-run --json`, place effects on the timeline at scene cuts, keep levels under the BGM, verify the render with check/look before reporting.
4. Log which effects were used in the '영상 제작 스킬' side chat, which manages video-production skills and assets.

## sungkil's standing rules

- BGM taste: brighter, livelier music that keeps the energy up — slow, quiet piano makes the mood droop, even for calm/goodnight themes (2026-10-29).
- Publishing is never automatic: any reel/video goes public only after sungkil confirms that specific item (YouTube/Instagram/Facebook absolute rule).
