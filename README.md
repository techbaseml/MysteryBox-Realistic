# MysteryBox — The Hollow Manor (3D Starter)

A separate first-person 3D mystery-game project using Three.js. This does not modify the earlier `MysteryBox` project.

## Project files

- `index.html` — game shell, HUD, dialogs, language control, room menu
- `styles.css` — responsive cinematic HUD and touch-first layout
- `game.js` — Three.js scene, camera look, object raycasting, puzzle state, inventory, evidence, English/Malayalam text
- `assets/scenes/` — reserved for future high-resolution scene textures and image references
- `assets/objects/` — reserved for imported GLTF/GLB models and object textures
- `assets/audio/` — reserved for licensed ambience and sound effects

## Run on Android for testing

**Important:** this project loads Three.js as an ES module from jsDelivr. A network connection is required. Most Android file viewers cannot run ES modules from a `content://` URL reliably.

Recommended local test:
1. Copy the `MysteryBox-Realistic` folder to a computer or a local development environment.
2. Serve the folder over HTTP (for example, `python -m http.server 8000` from this directory).
3. Open `http://localhost:8000` in a browser on that device. For testing on a phone from another device on the same Wi-Fi, use the computer's LAN IP and port 8000.
4. Later, after explicit approval, the project can be published to GitHub Pages, which supports the module import.

No account connection, repository operation, or deployment was performed.

## Controls

- Drag on the scene to look around.
- Tap a scene object to inspect it.
- Use the room menu to switch to unlocked locations.
- The HUD includes objectives, evidence, inventory, hint and language toggles.

## Current playable slice

- Foyer: inspect clock/portrait and solve the front-door code (`815`).
- Study: solve the desk drawer (`SHADOW`), inspect the bookcase, take the book, open the hidden compartment, collect the brass key.
- Attic: the room menu unlocks after collecting the key; inspect the chest and enter `moon-eye-key`, then read Elias's note.
- Progress is stored in this browser using `localStorage`.

## Asset plan

This initial build uses procedural Three.js geometry and materials for a lightweight, self-contained 3D starter. For a higher-fidelity production build, add:
- optimized GLB/GLTF furniture and prop models with baked PBR textures,
- seamless wood, wallpaper, fabric and floor textures,
- room-specific baked lighting / light probes,
- licensed ambient sound, floor creaks, object interaction and door sounds,
- mobile texture compression (KTX2), mesh compression (Draco), and asset loading indicators.

Prefer small, optimized assets (e.g. 1K textures for most props, 2K only for hero objects), use compressed GLB, and test memory/performance on the target Android device.

## Limitations of this starter

- The scene is real-time 3D, but the first pass uses procedural low-poly geometry rather than photorealistic scanned assets.
- It is a playable foundation, not a finished photorealistic commercial game. Higher visual fidelity requires adding actual 3D models and textures to the `assets` folders.
- The Three.js CDN is external and needs internet access; no external account is connected.
