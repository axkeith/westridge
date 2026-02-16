# Westridge Modpack

Westridge is a meticulously curated Minecraft 1.21.11 modpack designed to enhance the vanilla experience with quality-of-life improvements, performance optimizations, and subtle feature expansions.

## Key Features

- **Performance Focused:** Built on Fabric/Quilt for maximum FPS and stability.
- **Audio Overhaul:** Enhanced soundscapes for a more immersive atmosphere.
- **Social Integration:** Integrated voice chat for seamless communication.
- **Managed with Packwiz:** Easily update and manage mods using the efficient `packwiz` tool.

## Mod Overview

Westridge is a heavy "Vanilla+" pack with **129 mods** focused on extreme performance and deep immersion.

### Core Features
- **🚀 Performance:** Powered by `Sodium`, `Lithium`, `VMP`, and `C2ME` for maximum frames and chunk generation speed. `BadOptimizations` and `ModernFix` ensure a smooth experience even on lower-end hardware.
- **🎧 Immersive Audio:** Uses `AmbientSounds`, `Sound Physics Remastered`, and `AudioPlayer` to create a living, breathing soundscape with realistic reverbs and custom music support.
- **✨ Visual Overhaul:** Includes `Iris Shaders` (`MakeUp - Ultra Fast Shaders`), `Distant Horizons` for LOD rendering, `Continuity` for connected textures, and `Visuality` for atmospheric particles.
- **🛠️ Power-User Utilities:** Features like `Tweakeroo`, `Litematica`, `MiniHUD`, and `Inventory Profiles Next` provide advanced tools for technical players.
- **🗺️ Navigation:** A full mapping suite with `Xaero's Minimap`, `World Map`, and `Better Nether Map`.
- **💬 Social:** `Simple Voice Chat` for proximity communication and `Chat Heads` for a better multiplayer experience.

For the **full list of all 129 mods** with descriptions, check out the [Full Content Wiki](https://github.com/axkeith/westridge-mc/wiki/Content).

## Installation & Updates

### Client (Prism, MultiMC, ATLauncher)
These launchers support custom commands to automatically sync the pack using `packwiz-installer`.

1. **Create Instance:** Create a Minecraft 1.21.11 Fabric instance.
2. **Edit Instance:** Go to `Settings` -> `Custom Commands` (or `Pre-launch`).
3. **Pre-launch Command:** Add the following to automatically sync the pack:
   ```bash
   "$INST_JAVA" -jar packwiz-installer-bootstrap.jar https://github.com/axkeith/westridge-mc/raw/main/pack.toml
   ```
   *(Ensure `packwiz-installer-bootstrap.jar` is in your instance's `.minecraft` directory or provide the full path).*

### Other Launchers
For launchers without custom pre-launch commands:
- Manually run the `packwiz-installer-bootstrap.jar` using the command above in your instance's `.minecraft` directory before launching.
- Alternatively, download and extract the modpack files manually from the [releases page](https://github.com/axkeith/westridge-mc/releases).

## Server Setup

### Regular (Manual)
1. **Download:** Get the latest Fabric Loader for 1.21.11.
2. **Sync:** Use `packwiz-installer` to pull the modpack (server-side only):
   ```bash
   java -jar packwiz-installer-bootstrap.jar -g -s server https://github.com/axkeith/westridge-mc/raw/main/pack.toml
   ```
3. **Launch:** Run `java -jar fabric-server-launch.jar`.

### Docker (Recommended)
The `itzg/minecraft-server` image able to handle mod sides automatically via its `packwiz` integration.

- **Automatic Filtering:** By default, the image uses `packwiz-installer` logic to skip client-only mods based on your `pack.toml` configurations.
- **Extra Control:** You can explicitly pass flags using the `PACKWIZ_FLAGS` environment variable if needed.
- **Example `docker-compose.yml`**:
  ```yaml
  services:
    minecraft:
      image: itzg/minecraft-server
      environment:
        TYPE: FABRIC
        VERSION: 1.21.11
        PACKWIZ_URL: https://github.com/axkeith/westridge-mc/raw/main/pack.toml
  ```

## Project Structure

- `mods/`: Contains the packwiz `.pw.toml` mod definitions.
- `index.toml`: The main index of the modpack.
- `pack.toml`: General pack information.
- `wiki/`: Technical documentation and guides.
