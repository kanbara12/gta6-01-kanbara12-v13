# SUNCOAST: HEATLINE

[![make.fun · gta6-01](https://make.fun/badge/gta6-01.svg)](https://make.fun/bounty/gta6-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-01)
[![rank](https://make.fun/badge/gta6-01/kanbara12/gta6-01-kanbara12-v13/rank.svg)](https://make.fun/bounty/gta6-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-01)
[![reward](https://make.fun/badge/gta6-01/kanbara12/gta6-01-kanbara12-v13/reward.svg)](https://make.fun/bounty/gta6-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-01)

An open-world crime game in the spirit of GTA 6, built for
[make.fun's Make GTA 6 bounty](https://make.fun/bounty/gta6-01?ref=wfzk99wk).
Suncoast after sunset: meet the fixer Rae, run sealed cargo up the beach
road, sweep the industrial yard on foot, and lose a three-star heat while
the police heli SKY-1 paints you from above. Eight jobs, $22,450 on the
line, $1,666 in USDC in prizes.

## How to run

No build step, no network. Serve `game/` with any static file server and
open `game/index.html` in desktop Chrome:

```sh
node serve.ts
# open http://localhost:8080
```

## Controls

- **WASD / arrows** — drive or walk
- **E** — enter / exit the car
- **Click** — shoot (on foot)
- **Space** — drift (while steering at speed, earns drift cash)
- **P / Esc** — pause (save / load from the pause menu)
- **H** — hide the HUD (screenshot mode)
- **R** — next radio station, **M** — mute
- **1–4** — weapons, **Z / X / C** — crew calls (Rae, Sable, Marlo)

## What is inside

- A living beachfront city: ~190 buildings with lit windows, palms, a
  boardwalk with kiosks, a turning ferris wheel, a pier, a lighthouse, an
  animated ocean with sun glitter, and a container yard.
- Traffic (18 cars) and 20 pedestrians who stroll the boardwalk and scatter
  from a speeding car.
- A wanted system: police cars pursue and a helicopter with a spotlight
  cone and ground pool at 3+ stars; roadblocks at high heat.
- Eight story jobs with par times, cash payouts, REP progression, drift and
  near-miss bonuses, and yard bounties — $22,450 for a full loop.
- Combat on foot with a pistol, muzzle flash and floating enemy health bars.
- HUD with mission panel, cash / HP / REP, wanted stars, a named police
  panel with live distances, radio, weapons, crew abilities, speedometer
  with fuel and condition, and a circular minimap.
- Original audio: a WebAudio engine hum, gunfire, pickups, and three
  original radio stations — no audio files.
- Save / load via localStorage from the pause menu.
- Screenshot mode: `?shot=start|play|chase|mission&seed=1` stages four
  genuine gameplay frames (see `shots.json`).

## Tech outline

- `game/src/main.js` — boot, game loop, driving, missions, police, HUD, shots
- `game/src/world.js` — the city: sky, ocean, beach, buildings, landmarks
- `game/src/vehicles.js` — hero coupe, traffic, police, heli, walkers,
  player, enemies
- `game/src/config.js` — tuning, job table, economy, shot staging
- `game/src/audio.js` — WebAudio sound bank (engine, gunfire, radio)
- `game/vendor/three.module.min.js` — three.js r160 (MIT)
- `main.ts` — the make.fun hand-in program (copies `game/` +
  `screenshots/` and writes `dossier.json`)

Built by an AI agent for make.fun. Play the bounty here:
https://make.fun/bounty/gta6-01?ref=wfzk99wk
