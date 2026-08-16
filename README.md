# CMOS Circuit Design and SPICE Simulation using Sky130 PDK

**Author:** Mazin Akhtar Syed  
**Background:** B.Tech in Electrical Engineering (2nd Year), NIT Delhi  

## Overview
This repository contains the simulation files, netlists, and characterization reports for the VSD CMOS Circuit Design and SPICE Simulation workshop. All simulations were performed using the open-source **Ngspice** simulator and the **SkyWater 130nm (Sky130) Process Design Kit (PDK)**.

The objective of this project is to analyze the static and dynamic behavior of CMOS devices, moving from fundamental $I_D\text{--}V_{DS}$ characteristics to full CMOS inverter robustness and transient analysis.

---

## Day 1: NMOS Fundamentals & Long-Channel Characterization

### Objective
To understand basic SPICE syntax and simulate the transfer and output characteristics of a long-channel NMOS device ($W = 5\,\mu\text{m}, L = 2\,\mu\text{m}$).

### Results
* **Output Characteristics:** The $I_D$ vs. $V_{DS}$ curves demonstrate classic pinch-off behavior. The spacing between curves increases quadratically as $V_{GS}$ increases.
* **Transfer Characteristics:** The $I_D$ vs. $V_{GS}$ curve was utilized to measure the threshold voltage ($V_{th}$) of the device.

**Long-Channel Output Characteristics:**
![Day 1 Output Characteristics] <img width="1920" height="1080" alt="day1_nmos_id_vds_long_channel" src="https://github.com/user-attachments/assets/dc5b0423-4e25-4378-89d1-f6f8bfc13446" />


**Transfer Characteristics:**
![Day 1 Transfer Characteristics] <img width="1920" height="1080" alt="day1_nmos_id_vgs_transfer" src="https://github.com/user-attachments/assets/0da74601-01fd-4b29-88ff-a8e542e8af82" />


---

## Day 2: Short-Channel Effects & Velocity Saturation

### Objective
To characterize a short-channel NMOS device ($W = 0.39\,\mu\text{m}, L = 0.15\,\mu\text{m}$) and observe the effects of velocity saturation, alongside PMOS output characterization.

### Results
* **Velocity Saturation:** Unlike the long-channel device, the short-channel NMOS enters saturation at a much lower $V_{DS}$. The spacing between the curves is linear rather than quadratic due to the carrier velocity reaching its maximum limit.
* **PMOS Characterization:** Successfully simulated the PMOS output curves, noting the negative current flow convention in SPICE.

**Short-Channel NMOS Output (Velocity Saturation):**
![Day 2 Velocity Saturation] <img width="1920" height="1080" alt="day2_nmos_id_vds_velocity_sat" src="https://github.com/user-attachments/assets/bc26ead1-711e-479b-949c-3ef59be2cae9" />

**PMOS Output Characteristics:**
![Day 2 PMOS Output] <img width="1920" height="1080" alt="day2_pmos_id_vds_output" src="https://github.com/user-attachments/assets/50f16e41-8c33-4ff4-83e2-4e79962add78" />


---

## Day 3: CMOS Inverter VTC & Switching Threshold

### Objective
To design a CMOS inverter, plot its Voltage Transfer Characteristic (VTC), and evaluate the switching threshold ($V_m$).

### Results
* By sweeping the input voltage ($V_{in}$), the VTC was generated.
* The PMOS and NMOS widths ($W_p / W_n$) were adjusted to properly center the switching threshold near $VDD/2$.
* Exact measurement confirmed $V_m$ where $V_{in} = V_{out}$.

**Inverter VTC Curve:**
![Day 3 VTC]<img width="1920" height="1080" alt="day3_inv_vtc_ratio1" src="https://github.com/user-attachments/assets/f4e253c4-5aa3-4254-8c77-9735dd2ec06b" />

**Measurement of Switching Threshold ($V_m$):**
![Day 3 Switching Threshold] <img width="1920" height="1080" alt="day3_inv_vtc_switching_threshold_Vm" src="https://github.com/user-attachments/assets/1d7dce9d-367e-40e5-a350-5da0f1a4e302" />


---

## Day 4: Inverter Robustness & Short-Circuit Current

### Objective
To analyze the short-circuit current during state transitions and evaluate the noise margins of the inverter.

### Results
* **Switching Current:** A bell-shaped current spike was observed during the brief window when both the PMOS and NMOS networks were simultaneously conducting.
* This analysis is critical for understanding the dynamic power dissipation of the CMOS logic gate.

**Short-Circuit Current Spike:**
![Day 4 Short Circuit Current] <img width="1920" height="1080" alt="day4_inv_short_circuit_current1" src="https://github.com/user-attachments/assets/724f72e0-0476-4c83-9dc0-afc9f4e0b026" />


---

## Day 5: Dynamic Performance & Process Variations

### Objective
To simulate the transient response of the inverter, measuring propagation delays, and to test the robustness of the circuit under supply voltage variations.

### Results
* **Transient Analysis:** Extracted rise time ($t_r$), fall time ($t_f$), and propagation delays ($t_{pLH}$, $t_{pHL}$) by running a transient simulation with a pulsed voltage source.
* **Supply Variation:** Plotted multiple VTC curves overlaid on top of each other while stepping down the supply voltage ($V_{DD}$) from 1.8V to 0.8V to observe the degradation of noise margins.

**Transient Response:**
![Day 5 Transient Analysis] <img width="1920" height="1080" alt="day5_inv_transient_response" src="https://github.com/user-attachments/assets/13dfd024-c6bd-4e13-b9f6-07df47048bd7" />


**VTC under Supply Voltage Variation:**
![Day 5 Supply Variation] <img width="1920" height="1080" alt="day5_inv_supply_voltage_variation" src="https://github.com/user-attachments/assets/ea7aa79a-3c99-45c3-affb-9ef906f94378" />

---

## Workshop Notes
Detailed derivations, manual calculations, and theoretical explanations recorded during the sessions are organized into the following daily folders within this repository:

* 📁 **Day 1 - Basics of NMOS drain current (Id) vs Drain - to - source  Voltage (Vds) notes**
* 📁 **Day 2 - Velocity Saturation and basics of CMOS Inverter VTC notes**
* 📁 **Day 3 - CMOS Switching Threshold and dynamic simulations notes**
* 📁 **Day 4 - CMOS Noise Margin robustness evaluation notes**
* 📁 **Day 5 - CMOS Power Supply and device robustness variation evaluation notes**

---
*This repository was created as a final project submission for the VLSI System Design (VSD) CMOS Circuit Design and SPICE Simulation Workshop.*
