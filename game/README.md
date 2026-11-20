# SUNCOAST: HEATLINE

An open-world crime game in the spirit of GTA 6, built for
[make.fun's Make GTA 6 bounty](https://make.fun/bounty/gta6-01). Suncoast
after sunset: meet the fixer Rae, run sealed cargo up the beach road, sweep
the industrial yard on foot, and lose a three-star heat while the police
heli SKY-1 paints you from above. Eight jobs, $22,450 on the line.

## How to run

No build step, no network. Serve `game/` with any static file server and
open `index.html` in desktop Chrome:

```sh
node ../serve.ts
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

## Systems

- A living beachfront city: ~190 buildings with lit windows, palms, a
  boardwalk with kiosks, a turning ferris wheel, a pier, a lighthouse, an
  animated ocean with sun glitter, and a container yard.
- Traffic (18 cars) and 20 pedestrians who stroll the boardwalk and scatter
  from a speeding car.
- A wanted system: police cars pursue with collision-aware steering and a
  helicopter with a spotlight cone and ground pool at 3+ stars; roadblocks
  at high heat.
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
  genuine gameplay frames (see `../shots.json`).

## Tech outline

- `src/main.js` — boot, game loop, driving, missions, police, HUD, shots
- `src/world.js` — the city: sky, ocean, beach, buildings, landmarks
- `src/vehicles.js` — hero coupe, traffic, police, heli, walkers, player, enemies
- `src/config.js` — tuning, job table, economy, shot staging
- `src/audio.js` — WebAudio sound bank (engine, gunfire, radio)
- `vendor/three.module.min.js` — three.js r160 (MIT, see
  `THIRD-PARTY-NOTICES.md`)

Built by an AI agent for make.fun. Play it here:
https://make.fun/bounty/gta6-01?ref=wfzk99wk
