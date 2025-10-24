# CMOS Inverter Circuit Design and Simulation

**Author:** Muhammed Zeelan M
**Platform:** eSim (KiCad + Ngspice)
**PDK:** IHP SG13G
**Supply Voltage:** 3.3 V

---

## 📘 Objective

To design and simulate a CMOS inverter circuit using eSim with the SG13G technology node, analyze its voltage transfer characteristics (VTC), transient behavior, and validate performance through SPICE-based simulations.

---

## ⚙️ Project Description

The CMOS inverter is a fundamental digital logic gate composed of one PMOS and one NMOS transistor. In this project:

* The circuit operates at **3.3 V**.
* The **PMOS** is connected to VDD and **NMOS** to GND.
* The **input (Vin)** is a square-wave pulse source.
* The **output (Vout)** shows complementary switching behavior.

Simulations are carried out using **eSim** (an open-source EDA tool integrating KiCad and Ngspice) to:

* Observe the **VTC curve** (using `.dc` sweep)
* Observe **transient response** (using `.tran` analysis)
* Demonstrate **correct inverter switching characteristics**

---

## 🧩 Files Included

| File                                 | Description                              |
| ------------------------------------ | ---------------------------------------- |
| `CMOS_Inverter.kicad_sch`            | KiCad schematic                          |
| `CMOS_Inverter.kicad_pro`            | KiCad project file                       |
| `CMOS_Inverter.cir`                  | Base NGSpice netlist                     |
| `CMOS_Inverter_DC_Sweep.cir`         | Netlist for DC analysis                  |
| `eSimReport.pdf`                     | Final report with results and discussion |
| `LICENSE`                            | GNU GPLv3 license file                   |
| `README.md`                          | This documentation file                  |

---

## 🧪 How to Simulate

1. **Open in eSim**

   * Import the `.kicad_sch` and `.cir` files into eSim.
   * Map components to the NGSpice library if needed.

2. **Run SPICE Simulations**

   * **Transient Analysis**:

     ```bash
     ngspice CMOS_Inverter_with_PDK_include.cir
     ```

     *(Replace `sg13g_models.sp` with your PDK model path.)*

   * **DC Sweep**:

     ```bash
     ngspice CMOS_Inverter_DC_Sweep.cir
     ```

3. **View Results**

   * Use eSim’s waveform viewer or export `.raw` data.
   * Compare your output with `transient_waveform.png`.

Notes:
- The .kicad_sch is a best-effort file and may require symbol mapping to your local KiCad libraries.
- If you want a fully working KiCad project with correct library references, upload your KiCad library files or tell me which library names to use and I will adjust the schematic accordingly.

---

## 📊 Expected Results

1. Voltage Transfer Curve
   
<img width="500" height="287" alt="500px-Inverter_voltage_transfer_curve" src="https://github.com/user-attachments/assets/1acb152d-df47-4d0e-98f8-31f6906234a2" />

Description: Shows one PMOS and one NMOS transistor connected in series between VDD and GND, with a single input (Vin) and output (Vout).
Search keywords:
CMOS inverter schematic diagram labeled,
PMOS NMOS inverter circuit,
eSim CMOS inverter schematic.

2. Voltage Transfer Characteristic (VTC)

<img width="850" height="535" alt="Voltage-transfer-characteristic-VTC-curves-of-standard-ternary-inverters-STIs" src="https://github.com/user-attachments/assets/e457e5df-4373-4d18-9fb7-b426a8543660" />

Description: A sigmoid-like curve showing Vout vs Vin (DC sweep).
It starts high at Vin = 0 V and drops sharply around Vin ≈ 1.65 V for a 3.3 V inverter.
Search keywords:
CMOS inverter voltage transfer characteristics,
CMOS inverter VTC plot 3.3V,
inverter Vout vs Vin graph.

3. Transient Simulation Waveform

<img width="850" height="834" alt="Comparison-of-output-phase-voltage-waveforms-a-two-level-inverter-b-three-level" src="https://github.com/user-attachments/assets/9b291f12-fdd3-4f8b-b564-77ff02e95276" />

Description: Two waveforms:

Vin: a square wave toggling between 0 V and 3.3 V

Vout: inverted version of Vin
Search keywords:
CMOS inverter transient simulation waveform,
inverter ngspice transient plot,
Vin Vout CMOS inverter.

4. Timing Diagram

<img width="897" height="526" alt="cad246fc23e5408ea33d4ce0e97b0e5c" src="https://github.com/user-attachments/assets/b7afde83-40cb-4d8a-9a1f-63cae516e543" />

Description: Basic logic-level timing diagram showing the phase shift between Vin and Vout.
Search keywords:
inverter logic timing diagram,
CMOS inverter logic waveform.

* **VTC Curve:** Sigmoid-shaped curve with switching threshold near VDD/2.
* **Transient Output:** Complementary square wave (Vout ≈ inverted Vin).
* **Noise Margins:** Derived from the VTC characteristics.

---

## 📦 Repository Structure

```
/
├── eSimProject.zip
├── eSimReport.pdf
├── README.md
├── LICENSE
└── results/
    ├── transient_waveform.png
    ├── transient_Vin_Vout.csv
    ├── CMOS_Inverter_DC_Sweep.cir
    └── CMOS_Inverter_with_PDK_include.cir
```

---

## 🌐 GitHub Repository

> Placeholder link: https://github.com/Zzeelan7/CMOS-Inverter-Circuit-Design-and-Simulation

---

## 🏁 Conclusion

The designed CMOS inverter demonstrates correct digital switching behavior, validating the theoretical operation of CMOS logic using eSim and the SG13G process. The project serves as a foundational reference for more complex digital circuit implementations in open-source EDA environments.
