# ZMK Config for Lily58 with Nice!Nano v2

Simple ZMK configuration for Lily58 keyboard with Nice!Nano v2 controllers.

## Features

- Standard QWERTY layout
- 4 layers (default, lower, raise, adjust)
- Bluetooth connectivity with 5 profiles
- Basic function keys and symbols

## Getting the Firmware

### Option 1: Download from GitHub Actions (Recommended)

1. Push changes to this repository
2. Go to the **Actions** tab in GitHub
3. Click on the latest build run
4. Download the **firmware** artifact
5. Extract to get the `.uf2` files

### Option 2: Build Locally

```bash
# Clone and setup
git clone <your-repo>
cd <repo-name>
west init -l config
west update
west zephyr-export

# Build left half
west build -s zmk/app -b nice_nano_v2 -- -DSHIELD=lily58_left -DZMK_CONFIG="$(pwd)/config"

# Build right half  
rm -rf build
west build -s zmk/app -b nice_nano_v2 -- -DSHIELD=lily58_right -DZMK_CONFIG="$(pwd)/config"
```

## Flashing

1. Put Nice!Nano into bootloader mode (double-tap reset)
2. Copy the appropriate `.uf2` file to the mounted drive:
   - `lily58_left-nice_nano_v2-zmk.uf2` for left half
   - `lily58_right-nice_nano_v2-zmk.uf2` for right half
3. Repeat for both halves

## Layout

### Layer 0 (Default)
Standard QWERTY with layer access keys.

### Layer 1 (Lower) 
Function keys F1-F12 and symbols.

### Layer 2 (Raise)
Numbers and arrow keys.

### Layer 3 (Adjust)
Bluetooth controls (BT_CLR, BT_SEL 0-4).

## Bluetooth Pairing

- **BT_CLR**: Clear current profile
- **BT_SEL 0-4**: Select Bluetooth profile (0-4)
- Access via Layer 3 (hold Lower + Raise simultaneously)

## Configuration Files

- `build.yaml`: Build targets
- `config/west.yml`: ZMK dependencies  
- `config/lily58.keymap`: Key layout
- `config/lily58.conf`: Hardware settings
- `.github/workflows/build.yml`: GitHub Actions build

## License

MIT License