# 🏠 EssentialsXSpawn 2.22.0 — Commands & Usage

**Wiki:** https://essentialsx.net/wiki/modules  
**Purpose:** Controls where players spawn when they first join or respawn after death. Add-on module for EssentialsX (requires the core EssentialsX jar).

---

## What It Does

EssentialsXSpawn adds:
- Server-wide spawn point management
- Per-group spawn points (e.g. different spawn for VIP vs. default players)
- New player welcome messages and starter kits
- Respawn behavior control (spawn vs. bed vs. home)

---

## Commands

| Command | Description |
|---|---|
| `/setspawn [group]` | Set the spawn point at your current location (optionally for a specific permission group) |
| `/spawn` | Teleport yourself to the server spawn |
| `/spawn <player>` | Teleport another player to spawn (admin) |
| `/delspawn` | Remove the defined spawn point |

---

## Example Usage

```
# Set the server spawn for everyone at your location
/setspawn

# Set a separate spawn for the VIP group
/setspawn vip

# Teleport yourself to spawn
/spawn

# Teleport another player to spawn
/spawn PlayerName
```

---

## Configuration (in `plugins/Essentials/config.yml`)

The EssentialsXSpawn settings are in the **EssentialsX Spawn + New Players** section:

```yaml
# Message shown when a new player joins
newbies:
  announce-format: '&dWelcome {DISPLAYNAME}&d to the server!'
  # Kit given to new players on first join
  kit: ''
  # Teleport new players to spawn on first join
  spawnpoint: newbies

# Respawn behavior
respawn-at-home: false        # Respawn at player's /sethome
respawn-at-home-bed: true     # Respawn at player's bed
respawn-listener-priority: normal
```

---

## Permissions

| Permission | Description |
|---|---|
| `essentials.spawn` | Use `/spawn` to teleport to spawn |
| `essentials.spawn.others` | Teleport other players to spawn |
| `essentials.setspawn` | Use `/setspawn` |
| `essentials.spawn.cooldown.bypass` | Bypass spawn teleport cooldown |

---

## Group-Based Spawns

You can set different spawn points for different permission groups:

```
# In-game, while standing at the desired location:
/setspawn admin
/setspawn vip
/setspawn default
```

Players will be sent to their group's spawn when they use `/spawn`. The plugin checks LuckPerms groups to determine which spawn to use.

---

## Notes

- EssentialsXSpawn requires the **core EssentialsX jar** to be installed alongside it.
- It is a separate `.jar` file — `EssentialsXSpawn-2.22.0.jar`.
- Works perfectly with Paper (recommended platform).
- Respawn-at-bed behavior depends on Paper's native bed respawn handling.
