# Recoiless

Recoiless is a native Windows recoil compensation app for PUBG PC. The app is
category-based, so tuning is done by weapon category such as AR, SMG, LMG, DMR,
or SR instead of individual weapon profiles.

## Quick Start

1. Run `recoil_ui.exe` as Administrator.
2. Choose a weapon category in the `Weapons` tab.
3. Match the in-game scope and attachments.
4. Press `Insert` to arm or disarm.
5. Hold the selected trigger button while firing.
6. Press `Home` to hide or show the UI.

The app compensates only when PUBG is detected, PUBG is focused, the app is
armed, and the trigger is held.

## Features

### Category Recoil Control

- Tune recoil by category, not by specific weapon.
- Categories use pooled recoil data for stable default behavior.
- Scope, muzzle, grip, and stock selections affect compensation.
- Only valid scope and attachment options are shown for each category.

### Smooth Recoil Movement

- Recoil is delivered as continuous planned movement.
- Shot movement overlaps slightly to reduce rough step-like motion.
- Fractional movement is preserved so small corrections are not lost.
- `Max Y` can cap vertical movement or be set to `0` for unlimited pull-down.

### Power Tuning

- `Global Power` controls the base compensation strength.
- Each category has its own tune offset.
- Effective category power is clamped from `1` to `99`.
- Global power and category tune are adjusted from the `Weapons` tab.
- Presets and Train results update the selected category power cleanly.

### Header Status

The top header shows active category, scope, and app status.

| Status | Meaning |
|---|---|
| `OFFLINE` | PUBG is not detected |
| `IDLE` | PUBG is running but not focused |
| `READY` | App is armed and ready |
| `FIRING` | Compensation is active |
| `PAUSED` | App is disarmed |

On narrow windows the status switches to compact labels like `OFF`, `FIRE`, and
`PAUSE` so the header does not get clipped.

### Toast Notifications

- Toggle actions show short enabled or disabled feedback.
- Shortcut actions show feedback even when the main UI is hidden.
- Category and scope shortcut changes show the active selection.
- Duplicate app launches show that Recoiless is already active.

### Presets

- Save category, scope, attachments, power, and Max Y.
- Load a preset by clicking its row.
- Remove a preset with the centered `X` action.
- Active preset rows are highlighted.
- Up to 16 presets are supported.

### Train Calibration

Train mode calibrates the selected category and scope from wall-shot samples.

- Captures the center screen area after single shots.
- Detects bullet-hole drift from the crosshair center.
- Calculates recommended power.
- Fits vertical and horizontal recoil curves.
- Applies trained curves to the selected category.
- Saves trained curves so they persist after restart.
- Supports BMP upload for capture-based analysis.

Train needs at least 3 valid samples before analysis can run.

### Image Upload

- `Load BMP...` imports a screenshot and tries to detect a bullet-hole sample.
- `Save BMP...` exports the current training capture region.
- Useful for checking if bullet-hole detection is reading the correct area.

### Overlay HUD

Overlay mode shows a compact in-game control view.

- Category and scope
- Game status
- Firing indicator
- Armed or safe state
- Active preset name
- Power
- Vertical and horizontal output
- Ammo counter
- FPS graph
- Arm/disarm button
- Full UI button
- Exit button

### Settings

- Trigger button selection: `LMB`, `XB1`, `XB2`, or `RMB`.
- Arm key selection.
- Start armed option.
- Coach mode toggle.
- Weapon-only detect toggle.
- Detection coordinate tuning.
- Theme selection.
- Create, replace, and remove combo key bindings.

### Single Instance

- Only one app instance can stay active.
- Launching the app again signals the existing instance instead of duplicating it.
- Closing the app stops the recoil thread and cleans app-owned processes.

### App Branding

- Modern app icon.
- Logo asset for the UI.
- Consistent ASCII labels and status text.

## Controls

| Key | Action |
|---|---|
| `Insert` | Arm or disarm |
| `Home` | Hide or show UI |
| `LMB` | Default trigger button |

Trigger and arm bindings can be changed in the app settings.
