# Changelog

## [0.7] - 2026-03-28

### Added
- **Driver Info page** — full list of installed drivers with version, date, manufacturer and category. Filter and export to CSV
- **GPU Health page** — GPU stats powered by nvidia-smi: temperature, core/mem clocks, fan speed, power draw, VRAM free/total
- **Full System Latency Checker** — 6-section latency report scored out of 100: timer resolution, DPC heuristic, disk I/O, memory, network ping, DNS. Save or copy results
- Architecture tweaks: Intel/AMD CPU and NVIDIA/AMD GPU specific tweaks unlocked at runtime based on detected hardware
- AMD GPU tweaks: deep sleep disable, Radeon Chill off, ULPS disable
- NVIDIA GPU tweaks: max perf mode, telemetry disable, shader cache, HDCP off
- Game tweaks: DWM flush rate, CPU priority via MMCSS, fullscreen optimizations, HPET disable
- Debloat tweaks: Aero Peek, Aero Shake, Snap Assist, menu delay, thumbnail cache, sticky keys
- Laptop detection with AC-only performance tweak

### Fixed
- `RunC` rewritten with `ProcessStartInfo` — `&&` chained commands now work correctly
- `Exec-Cmd` dispatcher added — PS: prefix routes to PowerShell, everything else to cmd
- GUID corruption in registry paths resolved
- Em dash encoding issue fixed
- Tweak state persistence via `voidtune_state.txt`
- FORCE ALL CORES now uses explicit power plan GUIDs to avoid failing after Ultimate Perf activation
- DISABLE TELEMETRY / DISABLE SUPERFETCH no longer report FAILED when service is already stopped
- DISABLE HPET no longer fails when `useplatformclock` was never set
- GPU Health: `\u{00B0}` replaced with `[char]176` for PowerShell 5.1 compatibility
- GPU Health: VRAM total now reads from registry (`HardwareInformation.qwMemorySize`) before falling back to WMI, fixing incorrect 4GB cap on modern GPUs
- nvidia-smi path detection made more robust with multiple candidate paths

## [0.6] - 2026-03

### Added
- Initial public release
- Dashboard with health score and bottleneck detection
- Tweaks: CPU, GPU, RAM, Network, Debloat, Power, Latency, Game, Restore
- Privacy tab
- App Installer via winget / Chocolatey
- Services manager with Gaming and Normal presets
- Process Monitor with bloat detection and kill sweep
- Hardware Diagnostics
- Benchmarks: disk, RAM, CPU, network, DNS
- Personalize: dark mode, transparency, accent color, wallpaper, taskbar, animations
- Startup Manager
- Backup & Restore with auto registry backup
- Script Runner
