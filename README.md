# Grand Horizon RP - Data & Releases

Public game data + launcher APK + live config for **Grand Horizon RP** (Android, GTA SA based roleplay).

## Downloads (no GitHub account needed)

- **Launcher APK v1.2**: release `launcher-v1.2` -> `GrandHorizonRP-Launcher-v1.2.apk`
- **Game data**: release `game-data-v2.2` (3 parts, total ~2.2 GB, downloaded automatically by the launcher)

- Server: `142.132.203.47:14448`
- Telegram: https://t.me/grandhorizonrp

## v1.2 launcher changes

- FIXED: game crash after pressing PLAY (the SAMP client folder is now created automatically)
- FIXED: nickname is saved correctly into `GrandHorizonRP/SAMP/settings.ini`
- FIXED: download failures retry automatically (5 attempts) with size verification
- NEW: live server status (online + player count) on the launcher screen
- NEW: quick repair of existing installations - no 2.2 GB re-download needed
- NEW: clear error message on 64-bit-only devices that cannot run the game

## Server database (admin only)

If the phpMyAdmin import of `reytize.sql` fails with:

```
#1101 - BLOB, TEXT, GEOMETRY or JSON column 'weekly_prizes' can't have a default value
```

use **`server/reytize_fixed.sql`** from this repo instead:

1. Open phpMyAdmin on the Lemehost panel
2. Select the game database
3. Import tab -> choose `reytize_fixed.sql` -> Go

The fixed dump converts `weekly_prizes` to `varchar(128)` (defaults allowed) and
drops existing tables before re-creating them, so it can be imported repeatedly.

The launcher reads live config from `json/` in this repo.
