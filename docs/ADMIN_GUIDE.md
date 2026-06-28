# Administrator Guide

## Starting The Server

Windows:

start.bat

Linux:

./start.sh
git add 
Wait until:

Done (...)

appears in console.

---

## Stopping The Server

Use:

stop

Never force close the process.

---

## Verifying Plugins

Run:

plugins

Expected plugins:

* Geyser
* Floodgate
* ViaVersion
* ViaBackwards
* Spark

---

## Backup Strategy

Backup the following directories:

* world
* world_nether
* world_the_end

Store backups externally.

---

## Restore Procedure

1. Stop server.
2. Restore backup files.
3. Start server.
4. Verify world integrity.

---

## Migration To VPS

Copy:

* java-server
* scripts
* configuration files

Install Java 25.

Run start script.

No architecture changes required.

---

## Performance Monitoring

Use Spark for profiling.

Monitor:

* TPS
* Memory Usage
* Tick Times
* Entity Counts

---

## Recommended Maintenance

Daily

* Check logs
* Verify backups

Weekly

* Plugin updates
* Performance review

Monthly

* Full backup validation
* Disaster recovery testing

---

## Troubleshooting

### Plugins Not Loading

Check:

plugins directory

Verify:

plugin versions match server version

---

### Bedrock Players Cannot Join

Verify:

* Geyser loaded
* Floodgate loaded
* Bedrock port exposed

---

### Java Players Cannot Join

Verify:

* Server online
* Correct address
* Version compatibility

---

### Server Lag

Check:

* Entity count
* Chunk generation
* Plugin performance
* Memory allocation
