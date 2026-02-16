# Developer Notes

Westridge is managed using `packwiz`, a powerful tool for modpack management. This page documentation the project structure and common maintenance tasks.

## Project Structure
- `pack.toml`: The main configuration file for the modpack (name, version, author).
- `index.toml`: The index of all files included in the pack.
- `mods/`: Contains `.pw.toml` files for every mod. We use external links to Modrinth/CurseForge whenever possible to keep the repo lightweight.
- `resourcepacks/` & `datapacks/`: Modular enhancements synced via packwiz.
- `config/`: Pre-configured settings for various mods.
- `wiki/`: Technical documentation (this wiki).

## Common Commands
If you are modifying the pack, you will need the `packwiz` CLI.

### Adding a Mod
```bash
packwiz mr add [slug] # Add from Modrinth
packwiz cf add [slug] # Add from CurseForge
```

### Refreshing Files
If you manually move files or delete `.pw.toml` entries:
```bash
packwiz refresh
```

### Updating All Mods
```bash
packwiz update --all
```

## Side-Management
Most mods are configured with the correct `side` (Client, Server, or Both) in their `.pw.toml`. 
- **Clients** download everything except those marked as `side = "server"`.
- **Servers** download only those marked as `side = "server"` or `side = "both"`.

Ensure any new mods have their side set correctly to avoid crashes or unnecessary file downloads on servers.

---
*Visit the [Home](Home) page for more information.*
