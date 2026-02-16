# Installation Guide

Westridge is built on Fabric 1.21.11 and is optimized for launchers that support automated `packwiz` updates.

## Recommended Launchers
Launchers with "Custom Commands" or "Pre-launch" scripts are recommended as they can automatically sync the modpack every time you play.

### Prism / MultiMC / ATLauncher
These launchers allow you to keep the pack updated automatically using `packwiz-installer-bootstrap`.

1. **Create Instance**: Create a new instance for Minecraft **1.21.11** with the **Fabric Loader** (latest version).
2. **Setup Tools**: Download [packwiz-installer-bootstrap.jar](https://github.com/packwiz/packwiz-installer-bootstrap/releases/latest) and place it in your instance's `.minecraft` folder.
3. **Configure Sync**:
   - Go to **Edit Instance** -> **Settings** -> **Custom Commands** (or **Pre-launch**).
   - Enable "Pre-launch command" and enter:
     ```bash
     "$INST_JAVA" -jar packwiz-installer-bootstrap.jar https://github.com/axkeith/westridge-mc/raw/main/pack.toml
     ```
4. **Launch**: Every time you launch, the pack will check for updates and download any new mods or config changes automatically.

---

## Alternative Launchers
If your launcher does not support pre-launch commands (like the default Minecraft Launcher or CurseForge), you can still install Westridge.

### Manual Download (Releases)
1. Go to the [Releases](https://github.com/axkeith/westridge-mc/releases) page.
2. Download the latest `Westridge-vx.x.x.zip`.
3. Extract the contents into your `.minecraft` directory.
4. Launch with the Fabric 1.21.11 loader.

### Manual Sync (Advanced)
If you want to stay up-to-date manually:
1. Open a terminal/command prompt in your `.minecraft` folder.
2. Run the same `java -jar` command listed in the Prism section above whenever you want to check for updates.

---
*Visit the [Home](Home) page for more information.*
