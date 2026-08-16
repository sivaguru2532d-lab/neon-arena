# NEON ARENA — Project Structure

```text
NEON-ARENA/
├── src/
│   ├── main.tsx                  # Existing website entry point
│   ├── styles.css                # Global accessibility/base styles
│   └── neon-arena/
│       ├── NeonArena.tsx         # Menus, HUD, profile, settings, tutorial
│       ├── engine.ts             # Game loop, rendering, AI, combat, arena
│       ├── audio.ts              # Generated sound effects and music
│       ├── maps.ts              # 10 maps, hazards, unlocks, 6 AI levels
│       ├── types.ts              # Shared TypeScript interfaces
│       └── neon.css              # Responsive game and UI styling
├── server/
│   └── index.ts                  # Production server + multiplayer scaffold
├── tests/
│   ├── neon-test.ts              # Engine integration tests
│   └── browser-debug.mjs         # Desktop/mobile browser test suite
├── standalone/
│   └── NEON-ARENA.html           # Self-contained playable browser build
├── index.html                    # Website HTML entry
├── package.json                  # Commands and dependencies
├── package-lock.json             # Reproducible dependency versions
├── tsconfig.json                 # TypeScript configuration
├── vite.config.ts                # Vite development/build configuration
├── Dockerfile                    # Production container deployment
├── .dockerignore                 # Container exclusions
├── README.md                     # Setup, controls, and architecture
└── PROJECT_STRUCTURE.md          # This structure guide
```

Generated directories such as `node_modules` and `dist` are intentionally excluded. Run `npm install` and `npm run build` to generate them.
