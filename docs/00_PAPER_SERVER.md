# 🖥️ Paper Server — Overview & Key Commands

## What is Paper?

Paper is a high-performance fork of Spigot (which is itself a fork of CraftBukkit/Bukkit). It is the **recommended server software** for running plugins like the ones in your setup. Paper includes:

- **Performance optimizations** over vanilla and Spigot
- **Built-in spark profiler** (since 1.21, spark is bundled)
- Better chunk loading, async improvements
- Extra config options (`paper.yml` / `paper-world-defaults.yml`)
- Compatibility with all Bukkit/Spigot plugins

---

## Paper-Specific Commands (Console / OP)

| Command | Description |
|---|---|
| `/paper version` | Shows the Paper version and build number |
| `/paper reload` | Reloads Paper config (limited — full restart preferred) |
| `/paper dumpheap` | Creates a heap dump for memory analysis |
| `/paper mobcaps` | Shows current mob cap counts per world |
| `/paper syncloadinfo` | Shows information about sync chunk loads |
| `/paper timings` | **(Deprecated in 1.21+, use spark instead)** |

---

## Standard Server Admin Commands

These are built into Minecraft itself but work on Paper:

| Command | Description |
|---|---|
| `/op <player>` | Give a player operator (admin) status |
| `/deop <player>` | Remove operator status |
| `/whitelist add <player>` | Add player to whitelist |
| `/whitelist remove <player>` | Remove player from whitelist |
| `/whitelist on` / `/whitelist off` | Enable/disable whitelist |
| `/whitelist list` | List whitelisted players |
| `/ban <player> [reason]` | Ban a player |
| `/ban-ip <ip>` | Ban an IP address |
| `/pardon <player>` | Unban a player |
| `/kick <player> [reason]` | Kick a player |
| `/stop` | Stop the server safely |
| `/restart` | Restart the server (Paper) |
| `/reload confirm` | Reload plugins (not recommended; use restart) |
| `/save-all` | Force save all worlds |
| `/save-on` / `/save-off` | Toggle auto-saving |
| `/time set day` | Set time to day |
| `/time set night` | Set time to night |
| `/weather clear` / `/weather rain` | Change weather |
| `/gamerule <rule> <value>` | Set a gamerule (e.g. `/gamerule keepInventory true`) |
| `/difficulty <peaceful/easy/normal/hard>` | Set server difficulty |
| `/gamemode <mode> [player]` | Change gamemode |
| `/teleport <player> <target>` | Teleport a player |
| `/give <player> <item> [amount]` | Give items |
| `/clear <player>` | Clear a player's inventory |

---

## Important Config Files

| File | Purpose |
|---|---|
| `server.properties` | Core server settings (port, MOTD, max players, etc.) |
| `bukkit.yml` | Bukkit-level settings (mob spawning, etc.) |
| `spigot.yml` | Spigot performance tuning |
| `config/paper-global.yml` | Paper global settings |
| `config/paper-world-defaults.yml` | Default per-world Paper settings |
| `plugins/` | All your plugin JARs go here |

---

## Plugin Load Order (Your Server)

Your plugins load in roughly this order (dependency chain):

1. **PacketEvents** (required by WeaponMechanics)
2. **MechanicsCore** (required by WeaponMechanics)
3. **ViaVersion** (required by ViaBackwards)
4. **ViaBackwards** (depends on ViaVersion)
5. **Geyser-Spigot** (Bedrock bridge)
6. **Floodgate-Spigot** (Bedrock auth, works with Geyser)
7. **LuckPerms** (permissions)
8. **EssentialsX** (core utilities)
9. **EssentialsXSpawn** (depends on EssentialsX)
10. **CoreProtect** (logging/anti-grief)
11. **Spark** (performance profiler)
12. **WeaponMechanics** (guns plugin)
