# Blue Tsunami: documentary trailer (36 s)

A trailer about the 2026 Texas midterm upset: James Talarico defeating Ken Paxton for U.S. Senate, and Gina Hinojosa unseating Gov. Greg Abbott.

## Files
- `index.html`: the trailer as HTML motion graphics. Open it in a browser and press **Play** (Space pauses, R restarts).
- `blue-tsunami-trailer.mp4`: 1920x1080, 30 fps, 35.8 s render with the mixed soundtrack.
- `assets/texas-counties.svg`: layered vector map for animating in other tools. It has 254 county paths (`id="c48xxx"` FIPS, plus `data-name`, `data-cx`, `data-cy`) and a separate `#outline` path.
- `assets/soundtrack.mp3`: final mix (VO + score + sub boom), loudness-normalised to about -15 LUFS.
- `assets/vo/`: voiceover lines, trimmed and tempo-adjusted (`raw/` holds the originals from Higgsfield Text to Speech V2 on the ElevenLabs engine, voice "Callum").
- `assets/music/score.mp3`: score from Higgsfield (ElevenLabs Music v2.5).
- `assets/photos/`: supplied photos of Talarico and Paxton, resized only (Lanczos plus a light sharpen, no AI alteration).
- `assets/img/`: background plates generated in Higgsfield (GPT Image 2.6). They are atmospheric scenes with no candidate likenesses.

## Script and timing
Cuts are locked to the score's hits at 0.5, 7.75, 15.25, 22.5 and 30.0 s.

| Time | VO | Picture |
|---|---|---|
| 0.4 | For thirty years... Texas was a wall. | Texas outline draws on |
| 3.8 | Red. Unbreakable. They said it would never move. | Counties cascade red over storm plains |
| 7.75 | Then... the water started rising. | Blue water rises inside the map |
| 10.6 | A former schoolteacher took on Ken Paxton. | Senate photo split: Talarico vs. Paxton |
| 13.9 | Donald Trump bet millions on Paxton. But as the President's popularity sank... his endorsement became an anchor. | Paxton portrait, "Endorsed by Donald Trump" stamp on the 15.25 hit, sourced quote, then the portrait sinks under water |
| 22.4 | An Austin lawmaker took on the Governor himself. | Governor: Hinojosa vs. Abbott |
| 25.7 | November third. The polls close. | Clock 6:58 → 7:00, vote counter |
| 28.4 | And the wall... breaks. | Map cracks, then a flash and the flood on "breaks" at 30.0 |
| 31.3 | Blue Tsunami. The night Texas turned. | Title card over the crowd |

The Trump segment is based on The National Desk's Nov. 4, 2026 report that Trump endorsed and campaigned for Paxton, "poured millions of dollars into the Senate race," and that his popularity "took a dip."

Results on screen: Senate Talarico 55%, Paxton 43% (99% of the expected vote in), and Hinojosa unseats Abbott, per ABC News and NBC News projections on Nov. 3, 2026.

## Re-rendering the MP4
`window.__seek(t)` renders any moment deterministically. Step it at 30 fps with Playwright, screenshot each frame, and pipe the frames into ffmpeg with `assets/soundtrack.mp3`.
