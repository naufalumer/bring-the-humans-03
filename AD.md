# AD.md — "Put your agent to work"

## Concept

A 28-second vertical ad (1080x1920, 30fps, H.264 + AAC) for make.fun, built to be
watched, not skipped: a hook in the first 4 seconds, proof on screen, then the ask.

- **Hook (0–4s):** make.fun's ghost crew on their laptops. "YOUR AI AGENT IS BORED."
  Voice: "Your AI agent is sitting there. Doing nothing."
- **Proof (4–8s):** the real make.fun board, a $1,325 bounty card front and centre.
  "MEANWHILE, OTHER AGENTS ARE WINNING REAL MONEY."
- **What make.fun is (8–13.5s):** a real bounty page ($1,325, 10 places paid).
  "make.fun IS WHERE AI AGENTS COMPETE FOR REAL MONEY."
- **What agents do there (13.5–18.8s):** ghost mark bobbing.
  "CODE · TRADE · BUILD · CREATE" — "If your agent can do it, there's a bounty for it."
- **Close (18.8–26.7s):** "YOUR AGENT DOES THE WORK. YOU KEEP THE WINNINGS."
  then "ENTER YOUR AI AGENT IN A BOUNTY ON make.fun".
- **End card (24.2–28.7s):** make.fun's referral end card washes over the last
  seconds and holds, with referral code `bye4mn13` typed into its field.

Voiceover: one voice throughout (Casper, via the platform TTS tool), over a quiet
synth pad + kick bed made for this ad. On-screen text: Inter Bold, white on ink,
in make.fun's own colours (magenta #c41c83, ink #191419, white).

## Brand — all from make.fun's press pack, fetched in this session

- Manifest + guide: https://make.fun/press/manifest.json, https://make.fun/press/llms.txt
- Brand badge: https://make.fun/press/brand-badge/9x16/makefun-badge-9x16.png
  (1080x1920 overlay, laid over the video as-is from frame 0 until the end card)
- Referral end card: https://make.fun/press/referral-card/9x16/makefun-card-9x16-transparent.webm
  (sha256 verified against the manifest: 286b76c6…; the hold frame is the webm's own
  last frame, so the card never pops)
- Screenshots: board-dark + competition-dark from the press pack; mascot art:
  mark-on-dark-1024 + the ghost-crew header. Used as they are, never redrawn or recoloured.
- Referral code on the card: `bye4mn13` (verified from GET /api/agents/me,
  `referrals.code`; link https://make.fun/r/bye4mn13).
- Play code for the caption: `makefun-needle-wasp-jaguar`
  (verified from GET /api/competitions/bring-the-humans-03/play-code?n=0).
  NOTE: `bye4mn13` is the referral code, not a play code — the caption needs the
  play code above (or the code in the TikTok bio) for the gate to pass.

## How it was made (all in this session)

1. Fetched the press manifest + llms.txt, the badge, the end card, the screenshots
   and the mascot art; verified the card webm sha256 against the manifest.
2. Wrote the creative (this file's concept) and the voiceover script.
3. Synthesised the voiceover with the platform TTS tool; built the music bed
   (numpy synth: Am–F–C–G pad + kick) and the scene backgrounds (PIL) in this session.
4. Rendered with ffmpeg in two passes: `build_clip.sh` (scenes, text, badge),
   then the llms.txt end-card recipe (card over the last 2.5s, code typed in
   JetBrains Mono Bold, ink #191419, at the manifest's field position).
5. Checked the first frame (badge in place) and the last frame (end card + code)
   before handing the file over.

Build scripts and intermediates live outside this repository, in the builder's
work directory — the repository holds only the entry: `main.ts`, `VIDEO.json`,
`LICENSE`, `README.md`, this file, `.makefun/owner.json` and `ad.mp4`.

## Posting (Naufal, from his phone, @tyrmeapart0)

1. Post `ad.mp4` as a video (not a photo post), audience Everyone, from the
   public account @tyrmeapart0, between entries opening (22 Nov 2026 02:00 WIB)
   and the deadline (25 Nov 2026 02:00 WIB). No edit, effect or trim in TikTok's
   editor — post the file as it is.
2. Caption (copy from README.md): it must carry "$500 bounty", make.fun written
   out, and the play code `makefun-needle-wasp-jaguar`.
3. Copy the video's full address (https://www.tiktok.com/@tyrmeapart0/video/<id>)
   and put it in `VIDEO.json` in place of the placeholder. Then the entry can be
   submitted in the make.fun room.
4. Keep the video up, public and viewable in the US until the results are out.
   Do not buy, bot or farm views and do not pay to promote it — only real views count.

## Bounty facts

- Bounty: bring-the-humans-03, "Bring the humans with a TikTok ad"
  https://make.fun/bounty/bring-the-humans-03
- $500 USDC over 20 places (1st $100, 2nd $70, 3rd $50, 4th–10th $20, 11th–20th $14),
  escrowed on Solana, free entry. Places go by the video's real TikTok views alone.
- Entries open 22 Nov 2026 02:00 WIB, close 25 Nov 2026 02:00 WIB.
- Signing/payout wallet: 4AMjUwVXnUN4YCxZRRHJvP1547sxveye3VjTJ9W1mhA8.

## v2 — jedag-jedug cut (22 Nov 2026)

Rebuilt from Naufal's feedback on v1 ("flat bgt"): the same ad, same scenes,
same voiceover and timing, but now it moves on the beat.

1. **Jedag-jedug:** a new 120 BPM bed (hard four-on-the-floor kick, hats, claps,
   risers into every scene change) replaces v1's quiet ~100 BPM bed, and the
   whole frame zoom-pumps on every beat (2.8% punch, exponential settle).
   Visuals and music share one beat grid, so every bounce lands on a kick.
2. **Flash cahaya:** a white flash fires on every beat and a stronger
   white + magenta flash on scene changes and on the 13.5s / 18.8s drops.
3. **Typing:** every on-screen line types in character by character
   (~18 chars/s) with a blinking caret and a small pop when the line lands;
   the referral code on the end card types in the same way (one character
   every 0.09s). A typing click sounds at every revealed character, placed
   from the same schedule as the video, so sound and letters stay in sync.
4. **Motion halus:** eased cross-dissolves between scenes, eased
   squash/tilt/jump curves on the mascot, easeOutBack pops on finished lines,
   exponential pump/flash decays — no stepped jumps anywhere.
5. **Maskot gerak:** the ghost mark dances through 13.5–24.2s — drifting side
   to side, squash-stretching on every beat, tilting, jumping every 2s and
   flipping to face the other way every other bar — and small marks peek and
   bounce in the bottom corner during the proof scenes (board 4.06–8.07,
   bounty page 8.07–13.5). The art itself is untouched (press pack, as-is);
   the "poses" are the animation: squash, tilt, flip, jump, drift.

Build (all in bring-the-humans-03-work, new scripts written for v2):
`render_v2.py` renders all 802 frames with PIL (typing schedule exported to
`typing_schedule.json`); `audio_v2.py` synthesises `bed_v2.wav` (120 BPM) and
`clicks.wav` from that schedule; one ffmpeg pass adds the end card (same
llms.txt recipe as v1) and mixes VO + bed + clicks. Verified: 1080x1920,
h264 + AAC, 28.73s, mean -13.1 dB / max 0.0 dB; first frame has the badge,
last frame holds the end card with `bye4mn13` fully typed. v1 is kept as
`ad-v1.mp4` in this repo.

## v3 — meriah cut (22 Nov 2026, audio only)

Owner watched v2 and asked for more festive music ("musiknya yg meriah"):
same ad, same frames, new bed. `audio_v3.py` synthesises `bed_v3.wav` —
still exactly 120 BPM with the kick on the same 0.5s grid (58 kicks, all
verified on-grid), so every visual pump/flash/typing beat still lands:
brighter C–G–Am–F pad, punchy bass on the beat, a catchy C-major
pentatonic pluck hook with an echo bounce, tambourine on the offbeat 8ths,
claps on beats 2 and 4 (plus every beat in the drop), a sparkle arp in the
build/drop, 1.0s risers into every scene change, and the biggest drop at
13.5s where the mascot dance starts. The bed is level-matched to v2 by RMS
(kick peak 0.504 vs v2's 0.490) so the groove hits just as hard; the
voiceover and typing clicks are reused unchanged and re-mixed at the same
gains (VO 2.0, bed 0.36, clicks 1.0, limiter 0.9). The video stream was
copied, not re-encoded: framemd5 and stream md5 are identical to v2
(862 frames), only the audio track changed. Verified: 1080x1920, h264 +
AAC, 28.73s, mean -13.3 dB / max 0.0 dB; drop window (14–18.5s, bed only)
-12.8 dB vs v2's -12.6 dB. v2 is kept as `ad-v2.mp4` in this repo.

## What the top entries do — and how v5 differs (researched 22 Nov 2026)

Researched bring-the-humans-02 before locking v5 (new standing rule: study
the winners first). Humans-02 had 3,411 entries, scored by referral
signups, not views: rank 1 tuan-muda ("Getting started with make.fun — a
newcomer's guide", 379 provisional / 55 verified signups) and the whole top
10 are the same shape — newcomer's guides and step-by-step tutorials
("from zero", "your first entry, from signup to payout", "how verified
signups actually work"). Our own humans-02 entry hyped instead ("get paid
in USDC for what your AI agent builds") and finished rank 2,235 with 0
signups. Limits, stated honestly: the API exposes no TikTok video URLs for
those entries and there is no browser here, so this is from titles +
scores, not from watching the videos; and humans-03 is scored by views,
not signups, so the -02 pattern transfers as "teach and prove, don't
hype", not as a literal prediction. Humans-03 had 0 entries at research
time (it opens 02:00 WIB 22 Nov), so there were no -03 videos to study
yet — we are early. How v5 differs on purpose: it opens with a face and
an identity (the tyrmeapart profile card with the agent avatar, "MY AI
AGENT MADE THIS AD") instead of a generic guide title; it leads with
verifiable proof (the live rank-1 GTA clipper leaderboard with real
numbers: 3,509 views, 1,725 entries) instead of a promise; and it keeps
the festive 120 BPM energy with a dancing mascot instead of a plain
explainer. The middle "what is make.fun" beat stays because the
competition requires the ad to explain make.fun — but it is framed by
proof on both sides.

## v5 — rebuilt from scratch to the owner's 4-beat arc (22 Nov 2026)

Owner redirected the v4 avatar-cameo patch into a full rebuild ("build dr
0") with a locked 4-beat story, in this order:

1. **INTRO (0–9.0s):** the tyrmeapart make.fun profile card with the
   agent's avatar in a circular bubble (magenta ring, pop-in + beat bob),
   handle, "AI AGENT ON make.fun", chips "82 ENTRIES" + "#1 GTA CLIPPER".
   Hook line "MY AI AGENT MADE THIS AD." New VO (vo5, Casper):
   "This is my agent. Eighty-two bounties entered, and it is just getting
   started."
2. **WHAT IS MAKE.FUN (9.0–24.0s):** real board proof ("MEANWHILE, OTHER
   AGENTS ARE WINNING REAL MONEY.", vo2), real bounty page ("make.fun IS
   WHERE AI AGENTS COMPETE FOR REAL MONEY.", vo3), then the ghost mascot
   dancing on the 120 BPM grid ("CODE · TRADE · BUILD · CREATE", drop at
   18.5s).
3. **OUR PROGRESS (24.0–32.5s):** the live GTA clipper leaderboard panel —
   tyrmeapart #1 in gold with views counting up to 3,509, then jclaw 3,296,
   drelat 3,127, seriwinda24-del 2,942, zyschiee 2,822, footer "1725
   ENTRIES". Headline "WE'RE NUMBER ONE." + "AND STILL CLIMBING." New VO
   (vo6, Casper): "And right now, we are number one. Three thousand five
   hundred and nine views on our GTA 6 clip."
4. **CTA (32.5–40.5s):** "YOUR AGENT DOES THE WORK. YOU KEEP THE
   WINNINGS." + "ENTER YOUR AI AGENT IN A BOUNTY ON make.fun" (vo4).
   End card from 38.03s: referral code `bye4mn13` typed per character
   from 39.47s, plus two lines printed under the field from the card start
   — "PLAY CODE: makefun-needle-wasp-jaguar" and
   "JOIN: make.fun/r/bye4mn13".

Everything v2/v3 had is kept: 120 BPM festive bed (same recipe, extended
to 42.5s), whole-frame beat pump, white/magenta flashes on beats and
scene changes (second big drop at 24.0s, the leaderboard reveal), typing
text + clicks, smooth eased motion, dancing mascot + corner peeks, brand
badge from frame 0. The ghost-crew hook scene and its VO line (vo1) were
dropped — the owner's arc replaces that hook with the profile intro.
Profile + leaderboard numbers are live API data (fetched 21 Nov 23:46
WIB): handle tyrmeapart, 82 entries, referral bye4mn13; leaderboard
tyrmeapart 3,509 views at rank 1 of 1,725 entries.

Build (all new scripts in bring-the-humans-03-work): `render_v5.py`
renders all 1,216 frames with PIL (typing schedule to
`typing_schedule_v5.json`); `audio_v5.py` synthesises `bed_v5.wav` (120
BPM, C–G–Am–F cycling, 86 kicks all on-grid, on-beat energy 0.1109 vs
off-beat 0.0407) and `clicks_v5.wav` (278 clicks); vo5/vo6 synthesised
with `/opt/hatch/bin/tts`, voice `avocado_v2:casper` (same voice as
vo1–vo4); `build_final_v5.sh` adds the end card (same llms.txt recipe)
and mixes VO + bed + clicks. Verified: 1080x1920, h264 + AAC, 42.53s,
17,694,922 bytes, mean -13.8 dB / max -0.0 dB. QC frames: 0.5s badge +
typing, 4.0s profile clean, 28.0s leaderboard clean (header + gold #1 +
3509), 39.6s code mid-type ("by"), 42.0s full `bye4mn13` + play code +
join lines. v3 is kept as `ad-v3.mp4` in this repo.

One fix round during the build: the first render had the brand badge
overlapping the intro headline and the leaderboard panel header (badge
alpha bbox x 120–450, y 272–400, measured from the file). Fixed by moving
the intro headlines below the badge (y 440/570, card to y 740), the
leaderboard headline to y 100 and the panel to y 420, and by dropping the
comma from view numbers (the mono comma rendered with a gap; plain
"3509" matches the board). Note: `build_final_v5.sh` exits 1 only because
its final volumedetect grep runs under `-v error`, which suppresses the
volumedetect report; the encode itself succeeded and the levels were
verified in a separate pass.

---

## v6 — typography + 3D feel (22 Nov ~00:15 WIB, owner: "fontnya pake style font apaya yg bagus" + "kasih 3D feel")

Same video as v5 (42.53s, same scenes, same timing, same audio) — only the
fonts and the depth treatment changed. Rendered with `render_v6.py` (derived
from v5), assembled with `build_final_v6.sh`.

**Fonts (all free, OFL, from Google Fonts):**
- Headlines / display text / big numbers: **Anton** (heavy condensed
  display, `Anton-Regular.ttf`). Fallback Bebas Neue was not needed.
- Body text / smaller labels: **Montserrat ExtraBold**
  (`Montserrat-ExtraBold.ttf`). Fallback Inter ExtraBold / DejaVu Sans Bold
  was not needed.
- Referral-code field: still **JetBrains Mono Bold** — a code needs its
  fixed-width typing grid (mono char width 37.203px); Anton is not monospaced
  and would break the per-character positions.
- Glyph coverage verified with fontTools before rendering: Anton covers em
  dash, middle dot, apostrophe, digits, lowercase — no tofu. Leaderboard
  numbers stay plain digits with no comma (v5 fix kept).

**3D feel (tasteful depth, not clutter):**
- Extruded text: stacked offset shadow layers behind headline and number
  text (4px on LINES headlines, 3px on leaderboard header/rank/handle/views,
  2px on chips; black behind white text, dark amber behind INK text on the
  gold #1 row).
- Soft drop shadows under the profile card and the leaderboard panel
  (blurred dark rounded rect, offset +12/+16, blur 16).
- Beveled panel edges: light top/left, dark bottom/right, on the card and
  the panel.
- Subtle vertical depth gradient on the card and panel fills (top 1.18x
  lighter, bottom 0.85x darker).
- End card: drop shadow (2,3) on every drawtext (code chars, play code,
  join link). Animated scenes underneath unchanged.

**Verified:** 1080x1920, h264 + AAC, 42.533333s, 18,058,739 bytes, mean
-13.8 dB / max -0.0 dB (identical to v5, no clipping). Render: 1,216
frames, 270 typing events, typing schedule identical to v5 (v5 clicks stay
in sync). QC frames: 0.5s badge + typing, 4.0s profile clean (avatar circle,
Anton handle with extrusion, card drop shadow visible), 14.0s bounty page +
"make.fun IS WHERE" typing, 28.0s leaderboard clean (header + gold #1 +
3509, em dash renders), 37.0s close lines typing, 39.6s code mid-type
("bY"), 42.0s full `bye4mn13` + play code + join lines readable. v5 is
kept as `ad-v5.mp4` in this repo.

**Note:** `build_final_v6.sh` exits 1 only because its final volumedetect
grep runs under `-v error`, which suppresses the volumedetect report (same
v5 quirk); the encode succeeded and levels were verified in a separate pass
(mean -13.8 / max -0.0).

---

## v7-alt (comparison version, built from scratch — NOT the posting version)

**Purpose:** an alternate take of the same 4-beat arc (same order: profile
intro, what-is-make.fun, rank-1 leaderboard proof, CTA), built from zero so
the owner can compare it against approved v6 and pick. v6 stays the posting
version; `ad.mp4` was never touched. Rendered with `render_v7alt.py` (own
script, same LINES text/starts as v5 so the typing schedule is identical),
assembled with `build_final_v7alt.sh`. Output `ad-alt.mp4` in this repo.

**Style — "daylight pop" (the opposite of v6's dark ink):** light ivory
background (#F4F8F5) with a faint magenta/cyan dot grid, bold magenta
(#C41C83) and cyan (#00A8C6) accents, gold (#F5C542) for the #1 row and the
prize badge. Sticker treatment everywhere: white cards with thick ink
borders, drop shadows, slight rotations, layered sticker-stack typing pills.
The mascot is a sticker (thick white + ink outline) instead of v6's flat
mark; the badge uses the light-ground lockup (`lockup-2400.png`, ink
wordmark + magenta disc) because the white/magenta lockup is invisible on a
light background. 3D depth is kept in the light style: extruded text
(4px headlines, 3px leaderboard header/rank/handle/views, 2px chips),
blur-16 drop shadows, bevels, vertical depth gradient (top 1.18x, bottom
0.85x).

**Fonts (all free, OFL, from Google Fonts — deliberately different from v6):**
- Headlines / display / big numbers: **Bebas Neue** (tall condensed,
  `BebasNeue-Regular.ttf`, 61,400 B) — visibly different from v6's Anton.
- Body / small labels: **Poppins Bold** (`Poppins-Bold.ttf`, 155,996 B) —
  different from v6's Montserrat ExtraBold. The end-card play code and join
  link use Poppins Bold (same as v6's card).
- Referral code: still **JetBrains Mono Bold** — the typing grid needs a
  fixed width (37.203 px/char); same reason as v6.
- Glyph coverage verified with fontTools before rendering (Bebas + Poppins):
  em dash, en dash, middle dot, apostrophe, digits, lowercase — no tofu.

**Motion — a different, wilder recipe than v6 (owner: super festive, must
NOT reuse v6's motion):** v6 = frame pump 2.8%/beat, white flashes, typing,
eased dissolves, mascot dance. v7-alt = elastic bounces with overshoot on
every beat (panel scale 1 + 3% elastic, rows pop in with ease-out-back),
sticker pop-ins with rotation (cards rotate in -4deg to +2deg, pills tilt
-2deg/+2deg), confetti bursts on the drops (9s, 13s, 18.5s, 24s, 32.5s),
exaggerated squash-and-stretch (1.25x/0.75x on the mascot every beat, v6
was 1.12/0.86), zoom punches on the hard cuts (9.0s, 13.5s, 18.5s, 24.0s,
32.5s), colorful flashes (magenta on odd beats, cyan on even beats —
never plain white), spinning/tilting elements (mascot 360deg spin-in at
18.5s, trophy 360deg spin-in at 24.1s, $100 badge pop-in with rotation at
24.45s). Text stays legible throughout; nothing covers the badge, the
referral code, or the play code.

**Leaderboard scene — podium celebration:** a gold trophy (PIL-drawn,
bold silhouette with 3D shine + star sparkle, `trophy.png` 300x420, no
emoji, no stock image) spins in at 24.1s next to the #1 row, and a gold
"1ST PRIZE $100" badge pops in at 24.45s (1st place = $100 USDC, verified
from the competition payout curve). The #1 view count counts up 0 to 3509
over 2.2s (24.3s to 26.5s, ease-out). **Paper rain: 96 pieces** — 40 burst
at the 24.0s reveal drop (pre-scattered through the top half) + 56 trickle
at 7/s until 32.5s; every piece has its own speed, spin, drift, size
(8-16px) and colour (gold/white/magenta/cyan/ink), fluttering and rotating
as it falls. Exclusion rects keep the pieces off the headline, the
trophy/$100 badge, the panel header, the rank+handle and views columns,
the footer, and "AND STILL CLIMBING." — rank numbers, view counts, trophy
and badge stay fully readable. (QC fix: the trophy was first centred at
(445, 285), which put its cup behind the headline pill — moved to centre
(505, 305) at 90x126, headline lifted to y80, badge to centre (700, 305);
re-rendered and re-QC'd.)

**Scene 3 — drawn bounty card, not a screenshot:** the light screenshot
we had (`competition-light.png`) turned out to be a DIFFERENT bounty (a
pump.fun trading-bot bounty, $1,325), not bring-the-humans-03. A
headless-Chromium re-shoot of the real page failed in this VM
(ERR_TUNNEL_CONNECTION_FAILED; no browser available to a subagent), so
scene 3 is a PIL-drawn sticker-style bounty card (`make_scene3_drawn.py`)
carrying the REAL humans-03 facts (verified from the competition API
payout curve): $500 prize pool, 20 places paid, 1st $100 / 2nd $70 /
3rd $50 / 4th-10th $20 / 11th-20th $14, closes Nov 25, 2:00 AM WIB, URL
make.fun/bounty/bring-the-humans-03. v6 keeps the real page screenshot;
the alt's card is a deliberate style choice and shows the right bounty.

**Fresh numbers (fetched 22 Nov ~00:21 WIB, live API):** leaderboard
#1 tyrmeapart 3509, #2 jclaw 3327, #3 drelat 3127, #4 seriwinda24-del
2972, #5 zyschiee 2822, 1729 entries total; profile 82 entries, referral
bye4mn13. Audio reused as-is from v5/v6 (bed_v5.wav + VO files, no
re-recording); duration stays 42.53s.

**Verified:** 1080x1920, h264 + AAC, 42.533333s, 19,575,708 bytes, md5
ae166a92628243f5f7e4934f265ee2ef, mean -13.8 dB / max -0.0 dB (identical
to v5/v6, no clipping). Render: 1,216 frames, 270 typing events, typing
schedule identical to v5 (v5 clicks stay in sync). QC frames (v2 build):
0.5s badge + typing, 4.0s profile clean (avatar circle, Bebas handle with
magenta extrusion, chips), 9.5s board card + confetti burst, 11.0s
"MEANWHILE, OTHER AGENTS ARE WINNING REAL MONEY." complete, 14.0s drawn
bounty card + "MAKE.FUN IS AI AGENTS FOR REAL" typing, 19.0s mascot
mid-spin, 21.0s "CODE · TRADE / BUILD · CREATE" + settled mascot, 25.0s
trophy fully visible + $100 badge + count-up mid-flight (2396, correct
per the 2.2s ease), 28.0s leaderboard settled (3509, all rows legible,
papers thinning), 30.0s papers at panel edges, 34.0s close lines typing,
37.0s "ENTER Y / IN A" typing, 39.6s code mid-type, 42.0s full `bye4mn13`
+ play code + join lines readable. v6 stays as `ad.mp4` in this repo.

## v8-alt — greeting animation (22 Nov ~01:00 WIB, owner: "skrg klo ava lu di bikin bergerak bisa ga? sm maskot makefun jg dibikin bergerak, kaya ngesapa penonton")

v7-alt plus a greeting. Same 4-beat arc, same daylight-pop look, same fonts,
same audio (v5/v6 bed + VO, no re-recording), same 42.53s duration — the
greeting fits inside the existing intro timing, nothing extended.

**Cold open, 0–3s — avatar + mascot greet together:**
- Avatar (profile card): nods hello — extra ±9° tilt side to side + 12px
  vertical bob at ~1.4 Hz, envelope 0.3s in / 2.6s hold / 3.0s out, on top
  of the existing spin-in + beat wobble.
- Mascot (bottom-left peek): pops up 1.5x bigger, waves — ±12° tilt at
  ~1.7 Hz + little hops — then settles back to the normal peek by 3.0s.
- "HI!" speech bubble (PIL-drawn, white pill, ink outline, magenta Bebas
  text, tail pointing down-left at the avatar): pops in at 0.4s inside the
  profile card (top-right of the avatar, inherits the card motion), bobs,
  fades out 2.8–3.2s.
- Small PIL-drawn glove hand (white, ink outline, magenta cuff) next to
  the mascot, rotating ±25° like a wave, same 0.2–3.0s envelope.

**Dance open, 19.0–20.0s — mascot greets again:** right after the 360°
spin-in, the mascot tilts side to side ±14° at 2 Hz for one second, with a
"HI!" bubble at fixed (830, 470), fading in/out on the same envelope;
then the dance continues as in v7.

**Honest limit:** neither image has a real waving hand, so the greeting is
expressed through bob/tilt/nod + the HI bubble + the drawn glove hand —
not a literal hand wave. It reads clearly as a greeting anyway (verified
in QC frames 0.5/1.5/2.5/19.5).

**Verified:** 1080x1920, h264 + AAC, 42.533333s, 19,747,748 bytes, md5
96a88c24f4907ef5bbef17933bbc1321, mean -13.8 dB / max -0.0 dB (identical
to v5/v6/v7, no clipping). Render: 1,216 frames, 270 typing events, typing
schedule identical to v5 (v5 clicks stay in sync). QC frames: 0.5s badge +
typing + HI bubble already up + mascot peek with glove hand, 1.5s avatar
nod mid-tilt + HI bubble + mascot waving big, 2.5s same, 4.0s greeting
settled clean (bubble + hand gone, small peek back), 19.5s mascot mid-wave
+ HI bubble top-right + confetti, 28.0s leaderboard unchanged (trophy,
$100 badge, 3509, all rows legible), 42.0s end card full `bye4mn13` +
play code + join lines readable. v7 backed up as `ad-alt-v7.mp4` (md5
ae166a92628243f5f7e4934f265ee2ef, identical to the v7 original). v6 stays
as `ad.mp4` in this repo, untouched.

## v9 — Gemini-reference rebuild + pure white + alive (22 Nov ~01:07 WIB, owner: generated a 10s Gemini video, "bagus nih dia, tp cm 10 detik doang si bisa lu jadiin referensi nih sumpah" + "background harus PUTIH BERSIH" + "videonya harus terasa HIDUP")

v8-alt + Gemini-inspired touches, NOT a rebuild from scratch and NOT a
copy of the Gemini video. Same 4-beat arc, same timing, same text, same
audio (v5/v6 bed + VO, no re-recording), same 42.53s duration.

**What was taken from the Gemini reference (10s, 720x1280):**
- The avatar waving with a drawn hand; dense confetti from frame 0; a
  huge bold pink 3D headline; a big present mascot; the podium
  leaderboard with trophy + "1ST PRIZE $100" badge; the end-card layout.
- All of it rebuilt agent-made: PIL-drawn glove hands, PIL confetti,
  PIL 3D text, transforms of the OFFICIAL press-pack ghost art.

**What was deliberately NOT taken:**
- The Gemini leaderboard is FAKE — AI-hallucinated names and numbers
  (jooketta110, jomu3723, etc.). v9 uses REAL live leaderboard data only
  (see below). The Gemini 3D ghost is a DIFFERENT ghost, not the official
  make.fun mascot — v9 keeps the official press-pack ghost
  (`sticker_mascot.png`), transforms only, never redrawn. No frames or
  images from the Gemini video appear anywhere in the output.

**Pure white (owner correction):** every PIL-drawn surface is now pure
white #FFFFFF — page background, profile card, leaderboard panel, row
backgrounds (neutral light gray #EEEEF0, not cream). The cream the owner
saw in the v8 screenshot was the ivory page bg (255,246,232) + the
white-to-warm-cream card/panel gradients. The scene cards were already
white. The end card is unchanged: it is the official magenta press-pack
referral card (full-bleed), not a page surface.

**Flash / sparkle kept:** confetti, flash and twinkle all stay — the base
flash amplitude was lowered slightly (48 -> 30) so the white background
still reads white between pulses, and 36 PIL-drawn 4-point star twinkles
were added in the empty bands (side margins, top + bottom strips),
pulsing on the beat. The scene-cut flash punch is unchanged.

**Gemini touches in v9:**
- Avatar glove hand: the avatar gets its own PIL-drawn waving glove
  (white, ink outline, magenta cuff — same style as the mascot's glove),
  flipped so the thumb points toward the avatar, left of the circle,
  same 0.3-3.0s greeting envelope.
- Denser confetti: ambient rain of 70 small pieces the whole video (20
  pre-scattered so frame 0 is already dense) + a confetti burst at t=0 +
  80 pieces per scene-cut burst (was 50). Never over the badge, typed
  pills, avatar face, or the leaderboard panel rows.
- Intro headline bigger + bolder pink 3D: Bebas 124 (was 112), magenta
  fill, deep plum extrude, depth 6. The two pills now sit cleanly stacked
  (tighter pad, no tilt) instead of overlapping.
- Mascot bigger + 3D: dance size 380 (was 320), soft drop shadow (alpha
  mask, blurred, offset down-right) on every mascot paste.

**ALIVE (owner: "videonya harus terasa HIDUP"):**
- Greeting 0-3s with bigger amplitude: avatar nod +/-14deg (was 9) +
  18px bob (was 12) + 8% scale-up toward the camera; mascot wave
  +/-18deg (was 12) + higher hops, 1.7x size (was 1.5x); HI bubble pops
  with a bounce + beat pulse.
- Nobody ever stands still: avatar has a slow breathing scale (2%,
  2s period) on top of the beat wobble; mascot peeks have a slow hover
  (8px, 1.6s period) on top of the beat bob.
- Mascot reacts: scene-2 peeks are BIG (260) and sit right under the
  headline, leaning toward it, floating; the mascot pops in with the
  leaderboard panel, floats at the bottom-left, and CELEBRATES when the
  count-up lands on our views (26.58s) — a 360deg spin + a hop, then a
  wave; it waves again at 36.8-38.0s, just before the end card washes in
  (the card itself is the opaque magenta press-pack card, so nothing
  from the clip shows during 38.0-40.5s).
- Avatar in the intro is slightly bigger during the greeting (8% scale)
  and centred, facing the camera.

**Fresh numbers (fetched live 22 Nov ~01:18 WIB, just before rendering):**
leaderboard #1 jclaw 3604, #2 tyrmeapart 3509, #3 seriwinda24-del 3420,
#4 gm-xbt 3325, #5 zyschiee 3219, 1753 entries total; profile 82 entries,
referral bye4mn13. Our row is highlighted gold wherever it sits (not
rank 1); the count-up targets OUR views (3,509). The profile chip reads
"3509 VIEWS" (honest) instead of "#1 GTA CLIPPER".

**KNOWN ISSUE — read before picking this version:** on the board at
render time we are #2 (jclaw 3,604, our board read 3,509 still lags our
public YouTube count, which was 3,735 at 00:57 WIB and climbing). The
panel shows the real top 5 — but the (unchanged) VO and the typed line
still say "WE'RE NUMBER ONE." / "we are number one". That is a visible
contradiction inside this version: the panel says #2, the voice says #1.
v8 (rendered 00:21 WIB, when the board said #1) has no such contradiction.
If the board flips back to #1 before posting, the contradiction disappears
in substance — but as rendered, v9's panel is #2. Pick with eyes open.

**Honest limits:** no image has a real waving hand — both waving hands
are PIL-drawn gloves; the greeting is nod/tilt/bob + HI bubble + glove.
The mascot is the official art, transforms only. The end-card wave is in
the 1.2s before the opaque card, not during the card itself.

**Verified:** 1080x1920, h264 + AAC, 42.533333s, 21,138,235 bytes, md5
d5553bfd72f7e38aba6c2646370b44e3, mean -13.8 dB / max -0.0 dB (identical
to v5/v6/v7/v8, no clipping). Render: 1,216 frames, 270 typing events,
typing schedule identical to v5 (diff clean, v5 clicks stay in sync).
QC frames: 0.5s badge + typing + HI bubble + mascot peek with glove
hand + dense confetti from frame 0, 1.5s avatar nod mid-tilt + HI bubble
+ avatar glove hand + mascot waving big, 2.5s opposite wave phase (the
greeting reads across frames), 4.0s greeting settled clean, 11.0s board
card + big mascot under the headline, 19.5s mascot mid-wave + HI bubble
+ confetti, 26.8s leaderboard settled (real top 5, our row gold at #2,
count-up 3509, mascot mid-celebration-spin), 28.0s trophy + $100 badge +
1753 entries, 37.0s close wave before the end card, 42.0s end card full
`bye4mn13` + play code + join lines readable. v6 stays as `ad.mp4`, v8
stays as `ad-alt.mp4`, both untouched. v9 is `ad-v9.mp4` in this repo.

---

## v10 — fresh #1 numbers, VO updated (22 Nov ~01:43 WIB, owner caught the v9 contradiction)

Owner (01:28 WIB): "kok bisa voice over ngmg number 1 tp di leaderboard number 2 wkwk" — proposed reframing as rank 2 now ($70 est.) with confidence of rank 1 tomorrow ($100). The brief therefore asked for a re-recorded VO6 ("Right now we're number two — seventy dollars. But tomorrow, we're taking number one — a hundred dollars.") + new headline ("RIGHT NOW WE'RE #2 — $70. TOMORROW WE TAKE #1 — $100.").

**Board flipped while building.** Fresh API fetches at ~01:30 and ~01:31 WIB (two consecutive reads) + the owner's own screenshot at 01:37 WIB all agree: we are #1 again — tyrmeapart 3,814, jclaw 3,623. The parent's decision rule (fetch fresh right before render, match VO to panel) therefore resolves to branch (a): keep the #1 claim. Using the brief's #2 lines against a #1 panel would have created the SAME contradiction inverted (VO says #2, panel says #1), so v10 does NOT use the #2 reframe. Everything is in English, as the owner affirmed. If the board flips back to #2 before posting, the #2 reframe remains a valid re-render — but as rendered, v10 is internally consistent: VO says #1, panel says #1, chip says #1.

**Changes vs v9 (only these):** fresh leaderboard (#1 tyrmeapart 3,814, #2 jclaw 3,623, #3 seriwinda24-del 3,531, #4 gm-xbt 3,456, #5 drelat 3,383, 1,758 entries total); VO6 re-recorded with `/opt/hatch/bin/tts`, voice `avocado_v2:casper` (same voice as vo1–vo6), new line: "And right now, we are number one. Three thousand eight hundred and fourteen views on our GTA 6 clip." (8.04s, fits the 24.0–32.5s slot; old VO6 was 7.51s). Headline unchanged ("WE'RE NUMBER ONE." + "AND STILL CLIMBING.") — now TRUE against the panel. Profile chip reads "#1 GTA CLIPPER" again (the code shows the chip only while we hold #1). Count-up targets 3,814 (lands 26.4s, mascot celebrates then). Everything else is v9: pure white #FFFFFF, dense confetti from frame 0, big pink 3D headline, avatar glove hand, big mascot with shadow, alive motion, podium + trophy + "1ST PRIZE $100" badge, end card, bed + all other VOs identical.

**Verified:** 1080x1920, h264 + AAC, 42.533333s, 21,291,706 bytes, md5 2fc2d960df10daf7c9eac1b4907095fd, mean -13.8 dB / max -0.0 dB (identical to v5/v6/v7/v8/v9, no clipping). VO segment 24–32.5s mean -12.9 dB (voice present and audible). Render: 1,216 frames, 270 typing events, typing schedule identical to v5 (diff clean, clicks_v5.wav stays in sync). QC frames: 1.5s greeting clean (avatar nod + glove + HI bubble + "#1 GTA CLIPPER" chip + mascot peek), 25.0s headline typing mid-flight + count-up mid-flight (2,831 → 3,814), 28.0s leaderboard settled (gold #1 row 3814, full real top 5, 1758 entries, "AND STILL CLIMBING."), 42.0s end card full `bye4mn13` + play code + join lines readable. ad.mp4 (v6), ad-alt.mp4 (v8), ad-v9.mp4 untouched. v10 is `ad-v10.mp4` in this repo.
