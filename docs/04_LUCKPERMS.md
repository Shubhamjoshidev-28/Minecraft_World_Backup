# 🔑 LuckPerms 5.5.57 — Commands & Usage

**Wiki:** https://luckperms.net/wiki  
**Purpose:** The most powerful and widely-used permissions plugin. Controls what commands and features each player or group can access.

---

## What It Does

LuckPerms lets you:
- Create **permission groups** (default, moderator, admin, etc.)
- Assign **permissions** (nodes) to groups or individual players
- Set **inheritance** (moderator inherits from default)
- Use **contexts** (permissions only in certain worlds or servers)
- Manage everything via commands, **config files**, or the **web editor**

---

## Command Aliases

On Paper/Spigot, use:
- `/luckperms` — full name
- `/lp` — short alias (most common)
- `/luckperms user` → `/lp user`

---

## General Commands

| Command | Description |
|---|---|
| `/lp` | Show plugin info and available commands |
| `/lp sync` | Sync all cached data with the storage provider |
| `/lp info` | Show debug info, stats, and settings |
| `/lp editor` | **Open the web editor** (easiest way to manage permissions) |
| `/lp debug` | Record debug output and get a link |
| `/lp verbose <on/off/record/paste> [filter]` | Monitor permission checks in real time |
| `/lp tree [scope]` | View a tree of all registered permissions |
| `/lp search <permission>` | Search all users/groups for a specific permission |
| `/lp check <user> <permission>` | Check if a player has a specific permission |
| `/lp networksync` | Sync with all connected servers |
| `/lp reload` | Reload the config file |
| `/lp bulkupdate` | Perform bulk permission changes (console only) |
| `/lp migration` | Import from other permission plugins |

---

## User Commands

Manage individual players:

| Command | Description |
|---|---|
| `/lp user <player> info` | Show a player's info, groups, and permissions |
| `/lp user <player> permission set <node> <true/false>` | Add or remove a permission |
| `/lp user <player> permission unset <node>` | Remove a permission node |
| `/lp user <player> permission check <node>` | Check if player has a permission |
| `/lp user <player> permission checkinhers <node>` | Check inherited permissions |
| `/lp user <player> group add <group>` | Add player to a group |
| `/lp user <player> group remove <group>` | Remove player from a group |
| `/lp user <player> parent set <group>` | Set player's primary group |
| `/lp user <player> parent add <group>` | Add a parent group |
| `/lp user <player> parent remove <group>` | Remove a parent group |
| `/lp user <player> meta set <key> <value>` | Set a meta value (prefix, suffix, etc.) |
| `/lp user <player> meta unset <key>` | Remove a meta value |
| `/lp user <player> clone <new_player>` | Clone a user's permissions to another user |
| `/lp user <player> promote <track>` | Promote player along a track |
| `/lp user <player> demote <track>` | Demote player along a track |

---

## Group Commands

Manage permission groups:

| Command | Description |
|---|---|
| `/lp creategroup <name>` | Create a new group |
| `/lp deletegroup <name>` | Delete a group |
| `/lp listgroups` | List all groups |
| `/lp group <group> info` | Show group info and permissions |
| `/lp group <group> permission set <node> <true/false>` | Add or remove a permission |
| `/lp group <group> permission unset <node>` | Remove a permission node |
| `/lp group <group> parent add <parent>` | Make a group inherit from another |
| `/lp group <group> parent remove <parent>` | Remove inheritance |
| `/lp group <group> parent set <parent>` | Set primary parent group |
| `/lp group <group> meta set <key> <value>` | Set prefix/suffix/metadata |
| `/lp group <group> meta unset <key>` | Remove meta |
| `/lp group <group> setweight <weight>` | Set group priority/weight |
| `/lp group <group> clone <new_group>` | Clone a group |
| `/lp group <group> rename <new_name>` | Rename a group |

---

## Track Commands

Tracks let you define a promotion path (e.g. new → member → veteran):

| Command | Description |
|---|---|
| `/lp createtrack <name>` | Create a new track |
| `/lp deletetrack <name>` | Delete a track |
| `/lp listtracks` | List all tracks |
| `/lp track <track> info` | Show track info |
| `/lp track <track> append <group>` | Add a group to the end of the track |
| `/lp track <track> insert <group> <position>` | Insert a group at a position |
| `/lp track <track> remove <group>` | Remove a group from the track |
| `/lp track <track> clear` | Clear all groups from a track |
| `/lp track <track> rename <new_name>` | Rename a track |

---

## Common Examples

```
# Give yourself admin permissions
/lp user YourName parent add admin

# Add the 'fly' permission to the VIP group
/lp group vip permission set essentials.fly true

# Remove a permission from a player
/lp user PlayerName permission unset essentials.fly

# Set the default group for all new players
/lp group default permission set some.permission true

# Set a prefix for the admin group (requires Vault + EssentialsXChat)
/lp group admin meta set prefix "[Admin] "

# Make moderator inherit all default permissions
/lp group moderator parent add default

# Promote a player along the member track
/lp user PlayerName promote member-track

# Open the web editor (easiest way)
/lp editor
```

---

## Web Editor

The **easiest** way to manage LuckPerms is through the web editor:

1. Run `/lp editor` in-game or in console
2. Click the link shown in chat/console
3. Make all your changes in the browser UI
4. Click **Save** to apply

---

## Permissions for LuckPerms Commands

| Permission | Description |
|---|---|
| `luckperms.sync` | Use /lp sync |
| `luckperms.info` | Use /lp info |
| `luckperms.editor` | Use /lp editor |
| `luckperms.verbose` | Use /lp verbose |
| `luckperms.user.info` | View user info |
| `luckperms.user.permission.set` | Set user permissions |
| `luckperms.group.info` | View group info |
| `luckperms.group.permission.set` | Set group permissions |
| `luckperms.*` | All LuckPerms permissions |

---

## Tips

- By default on Paper, **OPs have full access** to LuckPerms commands.
- Use the **web editor** for initial setup — much easier than commands.
- Set a group **weight** to control which group's permissions take priority (higher = more priority).
- Always assign players to the `default` group as a baseline.
- Works perfectly with EssentialsX — use LuckPerms groups to control which EssentialsX commands each rank can use.
