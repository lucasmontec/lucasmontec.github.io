---

name: I2C Tool
type: Tool
featured: false

# Listing settings

font_awesome_icon: fa-microchip

bg: assets/images/i2c.png

one_liner: A tool to debug and interact with i2c devices.

source_code_url: https://gitlab.com/lucasmontec/platformio-arduino-projects/-/tree/master/I2CTool?ref_type=heads

description: |
    This I2C Tool is designed to facilitate interaction with I2C devices directly from the serial command line. It allows users to scan the I2C bus for devices, send bytes to specific addresses, send bytes to all addresses, request bytes from devices, and manipulate the I2C bus configuration. 

---

### The  Tool

I made this tool to work with Chinese I2C devices that have very little to no documentation. It's basically a tool that exposes I2C to the serial interface but also provides a few utilities like creating aliases, scanning addresses and such.

### Features

- **Scan the I2C bus** for connected devices.

- **Send bytes** to a specific device on the bus.

- **Broadcast bytes** to all devices on the bus.

- **Request bytes** or a **word** from a device, with optional byte order reversal.

- **Configure I2C** in runtime.
