# FPVCam

FPVCam is a cross-platform video capture and streaming tool that works with the FPVDisplay mobile app for real-time video transmission.

## Downloads

Choose the appropriate version for your platform:

### Linux
- [fpvcam-x86_64](https://github.com/p9dev/fpvcam/releases/latest/download/fpvcam.x86_64) - For 64-bit systems
- [fpvcam-i386](https://github.com/p9dev/fpvcam/releases/latest/download/fpvcam.i386) - For 32-bit systems

### ARM Devices
- [fpvcam-arm64](https://github.com/p9dev/fpvcam/releases/latest/download/fpvcam.arm64) - For Raspberry Pi 4/5 (64-bit Ubuntu/Debian)
- [fpvcam-armhf](https://github.com/p9dev/fpvcam/releases/latest/download/fpvcam.armhf) - For Raspberry Pi 3 and below (32-bit)
- [fpvcam-aarch64](https://github.com/p9dev/fpvcam/releases/latest/download/fpvcam.aarch64) - For Android devices, embedded Linux, AWS Graviton

### macOS
- [fpvcam-macos](https://github.com/p9dev/fpvcam/releases/latest/download/fpvcam.macos) - For Intel/Apple Silicon

## Installation

### Dependencies

#### Linux (Ubuntu/Debian)

```bash
# For 64-bit systems
sudo apt-get update
sudo apt-get install -y \
libopencv-dev \
libboost-program-options-dev \
libboost-system-dev \
libssl-dev \
libsodium-dev

# For 32-bit systems
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install -y \
libopencv-dev:i386 \
libboost-program-options-dev:i386 \
libboost-system-dev:i386 \
libssl-dev:i386 \
libsodium-dev:i386
```

#### Raspberry Pi & ARM Devices

```bash
# For Raspberry Pi OS, Ubuntu/Debian based systems
sudo apt-get update
sudo apt-get install -y \
libopencv-dev \
libboost-program-options-dev \
libboost-system-dev \
libssl-dev \
libsodium-dev

# For other ARM Linux distributions
# Please refer to your distribution's package manager
```

#### macOS

```bash
brew install opencv boost libsodium
```

## Usage

1. Install the FPVDisplay app on your mobile device
2. Launch FPVDisplay and scan or create a new configuration QR code
   - Tap the QR code to view detailed connection information (IP, Port, UUID)
   - For LAN mode: Use your device's local IP address
   - For WAN mode: Use the public IP/domain shown in the app
3. Get the UUID from FPVDisplay
4. Run FPVCam:

```bash
# Basic usage
./fpvcam --ip <ip_address> --port <port> --uuid <uuid>

# Example (with custom resolution and frame rate)
./fpvcam --ip 192.168.1.100 --port 50505 --uuid abcd1234 --resolution 720p --fps 30

# WAN mode example
./fpvcam --ip example.com --port 60606 --uuid abcd1234
```
