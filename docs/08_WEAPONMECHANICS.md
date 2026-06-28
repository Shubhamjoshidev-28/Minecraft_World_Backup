# 🔫 WeaponMechanics 4.3.1 + MechanicsCore 4.3.1 — Commands & Usage

**Wiki:** https://cjcrafter.gitbook.io/weaponmechanics  
**GitHub:** https://github.com/WeaponMechanics/WeaponMechanics  
**Purpose:** Advanced, highly customizable **guns plugin** for Minecraft. Adds realistic firearms with recoil, bullet spread, reload mechanics, scopes, and more.

---

## What They Do

### MechanicsCore
- **Dependency library** required by WeaponMechanics
- Provides shared utilities: brigadier commands, mechanics system, math, and more
- Has no gameplay features on its own — just needs to be installed
- Do NOT remove it — WeaponMechanics won't load without it

### WeaponMechanics
- Adds fully configurable **guns** to Minecraft
- Features include: bullet spread, recoil, scope (zoom), burst fire, fully-auto, reload, magazines, attachments
- All weapons are **YAML-configured** — you can create/customize any gun
- Includes default weapon packs (AK-47, M4, Sniper, etc.)
- Uses **PacketEvents** for smooth, low-latency packet handling

---

## WeaponMechanics Commands

All commands use `/weaponmechanics` or `/wm`.

| Command | Description |
|---|---|
| `/wm help` | Show all WeaponMechanics commands |
| `/wm give <player> <weapon> [amount]` | Give a weapon to a player |
| `/wm list` | List all available weapon configurations |
| `/wm reload` | Reload all weapon config files |
| `/wm info` | Show plugin version and info |
| `/wm shoot <player> <weapon>` | Force a player to shoot a weapon (debug) |
| `/wm convert` | Convert old weapon formats to new (migration tool) |
| `/wm test <player> <weapon>` | Spawn a dummy target for testing |

---

## MechanicsCore Commands

| Command | Description |
|---|---|
| `/mechanicscore` or `/mc` | Show MechanicsCore version info |
| `/mechanicscore reload` | Reload MechanicsCore configs |
| `/mechanicscore debug` | Toggle debug mode |

---

## Getting a Weapon In-Game

```
# Give yourself the AK-47
/wm give YourName AK-47

# Give yourself all default weapons
/wm list
# Then click the weapon in the list, or:
/wm give YourName <weapon_name_from_list>
```

---

## How Weapons Work

1. A **weapon config file** defines every property of a gun (damage, spread, reload time, etc.)
2. Default weapons are in `plugins/WeaponMechanics/weapons/`
3. Each weapon is a `.yml` file — you can create new ones by copying and editing existing ones
4. Players receive a **custom item** (e.g., a stick with custom NBT) that acts as the gun
5. Players left-click to shoot, sneak to scope/zoom, and press drop (Q) to reload

---

## Example Weapon YAML (Simplified)

```yaml
AK-47:
  Info:
    Weapon_Item:
      Type: IRON_HOE
      Name: "<red>AK-47"
    
  Shooting:
    Trigger: LEFT_CLICK
    Projectile_Speed: 100.0
    Spread:
      Base_Spread: 5.0
    
  Reload:
    Ammo:
      Magazine_Size: 30
      
  Damage:
    Base_Damage: 8.0
```

---

## Weapon Modules (Wiki Reference)

WeaponMechanics is built around "modules" — each controls a feature:

| Module | Description |
|---|---|
| `Info` | Basic weapon setup (item type, name, etc.) |
| `Shooting` | Fire rate, trigger type (auto/semi/burst), projectile speed |
| `Reload` | Magazine size, reload time, reload animations |
| `Scope` | Zoom level, overlay, scope-in/out speed |
| `Damage` | Base damage, headshot multiplier, armor penetration |
| `Spread` | Bullet spread patterns, moving/crouching spread changes |
| `Recoil` | Camera recoil pattern and recovery |
| `Skin` | Weapon skins/appearances |
| `Mechanics` | Custom mechanics triggered on shoot, reload, kill, etc. |

See full module documentation at: https://cjcrafter.gitbook.io/weaponmechanics/weapon-modules

---

## Permissions

| Permission | Description |
|---|---|
| `weaponmechanics.commands.give` | Use /wm give |
| `weaponmechanics.commands.list` | Use /wm list |
| `weaponmechanics.commands.reload` | Use /wm reload |
| `weaponmechanics.commands.info` | Use /wm info |
| `weaponmechanics.use.*` | Use all weapons |
| `weaponmechanics.use.<weapon_name>` | Use a specific weapon (e.g., `weaponmechanics.use.AK-47`) |
| `weaponmechanics.*` | All WeaponMechanics permissions |

---

## Setup Notes

- **PacketEvents** must be installed — WeaponMechanics depends on it
- **MechanicsCore** must be installed — it's a required dependency
- A **resource pack** is recommended for custom weapon textures (download link in SpigotMC page)
- Weapons are in `plugins/WeaponMechanics/weapons/*.yml` — edit these to customize guns
- VivecraftSpigot is supported if you want proper VR shooting

---

## Tips

- Use `/wm list` and click a weapon name to get it instantly without typing the full name
- Copy an existing weapon YAML and rename it to create custom weapons quickly
- Use VSCode to edit `.yml` files — it helps catch formatting errors
- Weapon config changes require `/wm reload` to take effect (no restart needed)
