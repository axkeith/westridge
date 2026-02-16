# Server Setup

Westridge is designed to be highly efficient on the server-side, with many client-only mods automatically filtered out during sync.

## 🐳 Docker Deployment (Recommended)
This is the easiest way to host Westridge. We recommend the `itzg/minecraft-server` image.

### Example `docker-compose.yml`
```yaml
services:
  westridge:
    image: itzg/minecraft-server
    container_name: westridge-server
    environment:
      TYPE: FABRIC
      VERSION: 1.21.11
      MEMORY: 4G
      EULA: "TRUE"
      # Packwiz integration
      PACKWIZ_URL: https://github.com/axkeith/westridge-mc/raw/main/pack.toml
    ports:
      - "25565:25565"
    volumes:
      - ./data:/data
    restart: unless-stopped
```

**Note on Filtering:** The `itzg` image automatically uses `packwiz-installer` logic to skip mods marked as client-only in their `.pw.toml` files.

---

## 💻 Regular Server Setup (Manual)
If you are hosting on a dedicated machine or via a panel like Pterodactyl:

1. **Install Fabric**: Setup a Fabric 1.21.11 server environment.
2. **Download Sync Tool**: Get [packwiz-installer-bootstrap.jar](https://github.com/packwiz/packwiz-installer-bootstrap/releases/latest).
3. **Sync Content**: Run the following command in your server directory:
   ```bash
   java -jar packwiz-installer-bootstrap.jar -g -s server https://github.com/axkeith/westridge-mc/raw/main/pack.toml
   ```
   - `-g`: GUI-less mode.
   - `-s server`: Explicitly tells `packwiz` to only download server-compatible mods.
4. **Accept EULA**: Create/edit `eula.txt` and set `eula=true`.
5. **Start**: Run `java -jar fabric-server-launch.jar`.

---
*Visit the [Home](Home) page for more information.*
