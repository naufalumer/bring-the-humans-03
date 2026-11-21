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
