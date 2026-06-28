# 🔄 ViaVersion 5.10.0 + ViaBackwards 5.10.0 — Commands & Usage

**ViaVersion Wiki:** https://viaversion.com/wiki  
**ViaBackwards GitHub:** https://github.com/ViaVersion/ViaBackwards  
**Purpose:** Allow players on **different Minecraft versions** to connect to your server simultaneously.

---

## What They Do

### ViaVersion
- Allows **newer clients** to connect to an **older server**
- Example: Your server runs 1.20.1 → players on 1.21 can still join
- Java clients only

### ViaBackwards
- Allows **older clients** to connect to a **newer server**
- Requires ViaVersion to be installed
- Example: Your server runs 1.21 → players on 1.18, 1.19, 1.20 can still join
- Supports clients down to 1.9

### Combined Effect (Your Setup)
With both installed, players on a **wide range of Minecraft versions** can connect to your server at the same time. They just see version-appropriate translations of blocks, items, and entities.

---

## ViaVersion Commands

Permission: `viaversion.admin` or `viaversion.command.<subcommand>`

| Command | Description |
|---|---|
| `/viaversion` or `/viaver` or `/vv` | Show ViaVersion info and version |
| `/viaversion help` | Show all ViaVersion commands |
| `/viaversion list` | List all connected players and their client versions |
| `/viaversion reload` | Reload the ViaVersion config |
| `/viaversion dump` | Generate a debug dump (for bug reports) |
| `/viaversion version` | Show plugin version |
| `/viaversion autoteam` | Toggle the auto-team feature (used for nametag color fixes) |
| `/viaversion dontbug` | Ignore a bug for the current session |
| `/viaversion pplist` | Show list of players and their protocols |

---

## ViaBackwards Commands

ViaBackwards has minimal admin commands since it works transparently:

| Command | Description |
|---|---|
| `/viabackwards` or `/viabw` | Show ViaBackwards info and version |
| `/viabackwards reload` | Reload ViaBackwards config |

---

## How It Works (No Setup Needed)

Both plugins work **automatically** after installation. You don't need to configure anything:

1. Drop `ViaVersion-5.10.0.jar` into `plugins/`
2. Drop `ViaBackwards-5.10.0.jar` into `plugins/`
3. Restart your server
4. Players on older/newer versions can now join

---

## Supported Versions

With ViaVersion + ViaBackwards (your config):

| Client Version | Can Connect? |
|---|---|
| Latest Minecraft | ✅ Yes (ViaVersion) |
| 1.21.x | ✅ Yes |
| 1.20.x | ✅ Yes (ViaBackwards) |
| 1.19.x | ✅ Yes (ViaBackwards) |
| 1.18.x | ✅ Yes (ViaBackwards) |
| 1.17.x | ✅ Yes (ViaBackwards) |
| 1.16.x | ✅ Yes (ViaBackwards) |
| 1.15.x | ✅ Yes (ViaBackwards) |
| 1.14.x | ✅ Yes (ViaBackwards) |
| 1.13.x | ✅ Yes (ViaBackwards) |
| 1.12.x | ✅ Yes (ViaBackwards) |
| 1.9.x | ✅ Yes (ViaBackwards, minimum) |
| 1.8.x or older | ❌ No (need ViaRewind for 1.8/1.7) |

---

## Permissions

| Permission | Description |
|---|---|
| `viaversion.admin` | Full access to all ViaVersion commands |
| `viaversion.command.list` | Use /vv list |
| `viaversion.command.reload` | Use /vv reload |
| `viaversion.command.dump` | Use /vv dump |
| `viaversion.command.version` | Use /vv version |

---

## Known Limitations

- Some visual elements may look different for players on older versions (e.g., blocks that don't exist in their version appear as a substitute block)
- Anti-cheat plugins may be less accurate for older version clients
- Scoreboard character limits vary by version
- 1.17+ world height changes (Y below 0) are invisible to clients older than 1.17

---

## Tips

- Keep ViaVersion and ViaBackwards on the **same build channel** (both release, or both dev)
- These plugins are **passive** — they require no ongoing management
- Check `/vv list` to see what versions your players are using
- If players report visual glitches, it may be a known version translation issue, not a server problem
