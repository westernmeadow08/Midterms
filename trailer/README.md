# Blue Tsunami: 30-second documentary trailer

A trailer about the 2026 Texas midterm upset: James Talarico defeating Ken Paxton for U.S. Senate, and Gina Hinojosa unseating Gov. Greg Abbott.

## Files
- `index.html`: the trailer as HTML motion graphics. Open it in a browser and press **Play** (Space pauses, R restarts).
- `blue-tsunami-trailer.mp4`: 1920x1080, 30 fps, 31.5 s render with the mixed soundtrack.
- `assets/texas-counties.svg`: layered vector map for animating in other tools. It has 254 county paths (`id="c48xxx"` FIPS, plus `data-name`, `data-cx`, `data-cy`) and a separate `#outline` path.
- `assets/soundtrack.mp3`: final mix (VO + score + sub boom), loudness-normalised to about -15 LUFS.
- `assets/vo/`: voiceover lines, trimmed and tempo-adjusted (`raw/` holds the originals from Higgsfield, Seed Audio, voice "Barrett").
- `assets/music/score.mp3`: score from Higgsfield (ElevenLabs Music v2.5).
- `assets/img/`: background plates generated in Higgsfield (GPT Image 2.6). They are atmospheric scenes with no candidate likenesses.

## Script and timing
| Time | VO | Picture |
|---|---|---|
| 0.2 | For thirty years, Texas was a wall. | Texas outline draws on |
| 3.5 | Red. Unbreakable. They said it would never move. | Counties cascade red over storm plains |
| 9.3 | Then the water started rising. | Blue water rises inside the map (score hit at 9.0) |
| 12.7 | A former schoolteacher took on Ken Paxton. | Senate: Talarico vs. Paxton |
| 16.6 | An Austin lawmaker took on the Governor himself. | Governor: Hinojosa vs. Abbott |
| 19.5 | November third. The polls close. | Clock 6:58 → 7:00, vote counter |
| 22.9 | And the wall... breaks. | Map cracks, then a flash and the flood on "breaks" at 25.0 |
| 26.4 | Blue Tsunami. The night Texas turned. | Title card over the crowd |

Results on screen: Senate Talarico 55%, Paxton 43% (99% of the expected vote in), and Hinojosa unseats Abbott, per ABC News and NBC News projections on Nov. 3, 2026.

## Re-rendering the MP4
`window.__seek(t)` renders any moment deterministically. Step it at 30 fps with Playwright, screenshot each frame, and pipe the frames into ffmpeg with `assets/soundtrack.mp3`.
