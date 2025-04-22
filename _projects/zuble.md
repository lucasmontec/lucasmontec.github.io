---
name: ZuBle
type: Library

font_awesome_icon: fa-bluetooth

one_liner: A unity library to use BLE Devices.

source_code_url: https://gitlab.com/lucasmontec/zuble-unity-ble-library
source_code_phrase: The source code is avaliable at GitLab.

description: This is a simple wrapper around android's BLE capabilities.

---

###  Zumbie Bluetooth Low Energy Unity Library

​	This is a simple wrapper around android's BLE capabilities. This is a complete jerry-rig implementation. I'll try to improve on-demand. This library currently only handles a single device per connection.

### Features

- Scan BLE Devices with callbacks.
- Connect async and callback.
- Write and read with any Gatt addresses.

### Example project

I use this library to code my remote control in unity to control my cat robot. That's an ESP32 based robot that I have built and I needed a bluetooth LE library on unity to make the app for it.
Here's the controller project: https://gitlab.com/lucasmontec/catbot-ble-controller

It's very rough but it allows me to develop the robot and test it directly.