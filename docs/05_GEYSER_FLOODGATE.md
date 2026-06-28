# 🌉 Geyser-Spigot + Floodgate-Spigot — Commands & Usage

**Geyser Wiki:** https://geysermc.org/wiki/geyser/  
**Floodgate Wiki:** https://geysermc.org/wiki/floodgate/  
**Purpose:** Geyser allows Minecraft: Bedrock Edition players (consoles, mobile, Windows) to join your Java Edition Paper server. Floodgate lets them do so without needing a Java account.

---

## What They Do

### Geyser-Spigot
- Acts as a **protocol bridge** between Bedrock and Java
- Translates all packets between both clients transparently
- Bedrock players connect on a **UDP port** (default: 19132)
- Requires no changes for Java players — they connect normally

### Floodgate-Spigot
- Optional companion plugin to Geyser
- Allows Bedrock players to join **without a Java Edition account**
- Handles Bedrock authentication independently
- Adds a prefix to Bedrock players' names (default: `.`) to avoid name conflicts with Java players
- Enables account linking between Java and Bedrock accounts

---

## Setup Overview

1. Both `.jar` files go in `plugins/`
2. In `plugins/Geyser-Spigot/config.yml`, set `auth-type: floodgate`
3. Bedrock players connect to your IP on **port 19132** (UDP)
4. Java players connect normally on your standard port

---

## Geyser Commands

All Geyser commands require OP or the `geyser.command.*` permission.

| Command | Description |
|---|---|
| `/geyser help` | Show all Geyser commands |
| `/geyser list` | List all currently connected Bedrock players |
| `/geyser reload` | Reload the Geyser configuration |
| `/geyser version` | Show Geyser version and check for updates |
| `/geyser dump` | Generate a debug dump (for bug reports) |
| `/geyser ping` | Show Geyser connection status |
| `/geyser offhand` | Swap a Bedrock player's main hand / offhand items |
| `/geyser statistics` | Show Geyser statistics |
| `/geyser advancements` | Open advancements menu for Bedrock players |
| `/geyser settings` | Open Geyser settings menu for Bedrock players |
| `/geyser connectiontest <ip> <port>` | Test if Bedrock connections are reachable (console) |
| `/geyser transfer <player> <ip> <port>` | Transfer a Bedrock player to another server |

---

## Floodgate Commands

| Command | Description |
|---|---|
| `/floodgate help` | Show all Floodgate commands |
| `/floodgate version` | Show Floodgate version and check for updates |
| `/floodgate info <player>` | Show Floodgate info about a specific player |
| `/floodgate whitelist add <bedrock_username>` | Add a Bedrock player to the Java whitelist |
| `/floodgate whitelist remove <bedrock_username>` | Remove a Bedrock player from the whitelist |
| `/fwhitelist add <bedrock_username>` | Alias for whitelist add |
| `/linkaccount` | Link your Java and Bedrock accounts (run on Java first) |
| `/unlinkaccount` | Unlink accounts |

---

## Whitelisting Bedrock Players

If your server has a whitelist enabled, use Floodgate's command — **not** the standard `/whitelist`:

```
# Correct way to whitelist a Bedrock player:
/fwhitelist add BedrockPlayerName

# OR use their Floodgate UUID:
/whitelist add 00000000-0000-0000-XXXX-XXXXXXXXXXXX
```

Java players still use the normal `/whitelist add` command.

---

## How Bedrock Players Connect

1. Open Minecraft Bedrock Edition
2. Go to **Servers** → **Add Server**
3. Enter your server's IP address
4. Enter port **19132** (or whatever is configured in `config.yml`)
5. Join — they appear with a `.` prefix (e.g., `.BedrockPlayer`)

---

## Key Config Settings (`plugins/Geyser-Spigot/config.yml`)

```yaml
bedrock:
  address: 0.0.0.0   # Listen on all IPs
  port: 19132         # UDP port for Bedrock connections
  clone-remote-port: false  # Set true to use same port as Java

remote:
  address: auto       # Auto-detect Java server address
  
auth-type: floodgate  # Set to floodgate if using Floodgate plugin
                      # Set to online for normal Java auth (no Floodgate)
```

---

## Permissions

| Permission | Description |
|---|---|
| `geyser.command.help` | Use /geyser help |
| `geyser.command.list` | Use /geyser list |
| `geyser.command.reload` | Use /geyser reload |
| `geyser.command.version` | Use /geyser version |
| `geyser.command.dump` | Use /geyser dump |
| `geyser.command.offhand` | Use /geyser offhand |
| `geyser.command.*` | All Geyser command permissions |
| `floodgate.command.whitelist` | Use /floodgate whitelist |
| `floodgate.command.info` | Use /floodgate info |

---

## Important Notes

- Geyser does **not** support client-side mods — only server-side plugins
- Skins for Bedrock players may appear as Steve/Alex to Java players unless using GeyserSkinManager
- Some Java gameplay features may look different for Bedrock players (e.g., shield animations)
- ViaVersion is required if your server runs a version older than the latest Minecraft release
- **Do NOT share the `key.pem` file in the Floodgate config** — it allows Bedrock accounts to bypass Java authentication
