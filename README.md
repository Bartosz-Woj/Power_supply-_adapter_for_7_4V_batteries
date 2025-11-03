# Custom Power Supply Adapter for 7.4V batteries

## Project Description

The idea of this project is to create a **simple adapter** that allows using a **9 V (or higher)** DC power source instead of the original **7.4 V Li-ion battery** — specifically for the **Panasonic Lumix G7 camera**, using the **DMW-DCC8 DC coupler**.

This solution provides a regulated **8.6 V / 2 A** output suitable for continuous camera operation without relying on battery power.

This PCB can be used to replace a battery/accumulator in other similar applications.

---

## Technical Specifications

| Parameter          | Description                           |
| ------------------ | ------------------------------------- |
| **Input Voltage**  | 9 V – 20 V DC                         |
| **Output Voltage** | 8.6 V DC                              |
| **Output Current** | 2 A (max)                             |
| **Protection**     | Overcurrent fuse and ESD protection   |
| **Connector**      | Screw terminal connector (raster 5mm) |

---

## Battery Voltage Background

A typical **2S Li-ion battery pack** (used in cameras like the Lumix G7) has a **nominal voltage of 7.4 V**, but it varies depending on the charge level:

| Battery State    | Approx. Voltage |
| ---------------- | --------------- |
| Fully Discharged | 6.0 V           |
| Nominal          | 7.4 V           |
| Fully Charged    | 8.4 V           |

Initially, a resistor **R6** (8.66 kOhm) was selected to provide an output of **7.4V**, targeting a nominal 7.4 V equivalent output.

However, this voltage caused the camera to display the error:

> _"This battery cannot be used."_

and automatically power off after a few seconds.

After further research and forum discussions, it was discovered that the **Lumix G7** expects a slightly higher voltage (over 8.4) to correctly identify the source as an **external power supply** rather than a battery.

---

## Adjustment of output voltage

The output voltage is determined by a resistor divider network:

$$
V_{\text{out}} = V_{\text{ref}}\left(1 + \dfrac{R_5}{R_6}\right)
$$

For used step down converter (TPS54202):
$$ V\_{ref} = 0.596\,V $$

Example values:
| R5 | R6 | Output voltage |
| --- | ---- | -------------- |
| 100k | 8.66k | 7.4V |
| 100k | 7.5k | 8.6V |

---

## 📸 Photos

- **📷 Project Overview:**  
  ![Overview Photo](./photos/working_example.jpg)

- **🔌 Circuit Board / PCB:**  
  ![PCB Photo](./photos/front_side.jpg)

---

## Author

- **Project by:** Bartosz-Woj (Bartosz Wojciechowski)
- **Date:** 03.11.2025

---

## Disclaimer

> ⚠️ **Important Notice**

This project is a **custom-made modification** and **not approved by Panasonic** or any official manufacturer.  
Using this power adapter **may void your warranty** and **can potentially damage your device** if built or used incorrectly.

The author of this project **does not take responsibility** for any **damage, data loss, or warranty issues** resulting from the use of this adapter.
