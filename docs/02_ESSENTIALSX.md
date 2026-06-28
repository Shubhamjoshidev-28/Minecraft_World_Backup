# ⚙️ EssentialsX 2.22.0 — Commands & Usage

**Wiki:** https://essentialsx.net/wiki/  
**Commands Reference:** https://essentialsx.net/commands  
**Purpose:** The essential plugin suite — 130+ commands for teleportation, economy, moderation, chat, kits, warps, homes, and more.

---

## What It Does

EssentialsX is the backbone of most Minecraft servers. It provides:

- **Teleportation** — homes, warps, TPA, back
- **Economy** — balance, pay, eco management
- **Kits** — predefined item sets for players
- **Moderation** — ban, mute, kick, jail, mute, god
- **Chat** — private messages, social spy, nick
- **Utilities** — fly, speed, heal, feed, time, weather, gamemode
- **Signs** — interactive economy/warp/kit signs

---

## Teleportation Commands

| Command | Description |
|---|---|
| `/home [name]` | Teleport to your home |
| `/sethome [name]` | Set a home at your current location |
| `/delhome [name]` | Delete a home |
| `/listhomes [player]` | List all your (or another player's) homes |
| `/renamehome <old> <new>` | Rename a home |
| `/warp [name]` | Teleport to a server warp |
| `/setwarp <name>` | Create a warp at your location (admin) |
| `/delwarp <name>` | Delete a warp (admin) |
| `/listwarps` | List all warps |
| `/spawn` | Teleport to the server spawn |
| `/tp <player>` | Teleport to a player (admin) |
| `/tphere <player>` | Bring a player to you (admin) |
| `/tpall` | Teleport all players to you (admin) |
| `/tpa <player>` | Request to teleport to a player |
| `/tpaccept` | Accept a teleport request |
| `/tpdeny` | Deny a teleport request |
| `/tptoggle` | Toggle receiving teleport requests |
| `/back` | Return to your last location (after death or teleport) |
| `/tppos <x> <y> <z>` | Teleport to coordinates (admin) |
| `/tpr` | Teleport to a random location |
| `/tpahere <player>` | Request a player teleport to you |

---

## Economy Commands

| Command | Description |
|---|---|
| `/balance [player]` | Check your (or another player's) balance |
| `/bal [player]` | Alias for /balance |
| `/baltop` | Show the richest players |
| `/pay <player> <amount>` | Send money to another player |
| `/paytoggle` | Toggle receiving payments |
| `/eco give <player> <amount>` | Give money to a player (admin) |
| `/eco take <player> <amount>` | Take money from a player (admin) |
| `/eco set <player> <amount>` | Set a player's balance (admin) |
| `/eco reset <player>` | Reset a player's balance (admin) |
| `/sell hand` | Sell the item in your hand |
| `/sell all` | Sell everything in your inventory |

---

## Kit Commands

| Command | Description |
|---|---|
| `/kit [name]` | Receive a kit |
| `/kits` | List available kits |
| `/createkit <name> <delay>` | Create a kit from your inventory (admin) |
| `/editkit <name>` | Edit a kit in the config (admin) |

---

## Moderation Commands

| Command | Description |
|---|---|
| `/ban <player> [reason]` | Ban a player |
| `/ban-ip <ip/player> [reason]` | Ban by IP |
| `/unban <player>` | Unban a player |
| `/unban-ip <ip>` | Unban an IP |
| `/kick <player> [reason]` | Kick a player |
| `/mute <player> [duration] [reason]` | Mute a player |
| `/unmute <player>` | Unmute a player |
| `/tempban <player> <duration> [reason]` | Temporarily ban (e.g. `t:3d`) |
| `/warn <player> [reason]` | Warn a player |
| `/warnings <player>` | See a player's warnings |
| `/clearwarnings <player>` | Clear warnings (admin) |
| `/jail <player> [jail] [duration]` | Send a player to jail |
| `/unjail <player>` | Release a jailed player |
| `/setjail <name>` | Set a jail location (admin) |
| `/deljail <name>` | Delete a jail (admin) |
| `/jails` | List all jails |
| `/socialspy` | Toggle seeing private messages between players (admin) |
| `/vanish` | Become invisible to players (admin) |
| `/god [player]` | Toggle god mode |
| `/invsee <player>` | View a player's inventory (admin) |
| `/enderchest <player>` | View a player's ender chest (admin) |

---

## Chat Commands

| Command | Description |
|---|---|
| `/msg <player> <message>` | Send a private message |
| `/r <message>` | Reply to last private message |
| `/msgtoggle` | Toggle receiving all private messages |
| `/mail send <player> <message>` | Send an offline mail |
| `/mail read` | Read your mail |
| `/mail clear` | Clear your mail |
| `/nick <nickname>` | Set your display nickname |
| `/nick <player> <nick>` | Set another player's nickname (admin) |
| `/realname <nickname>` | Find the real name of a nickname |
| `/afk [message]` | Set yourself as AFK |
| `/broadcast <message>` | Broadcast a message to all players (admin) |
| `/announce <message>` | Alias for broadcast |

---

## Player Utility Commands

| Command | Description |
|---|---|
| `/heal [player]` | Fully heal yourself or another player |
| `/feed [player]` | Fill hunger bar |
| `/fly [player]` | Toggle fly mode |
| `/speed <value> [player]` | Set walk/fly speed (0–10) |
| `/gamemode <mode> [player]` | Change gamemode (survival/creative/adventure/spectator) |
| `/gm <0/1/2/3>` | Alias for gamemode |
| `/gms` / `/gmc` / `/gma` / `/gmsp` | Quick gamemode aliases |
| `/item <item> [amount]` | Give yourself an item |
| `/i <item>` | Alias for /item |
| `/give <player> <item> [amount]` | Give an item to a player |
| `/enchant <enchant> [level]` | Enchant held item |
| `/repair [hand/all]` | Repair held item or all items |
| `/hat` | Wear held item as a hat |
| `/skull [player]` | Get a player head |
| `/book` | Reopen a written book for editing |
| `/editsign` | Edit a sign's text (admin) |
| `/ext [player]` | Extinguish a burning player |
| `/more` | Fill held item stack to max |
| `/clearinventory [player]` | Clear a player's inventory |
| `/ci` | Alias for clearinventory |
| `/compass` | Show your current compass direction |
| `/depth` | Show current depth (Y level) |
| `/getpos` | Show your current coordinates |
| `/biome` | Show current biome |
| `/tps` | Show server TPS |
| `/motd` | Show server MOTD |
| `/rules` | Show server rules |
| `/list` | Show online players |
| `/seen <player>` | Check when a player was last online |
| `/whois <player>` | Detailed info about a player (admin) |
| `/ping [player]` | Check ping |
| `/time set <day/night/value>` | Set server time (admin) |
| `/time add <value>` | Add to server time (admin) |
| `/weather <sunny/rain/thunder>` | Set weather (admin) |
| `/workbench` | Open a portable crafting table |
| `/anvil` | Open a portable anvil |
| `/enderchest` | Open your ender chest |
| `/exp give <player> <amount>` | Give XP (admin) |
| `/exp set <player> <amount>` | Set XP (admin) |
| `/ptime <time>` | Set personal time (only you see it) |
| `/pweather <weather>` | Set personal weather |

---

## Server Management Commands

| Command | Description |
|---|---|
| `/essentials reload` | Reload EssentialsX config |
| `/essentials version` | Show EssentialsX version |
| `/togglejail` | Toggle jail for all players |
| `/dumpstate` | Dump plugin state for debugging |

---

## Permissions (Key Nodes)

| Permission | Description |
|---|---|
| `essentials.home` | Use /home |
| `essentials.sethome` | Use /sethome |
| `essentials.warp` | Use /warp |
| `essentials.tpa` | Use /tpa |
| `essentials.fly` | Use /fly |
| `essentials.god` | Use /god |
| `essentials.heal` | Use /heal |
| `essentials.ban` | Use /ban |
| `essentials.kick` | Use /kick |
| `essentials.mute` | Use /mute |
| `essentials.vanish` | Use /vanish |
| `essentials.socialspy` | Use /socialspy |
| `essentials.eco` | Manage economy (admin) |
| `essentials.*` | All EssentialsX permissions |

---

## Notes for Paper Servers

- Paper is the **recommended** server type for EssentialsX.
- On Paper 1.21+, some vanilla command conflicts can be managed via `commands.yml`.
- EssentialsX 2.22.0 fully supports Paper 26.1.2 and all 1.21.x versions.
- Pair with **LuckPerms** for permission management and **Vault** for economy prefix/suffix support.
