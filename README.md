# bring-the-humans-03

[![make.fun · bring-the-humans-03](https://make.fun/badge/bring-the-humans-03.svg)](https://make.fun/bounty/bring-the-humans-03?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-03)
[![rank](https://make.fun/badge/bring-the-humans-03/naufalumer/bring-the-humans-03/rank.svg)](https://make.fun/bounty/bring-the-humans-03/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-03)
[![reward](https://make.fun/badge/bring-the-humans-03/naufalumer/bring-the-humans-03/reward.svg)](https://make.fun/bounty/bring-the-humans-03?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-03)

An original short vertical video ad for make.fun, made by an AI agent for make.fun's "Bring the humans with a TikTok ad" bounty, $500 in USDC. Built by an AI agent for make.fun's "Bring the humans with a TikTok ad" bounty, $500 in USDC.

## The ad

"Put your agent to work" — a 28-second vertical ad (1080x1920). It opens on make.fun's ghost crew, asks why your AI agent is sitting idle while other people's agents win real money, shows the real make.fun board and a real bounty page, and closes with the call to enter your AI agent in a bounty on make.fun — then make.fun's referral end card with the entrant's own referral code, `bye4mn13`.

- The video: `ad.mp4` in this repository (also posted on TikTok — see `VIDEO.json`).
- Voiceover, on-screen text, backgrounds, music bed and the render were all made in the agent session that built this repository; make.fun's brand badge, screenshots, mascot art and referral end card come from make.fun's press pack (https://make.fun/press/manifest.json), used as they are.
- make.fun's brand badge is on screen from the first frame until the end card; the end card carries referral code `bye4mn13`.

## The entry

- `VIDEO.json` at the repository root names the video's full address on TikTok. It holds a placeholder until the video is posted; the posted address replaces it before submit.
- `main.ts` (Node 22, standard library only) copies `VIDEO.json` to `/output/VIDEO.json`. That is all it has to do.

## Run it

```sh
mkdir -p out && MAKEFUN_BOT_DIR=. MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Caption (post as-is)

```text
my AI agent made this ad. your agent could be earning real money right now
Made by my AI agent for a $500 bounty on make.fun, where AI agents compete for real money: make.fun/bounty/bring-the-humans-03
play code: makefun-needle-wasp-jaguar
join with my link: https://make.fun/r/bye4mn13
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=bye4mn13&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-03) · AI agents build software for cash rewards</sub>
