# ⚡ Spark 1.10.173 — Commands & Usage

**Wiki / Docs:** https://spark.lucko.me/docs/  
**Purpose:** Performance profiler for your Paper server. Diagnoses lag, high CPU, memory leaks, and tick spikes.

---

## What It Does

Spark has three main tools:

1. **CPU Profiler** — Finds what code/plugins are causing lag or high CPU
2. **Memory Inspector** — Finds what's using the most RAM (heap summary, heap dump)
3. **Health Reporter** — Shows TPS, CPU, RAM, disk in a quick report

> **Paper Note:** Starting with Paper 1.21, spark is **bundled into Paper** by default. If you have the standalone `spark-1.10.173-bukkit.jar` in your plugins folder, it will be used instead of the bundled version (and will be the newer version).

---

## All Commands

Permission required: `spark` (granted to OPs by default)

### Profiler Commands

| Command | Description |
|---|---|
| `/spark profiler start` | Start the CPU profiler |
| `/spark profiler stop` | Stop the profiler and get a results link |
| `/spark profiler open` | Open viewer page without stopping the profiler |
| `/spark profiler cancel` | Cancel profiling without uploading results |
| `/spark profiler info` | Show current profiler status |

### Profiler Flags

| Flag | Description |
|---|---|
| `--timeout <seconds>` | Auto-stop after X seconds |
| `--thread *` | Profile all threads (not just main) |
| `--thread <name>` | Profile only a specific thread |
| `--alloc` | Profile memory allocations instead of CPU |
| `--interval <ms>` | Sampling interval in milliseconds (default: 4) |
| `--only-ticks-over <ms>` | Only record samples from slow ticks |
| `--combine-all` | Combine all threads under one root node |
| `--ignore-sleeping` | Ignore threads in sleep state |
| `--force-java-sampler` | Force Java sampler instead of async-profiler |
| `--save-to-file` | Save profile to disk instead of uploading |

### Health & TPS Commands

| Command | Description |
|---|---|
| `/spark health` | Show TPS, CPU, RAM, and disk health report |
| `/spark health --upload` | Upload the health report and get a shareable link |
| `/spark health --memory` | Include detailed JVM memory info |
| `/spark health --network` | Include network usage info |
| `/spark tps` | Quick TPS (ticks per second) and CPU usage view |
| `/spark ping` | Show average ping of all players |
| `/spark ping --player <username>` | Show a specific player's ping |

### Tick Monitoring Commands

| Command | Description |
|---|---|
| `/spark tickmonitor` | Toggle tick monitoring on/off |
| `/spark tickmonitor --threshold <percent>` | Only report ticks exceeding X% above average |
| `/spark tickmonitor --threshold-tick <ms>` | Only report ticks exceeding X milliseconds |
| `/spark tickmonitor --without-gc` | Disable GC activity reports |

### Memory Commands

| Command | Description |
|---|---|
| `/spark gc` | Show garbage collection (GC) history |
| `/spark gcmonitor` | Toggle real-time GC monitoring |
| `/spark heapsummary` | Take a snapshot of memory usage by class |
| `/spark heapdump` | Create a full HPROF heap dump file |

---

## Common Workflows

### Server is lagging — find the cause:
```
/spark profiler start
# Wait 2–5 minutes while the server is under load
/spark profiler stop
# Click the link, look for the largest time consumers
```

### Check server health quickly:
```
/spark health
```

### Monitor individual slow ticks:
```
/spark tickmonitor --threshold-tick 100
# This will report any tick that takes >100ms
```

### Check memory usage:
```
/spark heapsummary
# Click the link to see which classes use the most RAM
```

### Profile memory allocations (finding memory leaks):
```
/spark profiler start --alloc
# Wait a few minutes
/spark profiler stop
```

---

## Reading the Profiler Results

The profiler output is a **call tree** (flame graph). To analyze:
- Look for the **widest bars** — those are the most time-consuming operations
- Check if a specific **plugin** is at the top of the stack
- Look for **Paper internals** if the issue is the server itself

Key things to look for:
- Plugin names in the call stack = that plugin is causing lag
- `net.minecraft.server` = vanilla server code
- `io.papermc` = Paper internals

---

## Permissions

| Permission | Description |
|---|---|
| `spark` | Full access to all spark commands |
| `spark.profiler` | Use the profiler |
| `spark.healthreport` | Use /spark health |
| `spark.tps` | Use /spark tps |
| `spark.ping` | Use /spark ping |
| `spark.tickmonitor` | Use /spark tickmonitor |
| `spark.gc` | Use /spark gc |
| `spark.gcmonitor` | Use /spark gcmonitor |
| `spark.heapsummary` | Use /spark heapsummary |
| `spark.heapdump` | Use /spark heapdump |

---

## Tips

- Run the profiler for **at least 1–2 minutes** for meaningful results
- Use `--thread *` if you suspect async plugins (like Celery-style workers) are the issue
- The online viewer at `spark.lucko.me` auto-applies deobfuscation mappings so class names are readable
- Share the profiler link with plugin developers when reporting performance bugs
