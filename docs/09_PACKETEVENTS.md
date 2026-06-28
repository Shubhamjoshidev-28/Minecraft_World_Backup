# 📦 PacketEvents — Commands & Usage

**Docs:** https://docs.packetevents.com/  
**GitHub:** https://github.com/retrooper/packetevents  
**Purpose:** Protocol library that allows other plugins (like WeaponMechanics) to read, modify, and send Minecraft network packets efficiently.

---

## What It Does

PacketEvents is a **developer library plugin** — it's not directly used by players or admins. It:

- Provides a **stable API** for other plugins to handle Minecraft packets
- Works across many versions (1.8–1.21.x) and platforms (Paper, Spigot, Velocity, etc.)
- Is required by **WeaponMechanics** on your server
- Handles low-level networking so other plugins don't have to

**You don't need to configure or use PacketEvents directly.** Just keep the jar in your `plugins/` folder.

---

## Why It's Installed

PacketEvents is a **hard dependency** of WeaponMechanics. Without it:
- WeaponMechanics will fail to load
- You'll see an error like `Cannot load WeaponMechanics — missing dependency: PacketEvents`

---

## Admin Commands

PacketEvents has minimal in-game commands:

| Command | Description |
|---|---|
| `/packetevents version` | Show PacketEvents version info |
| `/packetevents debug` | Toggle debug packet logging (console output) |

These commands are mostly used by **plugin developers**, not server admins.

---

## Permissions

| Permission | Description |
|---|---|
| `packetevents.command.version` | Use /packetevents version |
| `packetevents.command.debug` | Use /packetevents debug |

---

## Load Order

PacketEvents must load **before** plugins that depend on it. On your server, ensure that `packetevents.jar` is in the `plugins/` folder and the plugin loading order places it before WeaponMechanics. This happens automatically since PacketEvents declares itself as a dependency.

---

## Notes

- **Do not delete this plugin** — WeaponMechanics will break
- PacketEvents updates frequently; keep it updated alongside WeaponMechanics
- It has no config file that needs editing
- It is compatible with **Geyser**, **ViaVersion**, and **ViaBackwards** — they have soft-dependency support built in
