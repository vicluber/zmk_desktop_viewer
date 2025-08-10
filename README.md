# ZMK Config for Lily58 with Nice!Nano v2

**Minimal working ZMK configuration** for Lily58 keyboard with Nice!Nano v2 controllers.

**Current Status:** ✅ Building successfully with ZMK defaults

## What's Included

This is a **minimal setup** that uses ZMK's built-in defaults for Lily58:
- Default QWERTY layout from ZMK
- Standard Lily58 key bindings 
- Default Bluetooth configuration
- Automated GitHub Actions builds

## Getting the Firmware

### Download from GitHub Actions

1. Go to the **Actions** tab in this GitHub repository
2. Click on the latest green build run
3. Download the **firmware** artifact
4. Extract to get the `.uf2` files:
   - `lily58_left-nice_nano_v2-zmk.uf2`
   - `lily58_right-nice_nano_v2-zmk.uf2`

## Flashing

1. Put Nice!Nano into bootloader mode (double-tap reset button)
2. Copy the appropriate `.uf2` file to the mounted drive
3. Repeat for both halves (left and right)

## Current Files

- `build.yaml` - Defines build targets (left/right halves)
- `config/west.yml` - ZMK dependencies
- `.github/workflows/build.yml` - GitHub Actions build workflow

**No custom configuration files** - uses ZMK's built-in Lily58 defaults.

## Default Layout

Uses ZMK's standard Lily58 layout:
- **Layer 0:** QWERTY
- **Layer 1:** Lower layer (symbols, F-keys)  
- **Layer 2:** Raise layer (numbers, navigation)
- **Layer 3:** Adjust layer (Bluetooth controls)

## Next Steps

This minimal setup provides a **working foundation**. You can add custom configuration by creating:
- `config/lily58.keymap` - Custom key layout
- `config/lily58.conf` - Hardware settings
- `config/Kconfig.defconfig` - Build configuration

## Build Status

✅ **Working** - Builds successfully on GitHub Actions  
✅ **Tested** - Minimal configuration verified

## License

MIT License