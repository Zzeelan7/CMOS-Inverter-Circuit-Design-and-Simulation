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
| `CMOS_Inverter_with_PDK_include.cir` | Netlist referencing SG13G PDK            |
| `transient_waveform.png`             | Behavioral transient waveform            |
| `transient_Vin_Vout.csv`             | Transient simulation data                |
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

---

## 📊 Expected Results

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

> Placeholder link: [https://github.com/yourusername/eSim_CMOS_Inverter](https://github.com/yourusername/eSim_CMOS_Inverter)

---

## 🧾 License

This project is distributed under the **GNU General Public License v3.0** (GPLv3).
You are free to use, modify, and distribute it under the same license conditions.
See the included `LICENSE` file for full legal text.

---

## 🏁 Conclusion

The designed CMOS inverter demonstrates correct digital switching behavior, validating the theoretical operation of CMOS logic using eSim and the SG13G process. The project serves as a foundational reference for more complex digital circuit implementations in open-source EDA environments.
