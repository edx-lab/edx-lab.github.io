# GECKO Lite W | EDX_LAB
## 3D printing files and build guide (EN)

**Project:** GECKO Lite W — Compact Wireless Security Tool  
**Creator:** EduSicilia | EDX_LAB  
**Official website and documentation hub:** **https://edx-lab.github.io/**  
**Firmware source code and documentation:** https://github.com/edx-lab/GECKO-Lite-W  
**Official firmware v1.0.0:** https://github.com/edx-lab/GECKO-Lite-W/releases/tag/v1.0.0

> **IMPORTANT:** This ZIP contains 3D models for making the GECKO Lite W enclosure. **Physical electronic components are not included.** The EDX_LAB website is the central reference for documentation, bill of materials, downloads and news.

## 1. What is GECKO Lite W?

GECKO Lite W is an ESP32-S3-based portable device with a color screen and physical controls, developed for wireless security learning, experimentation and analysis **on your own systems or systems you are explicitly authorized to test**. It runs a version of the Bruce firmware adapted to this particular hardware. The enclosure is designed for FDM 3D printing and can be customized using the STEP files.

### Device specifications

| Item | Specification |
| --- | --- |
| Microcontroller | ESP32-S3 N16R8 |
| Memory | 16 MB Flash + 8 MB PSRAM |
| Wireless connectivity | Integrated Wi-Fi and Bluetooth Low Energy |
| Display | 2.0-inch ST7789V SPI TFT; 240 × 320 physical pixels, 320 × 240 landscape UI |
| Controls | 5-direction joystick, center press, 2 additional buttons |
| Storage | SPI microSD card reader (separate bus from display) |
| Battery | 3.7 V, 800 mAh 802540 LiPo battery |
| Charging | Separate USB-C LiPo charging module |
| Power | DC-DC step-up converter and output filtering |
| Audio | Passive buzzer |
| Firmware | GECKO Lite W v1.0.0, based on Bruce |
| Enclosure production | FDM/FFF 3D printing |

These specifications apply to the documented GECKO Lite W build. They do not guarantee compatibility with other ESP32-S3 boards, screens, or visually similar modules.

## 2. What's in the download

- **STL files:** enclosure parts ready to prepare in a 3D printer slicer.
- **STEP/STP files:** editable CAD geometry for customization.
- **This README:** printing, assembly, safety information and official links.

Check the actual package folders and part names. Firmware and source code are distributed **separately on GitHub**. The illustrated bill of materials (BOM), in Spanish and English, with component photographs and purchasing links, is available through the official website; it may also be included as separate documentation.

## 3. Required electronic components

The build uses the following main components (one of each):

1. ESP32-S3 N16R8 (16 MB Flash, 8 MB PSRAM).
2. 2-inch ST7789V SPI TFT display.
3. 3.7 V, 800 mAh 802540 LiPo battery.
4. 5-way joystick module with two SET/RST buttons.
5. USB-C LiPo battery charging module.
6. Miniature slide on/off switch.
7. DC-DC step-up converter.
8. SPI microSD card reader and a compatible microSD card.
9. Two-pin passive buzzer.

**Additional supplies:** wiring, connectors and mounting materials; **100 nF + 10 µF** capacitors in parallel at the step-up output; a battery-voltage sensing divider using **two 100 kΩ resistors and one 100 nF capacitor** from the divider midpoint to GND. Check component values, placement and connections against the technical documentation before soldering.

**Illustrated BOM and links to the exact modules:** https://edx-lab.github.io/

## 4. Suggested print settings

| Setting | Starting recommendation |
| --- | --- |
| Process | FDM / FFF |
| Material | PLA or PETG |
| Nozzle | 0.4 mm |
| Layer height | 0.20 mm |
| Walls | 4 perimeter lines as a starting point |
| Top and bottom layers | 5 |
| Infill | 30% gyroid |
| Supports | Only when required by the selected part orientation and slicer preview |
| Orientation | Choose a stable build surface while preserving visible finishes and functional openings |
| Print time and material | Depend on slicer, printer and material; calculate before printing |

These are **suggested starting settings**, not a validated profile for every printer. Actual wall thickness is determined by the CAD geometry and **is not necessarily equivalent** to the slicer's perimeter count. Do not scale parts; scaling changes fits and module clearances.

## 5. Assembly and checks

1. **Before printing:** load every STL in your slicer, check that you have the complete part set, and inspect orientation and possible supports. Do not rescale.
2. **Print the parts:** use consistent material/settings where fit matters. Allow parts to cool before removing them from the build plate.
3. **Finishing:** remove supports if used and gently clean holes, tabs, slots and mating surfaces. Do not force parts together.
4. **Dry fit:** temporarily position the screen, ESP32-S3, joystick, microSD reader, switch, battery and other modules. Check space for wiring, connectors and closure before fastening or soldering.
5. **Wiring:** follow the official GECKO Lite W wiring information/pinout. Pay particular attention to common ground, power rails and battery polarity. Do not switch on until the wiring is checked.
6. **Electrical inspection:** with the battery disconnected, examine solder joints, continuity, shorts and the DC-DC converter's configured output voltage. Use a multimeter; do not assume the module arrives with the correct output setting.
7. **First power-on:** test the display, joystick, buttons, microSD, buzzer and battery measurement before fully closing the enclosure.
8. **Final closure:** arrange wiring so it cannot be pinched. Secure the battery without piercing, squeezing or exposing it to sharp edges. Close using the fastening features provided by your printed version.
9. **Firmware:** download the official release and follow the installation instructions supplied on GitHub.

### Firmware v1.0.0 quick GPIO reference

| Signal | GPIO |
| --- | --- |
| TFT: CLK / MOSI / CS / DC / RST | 12 / 11 / 10 / 9 / 8 |
| microSD: CLK / MOSI / MISO / CS | 14 / 13 / 16 / 15 |
| Joystick: up / down / left / right | 4 / 5 / 6 / 7 |
| Joystick center press | 21 |
| B1 / SET | 17 |
| B2 / RST | 18 |
| Battery ADC sensing | 1 (midpoint of 100 kΩ / 100 kΩ divider) |
| Buzzer | 38 |

Controls are active-low with internal pull-ups. In this build, the display **BL pin is connected to 3.3 V**. This table **is not a complete wiring schematic**. Always consult the latest repository documentation before wiring the electronics.

## 6. Firmware and first installation

Firmware is not necessarily bundled with this enclosure ZIP. Download it from:

**https://github.com/edx-lab/GECKO-Lite-W/releases/tag/v1.0.0**

For a first installation, use the combined binary **`Gecko-esp32-s3-n16r8.bin`**, flashed at address **`0x0`**, as documented in the official installation guide. **`firmware.bin` contains the application only and must not be flashed at `0x0`.** Follow `INSTALACION.md` in the official release for full instructions, port configuration, updates and warnings concerning settings stored in flash.

## 7. Safety and responsible use

**Battery and charging**
- Use a suitable LiPo battery and charger. Respect polarity, voltage/current limits and manufacturer guidance.
- Never short, pierce, crush, deform or overheat the battery. Stop using damaged or swollen cells and arrange safe battery recycling.
- Do not charge on flammable surfaces; supervise initial charge tests. Verify charging-circuit behavior before routine use.
- Do not assume the charger provides every protection feature: check the actual protections provided by your battery and charging hardware.

**Electronics and printing**
- Disconnect power and battery before handling wiring, solder joints or modules. Prevent shorts, reverse polarity and contact between energized parts and metal tools.
- A PLA/PETG printed enclosure is not certified electrical insulation, thermal protection, waterproofing or impact protection.
- Keep out of reach of small children: the build contains small parts and a lithium battery.
- This is not a certified product and is not intended for medical, safety-critical industrial or personal-protection use.

**Wireless security and legal requirements**
- Security analysis and testing features must be used **only on your own networks/devices or with explicit authorization**.
- Certain functions may disrupt network/device availability. Follow applicable laws and do not interfere with, capture from, or run intrusive tests against third-party systems.
- The builder/user is responsible for electrical safety and lawful operation.

## 8. Support, community and official channels

**All EDX_LAB documentation, project news and updates:**  
https://edx-lab.github.io/

**Source code, issues and firmware releases (GitHub):**  
https://github.com/edx-lab/GECKO-Lite-W

**Creator on Cults3D:** search for **EduSicilia**.  
**Social media and other channels:** use the links provided on the **official EDX_LAB website** to find authentic, current accounts. Do not assume that similarly named accounts are affiliated with the project.

For build-related support, specify the board/display model, firmware version, exact symptoms and clear wiring photographs when appropriate. Check existing documentation and repository issues before reporting a problem.

## 9. Customization and distribution

STEP files let you modify the enclosure for your own use or derivative builds. Changes may affect fit, compatibility, structural integrity and safety; no compatibility guarantee is implied. Please credit **EduSicilia | EDX_LAB** when referencing the original design.

**Licensing:** consult the terms shown on the Cults3D model listing and in each source repository/file. **Do not assume the enclosure model license is the same as the firmware license.** Bruce firmware and third-party materials retain their respective notices and licenses.

---

**GECKO Lite W | EDX_LAB**  
**OFFICIAL WEBSITE: https://edx-lab.github.io/**  
Thanks for building, exploring and improving hands-on learning projects.
