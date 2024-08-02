---
layout: default
---

# Boards

Under construction!

## USB Source-Measure
- **Microcontroller**: ESP32-S3, **Power**: USB-C PD (FUSB302)
- **Firmware**: ESPHome with custom drivers
- **Links**: [HDL Source](https://github.com/BerkeleyHCI/PolymorphicBlocks/blob/master/examples/test_usb_source_measure.py)
  [Layout](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/UsbSourceMeasure)
  [Firmware](https://github.com/ducky64/edg-pcbs/blob/main/IoTDevices/iotusbsourcemeasure.yml),
  [PC Interface](https://github.com/ducky64/edg-pcbs/tree/main/IoTDevices/SmuRemoteControl),
  [Case (OpenSCAD)](https://github.com/ducky64/edg-pcbs/tree/main/UsbSmu/mechanical)
  - **Note**: while the current revision (v3) is functional with blue wire fixes, another revision v3.1 is planned.
- **Notable features**: discrete synchronous buck-boost converter driven by the ESP32, analog feedback controls for current and voltage (voltage setpoint + current limits), current ranging circuit, local interface with OLED and encoder + 4-way switch

Device specs:
- **Output / measurement range**: 0 - 30V, -3 - +3A (two quadrant operation; electrical limits, thermal limits may be lower)
- **Output resolution**: 10mV, 10mA / 1mA (for 3A / 300mA ranges) (12-bit DAC, MCP4728)
- **Measurement resolution** (noise floor): 1mV, 100uA / 10uA (for 3A / 300mA ranges) (24-bit ADC, MCP3561)

## Stick BLE Multimeter
- **Microcontroller**: nRF52840, **Power**: internal 1xAA (Alkaline or LFP or Li-ion)
- **Firmware**: mbed + PlatformIO
- **Links**: [HDL Source](https://github.com/BerkeleyHCI/PolymorphicBlocks/blob/master/examples/test_multimeter.py),
  [Layout](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/Multimeter),
  [Firmware](https://github.com/CalSol/Devops-BLE-FW/tree/main/Multimeter),
  [Android app](https://github.com/ducky64/BleMultimeterApp),
  [Case (FreeCAD)](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/Multimeter/mechanical)
  - **Note**: another revision (v3) is planned to improve measurement noise.
- **Notable features**: measurement and constant-current driver ranging circuits

Inspired by the [TI BLE multimeter reference design](https://www.ti.com/tool/TIDA-01012).

Device specs:
- **Modes**: voltage / resistance / diode / continuity
- **Measurement ranges**: 1:1, 1:10, 1:100, 1:1000 voltage attenuation
  - High voltage withstand (>40V) NOT physically tested (yet)
- **Current driver ranges**: 1uA, 10uA, 100uA, 1mA; with PWM DAC for fine control
- **Measurement resolution** (noise floor): ~4 digits (24-bit ADC, MCP3561)

## E-ink Calendar
- **Microcontroller**: ESP32-S3, **Power**: 4xAA NiMH (expected 1 year battery life), accepts any 4.5-20v source
- **Firmware platform**: Arduino + PlatformIO
- **Links**: [HDL Source](https://github.com/BerkeleyHCI/PolymorphicBlocks/blob/master/examples/test_iot_display.py),
  [Layout](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/IotDisplay),
  [Firmware](https://github.com/ducky64/edg-pcbs/tree/main/IoTDisplay),
  [Image server](https://github.com/ducky64/eink-svg-server)
- **Notable features**: low sleep current (80uA), reverse input protected, e-ink display, display templates in SVG

## IoT Fan Driver
- **Microcontroller**: ESP32-C3, **Power**: 12v barrel jack
- **Firmware platform**: ESPHome
- **Links**: [HDL Source](https://github.com/BerkeleyHCI/PolymorphicBlocks/blob/master/examples/test_iot_fan.py),
  [Layout](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/IotFan),
  [Firmware](https://github.com/ducky64/edg-pcbs/blob/main/IoTDevices/iotfandriver_r2.yml)
  - Note: broken ground plane significantly reduces RF performance, can be fixed with blue wire
- **Notable features**: discrete RF layout, programmatically generated LED ring layout using SVG-PCB

## Multilevel Converter Prototype
- **FPGA**: iCE40UP5k
- **Gateware**: Chisel
- **Links**: [HDL Source](https://github.com/BerkeleyHCI/PolymorphicBlocks/blob/master/examples/test_fcml.py),
  [Layout](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/Fcml),
  [RTL](https://github.com/calisco/fcml-rtl)
- **Notable features**: FPGA, multilevel converter generator (this device is 4-level)

## Soldering Iron Controller
- **Microcontroller**: ESP32-S3, **Power**: USB-C PD (FUSB302)
- **Firmware**: ESPHome
- **Links**: [HDL Source](https://github.com/BerkeleyHCI/PolymorphicBlocks/blob/master/examples/test_iot_iron.py),
  [Layout](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/IotIron),
  [Firmware](https://github.com/ducky64/edg-pcbs/blob/main/IoTDevices/iotiron.yml)
- **Notable features**: discrete synchronous buck converter driven by the ESP32, compatible with JBC cartridges

## "Owlbot"
- **Microcontroller**: ESP32-S3 socketed dev board
- **Firmware**: Arduino IDE / ESPHome
- **Links**: [HDL Source](https://github.com/BerkeleyHCI/PolymorphicBlocks/blob/master/examples/test_robotowl.py),
  [Layout](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/RobotOwl),
  [Course lab manual](https://github.com/ducky64/lacc23-embedded/blob/lacc-23/lab2_1.md)

## CANdapter
- **Microcontroller**: LPC1549
- **Firmware**: mbed + PlatformIO
- **Links**: [HDL Source](https://github.com/BerkeleyHCI/PolymorphicBlocks/blob/master/examples/test_can_adapter.py),
  [Layout](https://github.com/BerkeleyHCI/PolymorphicBlocks/tree/master/examples/CanAdapter),
  [Firmware](https://github.com/CalSol/Devops-FW/tree/main/Candapter)
