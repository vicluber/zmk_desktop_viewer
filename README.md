# ZMK Reset Settings Firmware for Lily58

**Dedicated reset settings firmware** for Lily58 keyboard with Nice!Nano v2 controllers.

**Purpose:** 🔄 Specialized firmware for resetting keyboard settings and Bluetooth pairings

## What's Included

This firmware provides dedicated reset functionality:
- Bluetooth pairing management (clear all, select profiles)
- System reset and bootloader access
- Factory reset capabilities
- Automated GitHub Actions builds

## Getting the Firmware

### Download from GitHub Actions

1. Go to the **Actions** tab in this GitHub repository
2. Click on the latest green build run
3. Download the **firmware** artifact
4. Extract to get the reset settings `.uf2` files:
   - `lily58_left-nice_nano_v2-zmk.uf2` (Reset Settings Left)
   - `lily58_right-nice_nano_v2-zmk.uf2` (Reset Settings Right)

## Flashing

1. Put Nice!Nano into bootloader mode (double-tap reset button)
2. Copy the appropriate `.uf2` file to the mounted drive
3. Repeat for both halves (left and right)

## Current Files

- `build.yaml` - Defines reset settings build targets
- `config/west.yml` - ZMK dependencies
- `config/lily58.keymap` - Reset settings keymap
- `config/lily58.conf` - Reset configuration
- `.github/workflows/build.yml` - GitHub Actions build workflow

## Reset Functions Layout

**Single Reset Layer** with the following functions:
- **Top row:** BT_CLR_ALL, BT_SEL 0-4, BT_CLR, SYS_RESET
- **Middle row:** BT_PRV, BT_NXT, BOOTLOADER
- **Bottom row:** Additional reset functions

## Key Functions

- `BT_CLR_ALL` - Clear all Bluetooth pairings
- `BT_SEL 0-4` - Select specific Bluetooth profile
- `BT_CLR` - Clear current Bluetooth pairing
- `BT_PRV/NXT` - Navigate between Bluetooth profiles
- `SYS_RESET` - System reset
- `BOOTLOADER` - Enter bootloader mode

## Usage

1. Flash this firmware to reset keyboard settings
2. Use the reset functions as needed
3. Flash back to your normal firmware afterward

## Build Status

✅ **Working** - Builds reset settings firmware successfully  
🔄 **Purpose** - Dedicated reset and recovery firmware

## License

MIT License