# ESP32-C6 Environmental Sensor Station & Data Logger

An open-source, 4-layer IoT environmental monitoring station and telemetry data logger powered by the **ESP32-C6-WROOM-1** microcontroller. This board utilizes multi-protocol wireless connectivity (Wi-Fi 6, BLE 5, and Zigbee/Thread) to read atmospheric and gas sensors, display local telemetry, and securely back up data to a local MicroSD card.

---

## 🛠 Core Features & Hardware

### 1. Processor & Wireless Connectivity
* **MCU:** ESP32-C6-WROOM-1
* **Programming/Debugging:** On-board dual-purpose interfaces for flashing and debugging via a protected USB-C 2.0 interface.
* 
### 2. Comprehensive Sensor Array
* **SCD41-D-R2:** Photoacoustic $CO_2$ sensor measuring true carbon dioxide levels in ppm ($I^2C$ Address: `0x62`).
* **SGP41-D-R4:** Digital gas sensor providing multi-pixel MOx sensing for VOC (Volatile Organic Compounds) and $NO_x$ (Nitrogen Oxides) indoor environmental indexes ($I^2C$ Address: `0x59`).
* **HDC2033:** Low-power, high-accuracy digital temperature and relative humidity sensor ($I^2C$ Address: `0x44`).

### 3. Storage & User Interface
* **MicroSD Card Slot:** Dedicated SPI-driven logging interface with individual inline trace damping resistors and pull-ups for secure local data logging.
* **OLED Display (SSD1306):** 0.96" $I^2C$ graphic display panel for live visual terminal outputs and local troubleshooting ($I^2C$ Address: `0x3C`).

### 4. Power & Battery Management
* **Charging:** TP4056 lithium battery management IC with automated charge/discharging  indicator LEDs.
* **Power Path Switching:** Automated hardware power routing utilizing an AO3401A P-Channel MOSFET to seamlessly switch between USB power and Battery power.
* **Regulator:** AP2112K-3.3V Ultra-low dropout, low-noise LDO regulator supplying clean $3.3\text{V}$ power rails up to $600\text{mA}$ to the wireless MCU and sensors.

---

## 🎛 4-Layer PCB Stackup Architecture

This board is structured with an optimized 4-layer stackup:

* **Layer 1 (Top Copper - F.Cu):** High-speed digital signals, data busses ($I^2C$, SPI), and  component placement.
* **Layer 2 (Internal Plane 1 - In1.Cu):** Solid Ground Plane (GND) providing direct, uninterrupted return paths for low EMI noise and optimal RF shielding.
* **Layer 3 (Internal Plane 2 - In2.Cu):** Split Power Plane ($+5\text{V}$, $+3.3\text{V}$, $\text{VBAT}$) providing low-impedance power distribution directly below signal lines.
* **Layer 4 (Bottom Copper - B.Cu):** Secondary signal traces and clean copper pours for thermal dissipation.
