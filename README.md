## ESP Light Project

## Overview
This project is designed for ESP32/ESP32-Cx series microcontrollers and provides a firmware solution for controlling lights. It leverages the ESP-IDF framework and supports various ESP chipsets, including ESP32, ESP32C2, ESP32C3, ESP32C5, ESP32C6, ESP32H2, ESP32P4, and ESP32S3. The project is modular, supporting multiple components and configurations for different hardware and use cases.

## Features
- Light control firmware for ESP32/ESP32-Cx series
- Modular component structure using ESP-IDF managed components
- Support for multiple chipsets and configurations
- OTA (Over-the-Air) update support
- Diagnostics and insights integration
- Secure certificate management
- LED strip and button support
- mDNS and network discovery
- CBOR and JSON parsing/generation

## Directory Structure
- `main/` - Main application source code
  - `app_main.cpp` - Main entry point
  - `app_driver.cpp` - Light driver logic
  - `app_priv.h` - Private header definitions
  - `CMakeLists.txt` - Build configuration for main app
  - `idc_component.yml` - Component manifest
  - `Kconfig.projbuild` - Project configuration options
  - `certification_declaration/` - Certification files
- `managed_components/` - ESP-IDF managed components (button, cbor, diagnostics, led_strip, etc.)
- `build/` - Build output directory (generated after build)
- `CMakeLists.txt` - Top-level build configuration
- `partitions.csv` - Partition table for flash layout
- `sdkconfig*` - SDK configuration files for various chipsets and build options

## Getting Started
### Prerequisites
- ESP-IDF (v5.x or later) installed and configured ([ESP-IDF Setup Guide](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/))
- Supported ESP32/ESP32-Cx hardware
- Python 3.x

### Build and Flash
1. **Set up ESP-IDF environment:**
    ```sh
    . $HOME/esp/esp-idf/export.sh
    ```
2. **Configure the project:**
    ```sh
    idf.py menuconfig
    ```
3. **Build the project:**
    ```sh
    idf.py build
    ```
4. **Flash to device:**
    ```sh
    idf.py -p <PORT> flash
    ```
    Replace `<PORT>` with your device's serial port (e.g., `/dev/ttyUSB0`).

### Partition Table
The `partitions.csv` file defines the flash memory layout. You can customize it as needed for your application.

### Configuration
- Use the appropriate `sdkconfig.defaults.*` file for your target chipset and features.
- Additional configuration can be done via `menuconfig`.

## Components
This project uses several ESP-IDF managed components, including:
- `button` - Button handling
- `cbor` - CBOR encoding/decoding
- `esp_diag_data_store` - Diagnostics data storage
- `esp_diagnostics` - Diagnostics framework
- `esp_encrypted_img` - Encrypted image support
- `esp_insights` - Insights and telemetry
- `esp_rcp_update` - RCP update support
- `esp_secure_cert_mgr` - Secure certificate management
- `esp-serial-flasher` - Serial flashing utility
- `jsmn`, `json_generator`, `json_parser` - JSON support
- `led_strip` - LED strip control
- `mdns` - mDNS support
- `rmaker_common` - RainMaker common utilities

## Certification
Certification-related files are located in `main/certification_declaration/`.

## Contributing
1. Fork the repository and create your branch.
2. Commit your changes with clear messages.
3. Push to your fork and submit a pull request.

## License
See the `LICENSE` file for license information.

## References
- [ESP-IDF Documentation](https://docs.espressif.com/projects/esp-idf/en/latest/)
- [ESP-IDF Component Registry](https://components.espressif.com/)

---
For more details, refer to the source code and comments within each file.
