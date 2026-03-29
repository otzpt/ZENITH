# VOIDTUNE
> Windows optimization suite for gamers and power users.

[![Version](https://img.shields.io/badge/version-0.7-7c3aed?style=flat-square)](https://github.com/otzpt_dev/voidtune/releases)
[![License](https://img.shields.io/badge/license-GPL%20v3-22c55e?style=flat-square)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-38bdf8?style=flat-square)]()
[![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-blue?style=flat-square)]()

**[🌐 Website](https://voidtune-optimizer.netlify.app/) • [📦 Releases](https://github.com/otzpt_dev/voidtune/releases) • [🐛 Issues](https://github.com/otzpt_dev/voidtune/issues)**

---

VOIDTUNE is a free, open-source Windows optimizer and debloater built with PowerShell 5.1+ and WPF/XAML. It gives gamers and power users a clean, dark UI to apply system tweaks, manage services, monitor hardware, and install apps — all in one place, without touching the command line.

Visit the official site at **[voidtune-optimizer.netlify.app](https://voidtune-optimizer.netlify.app/)** for more info and screenshots.

---

## Features

### Tweaks
Apply and revert registry tweaks, power plan changes, and system settings across multiple categories:
- **CPU** — High performance plan, Win32 priority, timer resolution, core parking, boost modes
- **GPU** — Hardware GPU scheduling, TDR delay, Direct Flip, MPO disable, GPU priority
- **RAM** — Disable paging executive, large system cache, memory compression
- **Network** — TCP no delay, Fast Open, RSS, DNS flush, QoS throttle removal
- **Debloat** — Telemetry, Cortana, Game Bar, animations, mouse acceleration, Superfetch
- **Power** — Balanced, High Performance, Ultimate Performance (hidden plan)
- **Latency** — App kill timeout, NTFS optimization, IRQ priority, HPET disable
- **Game** — Game Mode, MMCSS scheduling, fullscreen optimizations, DWM flush rate
- **Restore** — One-click revert to Windows defaults
- **Architecture tweaks** — Intel/AMD CPU and NVIDIA/AMD GPU specific tweaks unlocked at runtime based on detected hardware

All tweaks show their current applied state and can be individually reverted.

### Dashboard
Real-time CPU and RAM usage, health score, bottleneck detection, quick stats on applied tweaks, backups, and running processes.

### App Installer
Install common apps via winget (Chocolatey fallback) — browsers, dev tools, gaming launchers, hardware monitors, media, security tools — all in one click.

### Services
Toggle, stop, start and profile Windows services. Includes Gaming and Normal presets, dependency warnings, and a disable-all option.

### Process Monitor
View top processes by RAM usage, tag known bloat automatically, kill individual processes or sweep all bloat in one click.

### Hardware Diagnostics
Full hardware info cards: CPU, GPU, RAM, Disk, OS, Motherboard, Uptime. Driver version and build info included.

### Driver Info
Full list of installed drivers with version, date, manufacturer and category. Filter by name, category or manufacturer. Export to CSV.

### GPU Health
GPU name, vendor, driver version and date, VRAM total and free, GPU usage, temperature, core clock, memory clock, fan speed, power draw. Powered by nvidia-smi on NVIDIA systems.

### Full System Latency Checker
Six-section latency report: timer resolution, DPC heuristic, disk I/O, memory, network ping, DNS resolution. Scored out of 100 with recommendations. Results can be copied or saved to file.

### Benchmarks
Quick in-app benchmarks: disk write, disk read, RAM throughput, CPU prime sieve, network ping, DNS resolution. History log included.

### Privacy
Block telemetry, ads, camera, microphone, location, Cortana, activity feed and Windows Update.

### Personalize
Toggle dark mode, transparency, rounded corners, taskbar items, accent colors, wallpaper, ClearType, animations, AeroPeek, and more — with live preview and Explorer restart.

### Startup Manager
View and disable startup entries from HKCU and HKLM.

### Backup & Restore
Auto registry backup before every apply. Manual backup and Windows restore point creation. Restore from any saved backup.

### Script Runner
Run CMD or PowerShell commands directly with full admin rights from inside VOIDTUNE.

---

## Requirements

- Windows 10 (Build 19041+) or Windows 11
- PowerShell 5.1 or newer
- Administrator privileges (auto-requested on launch)
- winget (recommended) or Chocolatey for App Installer

---

## Installation

VOIDTUNE does not require installation. Just download and run.

**Option A — Run from source**

1. Clone the repository:
   ```
   git clone https://github.com/otzpt_dev/voidtune.git
   ```
2. Right-click `LAUNCH_VOIDTUNE.bat` → Run as Administrator

**Option B — Download zip**

1. Go to [Releases](https://github.com/otzpt_dev/voidtune/releases)
2. Download the latest zip and extract it — keep all files and folders together
3. Right-click `LAUNCH_VOIDTUNE.bat` → Run as Administrator

> **Note:** All files (`core\`, `modules\`, `ui\`, `*.xaml`) must stay in the same folder. Do not move files around.

---

## Building the EXE

Requires [ps2exe](https://github.com/MScholtes/PS2EXE):

```powershell
Install-Module ps2exe -Scope CurrentUser
Invoke-PS2EXE .\VOIDTUNE.ps1 .\VOIDTUNE.exe -noConsole -requireAdmin -title "VOIDTUNE" -version "0.7.0.0"
```

---

## Contributing

Contributions are welcome. If you want to add tweaks, fix bugs, or improve the UI:

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "add: your feature"`
4. Push and open a Pull Request

For new tweaks, add them to `modules/data.ps1` following the existing `[TI]` model. Include a `RevertCmd` wherever possible.

For bug reports, open an issue with your Windows build, hardware info, and the relevant lines from `logs/voidtune_*.log`.

---

## Disclaimer

VOIDTUNE modifies Windows registry entries, services, and system settings. Use at your own risk. Always create a backup or restore point before applying tweaks. The author accepts no responsibility for data loss, system instability, or any other issues arising from use of this software.

---

## License

VOIDTUNE is licensed under the [GNU General Public License v3.0](LICENSE).

You are free to use, modify, and distribute this software under the terms of the GPL v3. Any derivative work must also be distributed under the same license.

Copyright (C) 2026 [@otzpt_dev](https://github.com/otzpt_dev) • [voidtune-optimizer.netlify.app](https://voidtune-optimizer.netlify.app/)
