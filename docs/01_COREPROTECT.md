# 🛡️ CoreProtect CE 23.2 — Commands & Usage

**Wiki:** https://docs.coreprotect.net/  
**Purpose:** Anti-griefing data logger — tracks every block place, break, chest interaction, kill, and more. Lets you inspect, rollback, and restore damage.

---

## What It Does

- Logs **all block changes** (placed, broken, burned, etc.)
- Logs **chest/container interactions** (items added/removed)
- Logs **kills, explosions, leaf decay, tree growth**
- Lets you **rollback** (undo) any player's actions
- Lets you **restore** (redo) rolled-back changes
- Lets you **inspect** individual blocks to see their full history

No configuration needed — install the jar and it starts logging immediately.

---

## All Commands

All commands use the prefix `/co` (or `/coreprotect`).

| Command | Description |
|---|---|
| `/co help` | Show all CoreProtect commands in-game |
| `/co inspect` | **Toggle the inspector** — right-click blocks to see their history |
| `/co i` | Alias for `/co inspect` |
| `/co lookup` | Look up block/action data using parameters |
| `/co l` | Alias for `/co lookup` |
| `/co rollback` | Roll back (undo) player or game actions |
| `/co rb` | Alias for `/co rollback` |
| `/co restore` | Restore (redo) previously rolled-back data |
| `/co rs` | Alias for `/co restore` |
| `/co purge` | Delete old log data to free up disk space |
| `/co reload` | Reload the CoreProtect config file |
| `/co status` | Show plugin version and status |
| `/co consumer` | Pause or resume the data consumer queue (console only) |
| `/co migrate-db` | Migrate between SQLite and MySQL (console only) |
| `/co near` | Quick lookup within 5 blocks of your position |
| `/co undo` | Revert your last rollback or restore |

---

## Parameters (used with lookup, rollback, restore)

| Parameter | Example | Description |
|---|---|---|
| `u:<user>` | `u:Steve` | Target a specific player (or multiple: `u:Steve,Alex`) |
| `t:<time>` | `t:1h` | How far back to go (weeks `w`, days `d`, hours `h`, minutes `m`, seconds `s`) |
| `r:<radius>` | `r:20` | Block radius around your position |
| `r:#global` | `r:#global` | Target the entire server |
| `r:#world_nether` | `r:#world_nether` | Target a specific world |
| `r:#worldedit` | `r:#worldedit` | Use a WorldEdit selection as the area |
| `a:<action>` | `a:-block` | Filter by action type (see table below) |
| `i:<include>` | `i:diamond_ore` | Only include specific blocks |
| `e:<exclude>` | `e:stone,dirt` | Exclude specific blocks |
| `#preview` | `#preview` | Preview the rollback without applying it |
| `#count` | `#count` | Show the count of affected blocks |

### Action Types for `a:`

| Action | Meaning |
|---|---|
| `a:block` | All blocks placed or broken |
| `a:+block` | Only blocks placed |
| `a:-block` | Only blocks broken |
| `a:chat` | Chat messages |
| `a:click` | Player interactions (button presses, levers, etc.) |
| `a:command` | Commands used |
| `a:container` | All chest/container changes |
| `a:+container` | Items put INTO containers |
| `a:-container` | Items taken FROM containers |
| `a:inventory` | Player inventory changes |
| `a:kill` | Kills (mobs and players) |
| `a:session` | Login/logout events |
| `a:sign` | Sign text edits |
| `a:username` | Username changes |

---

## Example Commands

```
# See who placed/broke the block you're standing near
/co i
(right-click the block)

# Roll back Steve's actions from the last 2 hours within 20 blocks
/co rollback u:Steve t:2h r:20

# Roll back EVERYTHING in the last 15 minutes globally
/co rollback t:15m r:#global

# Roll back only blocks broken (not placed) by Steve in the last day
/co rollback u:Steve t:1d a:-block

# Preview a rollback first
/co rollback u:Steve t:1h r:50 #preview

# Restore (undo) a rollback
/co restore u:Steve t:1h r:20

# Delete data older than 30 days
/co purge t:30d

# Look up Steve's recent chest interactions
/co lookup u:Steve t:1d a:container

# Look up what happened at your location in the last hour
/co lookup t:1h r:5
```

---

## Permissions

| Permission | Description |
|---|---|
| `coreprotect.inspect` | Use `/co inspect` |
| `coreprotect.lookup` | Use `/co lookup` |
| `coreprotect.rollback` | Use `/co rollback` |
| `coreprotect.restore` | Use `/co restore` |
| `coreprotect.purge` | Use `/co purge` |
| `coreprotect.reload` | Use `/co reload` |
| `coreprotect.status` | Use `/co status` |
| `coreprotect.*` | All CoreProtect permissions |

---

## Tips

- Use `/co i` before right-clicking a block to instantly see its history without typing a lookup command.
- Always use `#preview` before a large rollback to see what will happen.
- Data is stored in `plugins/CoreProtect/database.db` (SQLite by default).
- You can optionally switch to MySQL in the config for better performance on large servers.
