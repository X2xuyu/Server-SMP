# 🧊 BlackSMP — Purpur 1.21.4 Server Pack

[![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-brightgreen)](#)
[![Server](https://img.shields.io/badge/Server-Purpur-7f5af0)](#)
[![Java](https://img.shields.io/badge/Java-21-blue)](#)
[![Plugins](https://img.shields.io/badge/Plugins-21-orange)](#)
[![Status](https://img.shields.io/badge/Type-SMP%20%7C%20Survival-success)](#)

> A **ready-to-run** Minecraft SMP server pack using **Purpur 1.21.4** (Paper fork) with a curated plugin set.
> Designed for **performance + QoL**, and easy for others to clone and customize.

---

## 📌 What’s in this repo?

This repository focuses on:
- ✅ Server configuration (`server.properties`, Paper/Purpur configs, plugin configs)
- ✅ Recommended start scripts / JVM flags
- ✅ Notes for hosting (LAN / Internet / CGNAT tunnels)

**Not recommended to publish:**
- ❌ world folders (huge + changes constantly)
- ❌ logs/crash-reports
- ❌ player/auth data (ops/whitelist/bans)

---

## ✅ Requirements

| Item | Required |
|---|---|
| Minecraft | Java Edition **1.21.4** |
| Server | **Purpur 1.21.4** |
| Java | **Java 21** (Temurin/OpenJDK recommended) |
| OS | Windows (tested), Linux works with script changes |

---

## 🚀 Quick Start (Windows)

### 1) Install Java 21
Verify:
```bat
java -version
```

### 2) Put the server jar in root
Example:
```
purpur-1.21.4-2394.jar
```

### 3) Accept EULA
Edit `eula.txt`:
```
eula=true
```

### 4) Start
Use the recommended `Run.bat` below.

---

## 🧠 Recommended Start Scripts (RAM flags)

### ✅ Run.bat (Aikar-style flags, Java 21)
> Good default for most SMP servers. Adjust RAM based on your machine.

```bat
@echo off
title BlackSMP - Purpur 1.21.4
cd /d %~dp0

REM ======================
REM  RAM SETTINGS
REM  -Xms = initial memory
REM  -Xmx = max memory
REM ======================
set XMS=4G
set XMX=6G

REM ======================
REM  JAR NAME
REM ======================
set JAR=purpur-1.21.4-2394.jar

REM ======================
REM  START
REM ======================
java -Xms%XMS% -Xmx%XMX% ^
  -XX:+UseG1GC ^
  -XX:+ParallelRefProcEnabled ^
  -XX:MaxGCPauseMillis=200 ^
  -XX:+UnlockExperimentalVMOptions ^
  -XX:+DisableExplicitGC ^
  -XX:+AlwaysPreTouch ^
  -XX:G1NewSizePercent=30 ^
  -XX:G1MaxNewSizePercent=40 ^
  -XX:G1HeapRegionSize=8M ^
  -XX:G1ReservePercent=20 ^
  -XX:G1HeapWastePercent=5 ^
  -XX:G1MixedGCCountTarget=4 ^
  -XX:InitiatingHeapOccupancyPercent=15 ^
  -XX:G1MixedGCLiveThresholdPercent=90 ^
  -XX:G1RSetUpdatingPauseTimePercent=5 ^
  -XX:SurvivorRatio=32 ^
  -XX:+PerfDisableSharedMem ^
  -XX:MaxTenuringThreshold=1 ^
  -Dfile.encoding=UTF-8 ^
  -jar %JAR% --nogui

pause
```

### RAM guide
- **Small SMP (1–5 players):** 3–4GB
- **Medium (5–15 players):** 5–8GB
- **Large (15+ players / heavy farms):** 10–16GB+

> More RAM isn’t always better — too high can increase GC pauses.

---

## 🌐 How to Join / Host

### LAN (same Wi-Fi)
Players connect using:
```
192.168.x.x:25565
```

### Public Internet Hosting (friends far away)
If your WAN IP is in **100.64.x.x – 100.127.x.x** you are behind **CGNAT**  
➡️ Port forwarding will NOT work.

✅ Options:
1) **playit.gg tunnel** (fastest setup)
2) Request **Public IPv4** from ISP
3) VPS / proxy setup

**Important:** in `server.properties` keep:
```
server-ip=
server-port=25565
```

---

## 🧩 Plugin Summary

### 🔥 Core Essentials
| Plugin | Purpose |
|---|---|
| EssentialsX | Core commands, homes, warps, kits |
| LuckPerms | Permissions management |
| Vault | Economy/permissions bridge |
| PlaceholderAPI | Placeholders for scoreboards/GUI |

### 💰 Economy & UI
| Plugin | Purpose |
|---|---|
| EconomyShopGUI | Shop GUI / buy-sell system |
| HomeGUI | GUI for homes/menu |
| CommandPanels | GUI panels/menus |

### 🧭 Utility / QoL
| Plugin | Purpose |
|---|---|
| BetterRTP | Random teleport |
| BetterTeams | Team/clan system |
| SkinsRestorer | Skins for offline-mode servers |
| LoginSecurity | Password protection (offline-mode) |
| ItemEdit | Edit item lore/name/NBT tools |
| PvPManager | PvP protection / combat tags |
| voicechat | Proximity voice chat |
| Chunky | Chunk pregenerator |
| spark | Server profiler (bundled) |

### 🧪 Gameplay / Systems
| Plugin | Purpose |
|---|---|
| SmartSpawner | Spawner system + drops/xp integration |
| BlueSlimeCore | Dependency library |
| SimpleBounty | Bounty system |
| SimpleScore | Scoreboard system |
| AutoStop | Utility automation (server stop task) |

---

## 📦 Full Plugin List (as loaded)

| # | Plugin | Version |
|---:|---|---|
| 1 | EconomyShopGUI | 6.12.2 |
| 2 | AutoStop | 1.0 |
| 3 | BetterRTP | 3.6.13 |
| 4 | BetterTeams | 4.12.0 |
| 5 | BlueSlimeCore | 2.9.6.454 |
| 6 | Chunky | 1.4.28 |
| 7 | CommandPanels | 3.21.5 |
| 8 | Essentials | 2.22.0-dev+37-264b0ed |
| 9 | HomeGUI | 1.4 |
| 10 | ItemEdit | 3.7.0 |
| 11 | LoginSecurity | 3.2.0 |
| 12 | LuckPerms | 5.4.131 |
| 13 | LuckPermsGUI | 1.7.1 |
| 14 | PlaceholderAPI | 2.11.6 |
| 15 | PvPManager | 3.18.44 |
| 16 | SimpleBounty | 1.0 |
| 17 | SimpleScore | 3.12.5 |
| 18 | SkinsRestorer | 15.8.0 |
| 19 | SmartSpawner | 1.3.4 |
| 20 | Vault | 1.7.3-b131 |
| 21 | voicechat | 2.5.26 |

---

## 🗂️ Recommended Repo Layout

Keep configs + docs in GitHub, keep runtime data local.

Suggested structure:
```
/ (server root)
  server.properties
  eula.txt
  spigot.yml
  bukkit.yml
  paper-global.yml
  paper-world-defaults.yml
  purpur.yml
  plugins/
    <PluginName>/
      config.yml
      ...
  Run.bat
  README.md
```

---

## 🛡️ Security Notes (must-read)

If you host publicly:
- ✅ Turn on whitelist:
  ```
  whitelist=true
  ```
- ✅ Use LoginSecurity (offline-mode) or switch to online-mode
- ✅ Keep OP list minimal
- ✅ Backup regularly

If a secret was ever committed:
- remove it
- rewrite history
- rotate credentials

---

## 🧯 Troubleshooting

### ❌ FAILED TO BIND TO PORT
- Make sure `server-ip=` is empty
- Check if port already in use:
```bat
netstat -ano | findstr :25565
```

### ❌ Friends can’t join from outside
- Check WAN IP in router:
  - `100.64.x.x – 100.127.x.x` = CGNAT → use playit.gg

### Lag / TPS drops
- Use spark:
  - `/spark profiler`
- Pregenerate chunks with Chunky

---

## 📄 License
Shared for learning and self-hosting. You are responsible for what you publish and how you host it.
