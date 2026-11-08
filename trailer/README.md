# Blue Tsunami: documentary trailer (47 s)

A trailer about the 2026 Texas midterm upset: James Talarico defeating Ken Paxton for U.S. Senate, and Gina Hinojosa unseating Gov. Greg Abbott.

## Files
- `index.html`: the trailer as HTML motion graphics. Open it in a browser and press **Play** (Space pauses, R restarts).
- `blue-tsunami-trailer.mp4`: 1920x1080, 30 fps, 47 s render with the mixed soundtrack.
- `assets/texas-counties.svg`: layered vector map for animating in other tools. It has 254 county paths (`id="c48xxx"` FIPS, plus `data-name`, `data-cx`, `data-cy`) and a separate `#outline` path.
- `assets/soundtrack.mp3`: final mix (VO + score + sub boom), loudness-normalised to about -15 LUFS.
- `assets/vo/`: voiceover lines, trimmed and tempo-adjusted (`raw/` holds the originals from Higgsfield Text to Speech V2 on the ElevenLabs engine, voice "Callum").
- `assets/music/score_v1_extended.mp3`: the score used in the final mix. It is the original first-version score (`score_v1.mp3`, Higgsfield ElevenLabs Music v2.5), extended to 47 s by repeating its 9–25 s build on the bar line, so the hits fall every 8 s.
- `assets/music/score.mp3`: the alternate 36 s score from the second cut (not used).
- `assets/photos/`: supplied photos of Talarico and Paxton, resized only (Lanczos plus a light sharpen, no AI alteration).
- `assets/img/`: background plates generated in Higgsfield (GPT Image 2.6). They are atmospheric scenes with no candidate likenesses.

## Script and timing
Cuts are locked to the score's hits at 1, 9, 17, 25, 33 and 41 s. There is no film grain.

| Time | VO | Picture |
|---|---|---|
| 0.4 | For thirty years... Texas was a wall. | Texas outline draws on |
| 3.8 | Red. Unbreakable. They said it would never move. | Counties cascade red over storm plains |
| 9.0 | Then... the water started rising. | Blue water rises inside the map |
| 12.0 | A former schoolteacher took on Ken Paxton. | Senate photo split: Talarico vs. Paxton |
| 17.0 | Donald Trump bet millions on Paxton. But as the President's popularity sank... his endorsement became an anchor. | Paxton portrait with "Endorsed by Donald Trump" stamp and sourced quote, then the portrait sinks under water |
| 24.4 | Elon Musk poured more than four hundred million dollars into the midterms. It wasn't enough. | "$400,000,000+" slams in on the 25 s hit, then gets struck out |
| 30.2 | An Austin lawmaker took on the Governor himself. | Governor: Hinojosa vs. Abbott |
| 33.45 | November third. The polls close. | Clock 6:58 → 7:00, vote counter |
| 36.1 | The people have spoken. And Texas... stood up. | Crowd with phone lights at the Capitol |
| 39.6 | And the wall... breaks. | Map cracks, then a flash and the flood on "breaks" at 41.0 |
| 42.6 | Blue Tsunami. The night Texas turned. | Title card over the crowd |

Sources for the new segments:
- Trump: The National Desk (Nov. 4, 2026) reports that Trump endorsed and campaigned for Paxton, "poured millions of dollars into the Senate race," and that his popularity "took a dip."
- Musk: the Washington Post and Rolling Stone (Nov. 2026) report that he spent more than $400 million on the 2026 midterms, most of it backing Paxton. CNBC puts the total at $474 million or more.

Results on screen: Senate Talarico 55%, Paxton 43% (99% of the expected vote in), and Hinojosa unseats Abbott, per ABC News and NBC News projections on Nov. 3, 2026.

## Re-rendering the MP4
`window.__seek(t)` renders any moment deterministically. Step it at 30 fps with Playwright, screenshot each frame, and pipe the frames into ffmpeg with `assets/soundtrack.mp3`.
