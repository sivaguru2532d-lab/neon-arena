# NEON ARENA

A complete, lightweight top-down browser survival game integrated into the existing React/Vite application, presented with a detailed retro-pixel tactical command interface.

## Play

```bash
npm install
npm run dev
```

Production:

```bash
npm run build
npm start
```

Open `http://localhost:3001` in production or the Vite URL in development.

## Gameplay

Survive a 3.5-minute shrinking cyberpunk arena against seven tactical bots. Collect six power-up types, use cover, avoid dangerous zones, and eliminate every opponent.

### Controls

- Desktop: WASD/arrows, mouse aim, left-click attack, Space dash, P/Escape pause
- Mobile: virtual movement joystick, Attack button with automatic nearest-target aim, Dash button

## Architecture

- `src/neon-arena/engine.ts` — fixed-world game loop, actors, collision, AI, projectiles, power-ups, zone, rendering
- `src/neon-arena/NeonArena.tsx` — menus, HUD, profile, results, settings, tutorial, progression
- `src/neon-arena/audio.ts` — generated Web Audio effects and ambience
- `src/neon-arena/types.ts` — shared game contracts
- `src/neon-arena/maps.ts` — five genuinely different map definitions, unlocks, palettes, hazards, and six AI protocols
- `src/neon-arena/neon.css` — responsive premium interface
- `server/index.ts` — production static server and versioned WebSocket transport scaffold
- `server/neon-test.ts` — gameplay-system integration test

Progression, settings, per-map records, unlocks, selected AI rewards, XP, coins, wins, and kills persist in localStorage. Five battlefields use different collision polygons, route networks, obstacle geometry, combat distances, visual environments, hazards, and timed special events. Six AI protocols alter reaction time, prediction, accuracy, cover use, dodging, retreat, flanking, power-up strategy, and hazard awareness without unfair health or damage boosts. The engine is separated from React and input transport, allowing a future authoritative multiplayer adapter without rewriting rendering or UI.

## Validation

```bash
npm run build
npm test
```

The automated integration test validates player movement, projectile collision, health power-ups, shrinking-zone behavior, and the victory condition.
