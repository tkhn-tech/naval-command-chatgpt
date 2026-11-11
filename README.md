# Naval Command — Three.js PvE Fleet Sandbox

A modular TypeScript/Three.js naval-combat prototype using a Y-up world. It includes a player-commanded three-ship fleet, two autonomous hostile vessels, a procedural radial ocean, weather controls, formation steering, hull impacts, compartment flooding, sinking, and cinematic post-processing.

> This is a playable systems prototype, not a finished commercial naval game. Ships, islands, sky, and effects are procedural stand-ins.

## Run locally
Requires Node.js 20.19+ or 22.12+.

```bash
npm install
npm run dev
```

Create a production build with `npm run build`; Vite outputs to `dist/`.

## Controls
- W/S: throttle; A/D: rudder
- Tab: switch selected friendly ship
- 1/2/3: Line Ahead / Echelon / Broadside Line
- F or Space: main battery; G: homing torpedo
- Click ocean: set fleet waypoint
- Use the side panels for ship selection, weather, and formation spacing

## Architecture
- `OceanEnvironment`: six synchronized Gerstner waves, CPU surface sampling, PBR water, foam, weather and sky.
- `WarshipPhysicsController`: 12 buoyancy nodes, hydrodynamic drag, damping, spray and flooding effects.
- `FleetCommandSystem`: fleet selection, formations, waypoint steering, obstacle avoidance and enemy AI.
- `NavalCollisionSystem`: hull contacts, impulses, damage and blast falloff.
- `Warship`: compartments, damage, flooding, fires and sinking.
- `ScenePostProcessing`: ACES tone mapping, bloom and SMAA.

## Engineering scope
This is a game-oriented approximation, not validated naval architecture software. Production next steps include authored GLTF ship assets, calibrated hull coefficients, a spatial collision broadphase, dedicated armour/weapon systems, quality tiers and deterministic networking.

World up is +Y; ship forward is local +Z. Distances are meters, time seconds, velocities m/s, mass kg and forces newtons.

## License
MIT. Three.js is separately licensed under MIT.
