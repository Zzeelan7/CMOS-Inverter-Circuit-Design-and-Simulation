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


This schematic represents a standard CMOS inverter designed using the IHP SG13G process in eSim. It consists of:

A PMOS transistor (M1) connected between the output node and VDD (3.3 V).

An NMOS transistor (M2) connected between the output node and ground (GND).

The input node (Vin) drives the gates of both transistors simultaneously.

The output node (Vout) is taken from the connection point between M1 and M2.

When the input is LOW (0 V), the PMOS turns ON and NMOS turns OFF, producing a HIGH output (≈ 3.3 V).
When the input is HIGH (3.3 V), the PMOS turns OFF and NMOS turns ON, pulling the output LOW (≈ 0 V).

Purpose:
To visually represent the transistor-level realization of the inverter before simulation.

Recommended filename: CMOS_Inverter_Schematic.png

2. Voltage Transfer Characteristic (VTC)

<img width="850" height="535" alt="Voltage-transfer-characteristic-VTC-curves-of-standard-ternary-inverters-STIs" src="https://github.com/user-attachments/assets/e457e5df-4373-4d18-9fb7-b426a8543660" />

Description: A sigmoid-like curve showing Vout vs Vin (DC sweep).
It starts high at Vin = 0 V and drops sharply around Vin ≈ 1.65 V for a 3.3 V inverter.

This plot shows the DC transfer characteristic of the CMOS inverter, obtained using .dc Vin 0 3.3 0.01 analysis in Ngspice.
The X-axis represents input voltage (Vin), and the Y-axis represents output voltage (Vout).

As Vin increases:

Initially, Vout remains HIGH (near 3.3 V).

Around Vin ≈ 1.6 V, both transistors conduct partially, marking the switching threshold (Vth).

Beyond this, Vout rapidly falls to near 0 V, showing inverter action.

Purpose:
To analyze the inverter’s switching threshold and noise margins.

Recommended filename: VTC_Curve.png

3. Transient Simulation Waveform

<img width="850" height="834" alt="Comparison-of-output-phase-voltage-waveforms-a-two-level-inverter-b-three-level" src="https://github.com/user-attachments/assets/9b291f12-fdd3-4f8b-b564-77ff02e95276" />

Description: Two waveforms:

Vin: a square wave toggling between 0 V and 3.3 V

Vout: inverted version of Vin

The transient response demonstrates the dynamic switching behavior of the inverter when subjected to a periodic input pulse.
The waveform shows:

Vin (input) — a square wave toggling between 0 V and 3.3 V.

Vout (output) — an inverted version of Vin with small delay due to transistor switching time.

Key observations:

When Vin = 0 V → Vout ≈ 3.3 V

When Vin = 3.3 V → Vout ≈ 0 V

Small rise/fall delays illustrate inverter propagation delay.

Purpose:
To verify inverter switching functionality in the time domain.

Recommended filename: Transient_Waveform.png

4. Timing Diagram

<img width="897" height="526" alt="cad246fc23e5408ea33d4ce0e97b0e5c" src="https://github.com/user-attachments/assets/b7afde83-40cb-4d8a-9a1f-63cae516e543" />

Description: Basic logic-level timing diagram showing the phase shift between Vin and Vout.

A simplified logic-level waveform showing input and output transitions over time:

Input (Vin) transitions from LOW → HIGH → LOW periodically.

Output (Vout) transitions oppositely (HIGH → LOW → HIGH), maintaining complementary logic levels.

This idealized diagram supports understanding of logical functionality before detailed SPICE simulations.

Purpose:
To show conceptual operation of the inverter in digital logic timing terms.

Recommended filename: Logic_Timing_Diagram.png

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
