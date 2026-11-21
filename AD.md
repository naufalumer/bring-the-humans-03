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
