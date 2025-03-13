# Ring Oscillator Simulation Report

## 1. Introduction
A **Ring Oscillator** is a simple electronic oscillator composed of an odd number of **inverters** connected in a loop. It generates a periodic oscillating signal without any external clock input. Ring oscillators are widely used in **VLSI circuits**, **clock generation**, and **delay measurements**.

## 2. Circuit Description
The ring oscillator consists of:
- **Odd-numbered inverters** to ensure oscillation.
- **CMOS technology** for low power consumption.
- **Feedback mechanism** to create a self-sustaining oscillation.

### 2.1 CMOS Inverter Design
The **CMOS inverter** is a fundamental component of the ring oscillator. It consists of:
- **PMOS transistor (BSIM4 model)** connected to VDD.
- **NMOS transistor (BSIM4 model)** connected to GND.
- **Input-Output relationship:**
  - When the input is **high**, the NMOS conducts, pulling output **low**.
  - When the input is **low**, the PMOS conducts, pulling output **high**.

## 3. LTSpice Implementation
### 3.1 Components Used
- **PMOS Model:** P_50n (BSIM4 Level 54)
- **NMOS Model:** N_50n (BSIM4 Level 54)
- **Power Supply:** VDD = 1.8V
- **Inverter Chain:** 5-stage CMOS inverters

### 3.2 Netlist Structure
```spice
* Ring Oscillator Netlist
VDD VDD 0 DC 1.8V
X1 in out VDD 0 CMOS_INVERTER
X2 out in2 VDD 0 CMOS_INVERTER
X3 in2 in3 VDD 0 CMOS_INVERTER
X4 in3 in4 VDD 0 CMOS_INVERTER
X5 in4 in VDD 0 CMOS_INVERTER
.tran 1n 100n
.end
```

## 4. Simulation Results
### 4.1 Expected Output
The oscillation frequency is determined by:
\[ f = \frac{1}{2N \times T_p} \]
Where:
- **N** = Number of inverter stages (odd number)
- **T_p** = Propagation delay per inverter

### 4.2 Observed Results
- **Oscillation waveform:** ✅ (Captured in `documentation/Oscillator_Waveform.png`)
- **Frequency measured:** ~100 MHz (varies with process parameters)
- **Propagation delay per inverter:** ~500ps

## 5. Conclusion
The LTSpice simulation of a CMOS **5-stage ring oscillator** successfully demonstrates **self-sustained oscillations**. The results align with theoretical expectations, validating CMOS inverter characteristics. Further optimizations can be explored to reduce power consumption and increase frequency.

