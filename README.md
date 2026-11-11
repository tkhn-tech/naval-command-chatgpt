# Naval Command — Three.js PvE Fleet Sandbox

A browser-playable Three.js naval-combat prototype. The standalone game is served directly from `index.html` and uses Three.js modules from jsDelivr CDN; no local build step is required to play or host the prototype.

> This is a playable systems prototype, not a finished commercial naval game. Ships, islands, sky and effects are procedural stand-ins. The current browser build is a compact playable implementation; the deeper modular architecture and production-grade simulation remain future engineering work.

## Play locally
Open `index.html` through a local static server (ES modules generally require HTTP):

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Controls
- W/S: throttle; A/D: rudder
- Tab: switch selected friendly ship
- 1/2/3: Line Ahead / Echelon / Broadside Line
- F or Space: main battery; G: homing torpedo
- Click the ocean: set a fleet waypoint
- Use the panels for ship selection, weather and formation spacing

## Current prototype features
- Y-up Three.js scene, procedural ocean surface and six Gerstner-style wave bands
- Storm and sea-state controls that affect waves, visibility and lighting
- Three friendly vessels with formation steering and direct helm control
- Two hostile AI vessels that approach and engage the fleet
- Main-battery projectiles, homing torpedoes and hull damage
- Vessel status, speed, flooding and capsize readouts
- ACES tone mapping, bloom and SMAA post-processing

## Engineering scope
This is a game-oriented approximation, not validated naval architecture software. The current implementation is a compact browser prototype. Production next steps include splitting the runtime into the proposed decoupled systems (OceanEnvironment, WarshipPhysicsController, FleetCommandSystem, NavalCollisionSystem and ScenePostProcessing), authored GLTF ship assets, calibrated hull coefficients, a spatial collision broadphase, dedicated armour/weapon systems, mobile performance tiers and deterministic networking.

World up is +Y; ship forward is local +Z. Distances are meters and time is seconds.

## License
MIT. Three.js is separately licensed under MIT.
