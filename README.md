# PUBG Recoil Macro

A modular C++ recoil compensation tool for PUBG, built with ImGui and DirectX 9.

## Features
- Per-weapon recoil profiles (AR, SMG, LMG, DMR) with configurable parameters
- Scope-based recoil scaling (1x–8x)
- Attachment modifiers (compensator, grips, stocks)
- Recoil curve simulation (vertical + horizontal per shot)
- Crouch modifier, first-shot multiplier, and recovery speed
- Preset save/load system
- In-game overlay UI with weapon switching via combo keys

## Prerequisites
- [MSYS2](https://www.msys2.org/) with `ucrt64` environment
- MinGW-w64 g++ (included with MSYS2)

## Build
Open **MSYS2 UCRT64** terminal, then:

```bash
cd /path/to/recoil

g++ -O2 -static -static-libgcc -static-libstdc++ -std=c++17 -mwindows \
  -Isrc \
  src/recoil_main.cpp src/recoil_config.cpp src/recoil_state.cpp \
  src/recoil_settings.cpp src/recoil_game.cpp src/recoil_input.cpp \
  src/recoil_engine.cpp src/recoil_platform.cpp src/recoil_ui.cpp \
  src/recoil_log.cpp \
  vendor/imgui/imgui.cpp vendor/imgui/imgui_draw.cpp \
  vendor/imgui/imgui_tables.cpp vendor/imgui/imgui_widgets.cpp \
  vendor/imgui/imgui_impl_win32.cpp vendor/imgui/imgui_impl_dx9.cpp \
  -lgdi32 -luser32 -ld3d9 -ldwmapi -lshell32 -lwinmm \
  -o recoil_ui.exe
```

Output: `recoil_ui.exe`

## Configuration
- `config.ini` — weapon data, attachment stats, scope scaling, combo keys
- `recoil_settings.ini` — per-category power values, arm state, theme
- `recoil_presets.ini` — saved loadout presets

## Project Structure
```
assets/          JSON weapon/attachment data
src/             C++ source files
vendor/imgui/    Dear ImGui library
config.ini       Main configuration
```

## Credits
- **Developer** — Seno
- [Dear ImGui](https://github.com/ocornut/imgui) — GUI library (ocornut)

## Disclaimer
This tool modifies game input. Use at your own risk.
