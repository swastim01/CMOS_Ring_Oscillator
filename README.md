# Ring Oscillator Simulation

This repository contains the LTSpice simulation files for a **CMOS Ring Oscillator**, including circuit schematics, models, and simulation results.

## Project Structure

```
├── BSIM4_models.txt         # Transistor models for simulation
├── cmos_symbol.asc          # CMOS inverter schematic
├── cmos_symbol.asy          # CMOS inverter symbol file
├── Ring_Oscillator.asc      # Ring Oscillator schematic
├── Ring_Oscillator (netlist)# Netlist for the oscillator
├── Ring_Oscillator.op       # Operating point analysis results
├── Ring_Oscillator_Report.pdf # Documentation
├── images/
│   ├── simulation_result.png    # Simulation waveform
│   ├── ring_oscillator_circuit.png # Ring oscillator schematic
│   ├── cmos_inverter_circuit.png   # CMOS inverter schematic
└── README.md                # Project documentation
```

## Overview
The **CMOS Ring Oscillator** is a fundamental digital circuit composed of an odd number of CMOS inverters connected in a loop. It generates an oscillating signal without any external clock input.

### Working Principle
- The inverters introduce a propagation delay that causes the signal to oscillate.
- The frequency of oscillation is determined by the number of inverters and their delay.
- The output is a periodic waveform with a frequency dependent on the supply voltage, process parameters, and circuit design.

## Files Description

### **Schematics and Symbols**
- **cmos_symbol.asc** → CMOS inverter schematic.
- **cmos_symbol.asy** → Symbol for the CMOS inverter.
- **Ring_Oscillator.asc** → Complete ring oscillator schematic in LTSpice.
- **Ring_Oscillator (netlist)** → Netlist for circuit simulation.

### **Simulation Results**
- **Ring_Oscillator.op** → Operating point analysis results.
- **Ring_Oscillator (raw png)** → Simulation waveforms and results.

### **Models**
- **BSIM4_models.txt** → Defines the PMOS and NMOS transistor models for accurate SPICE simulation.

### **Documentation**
- **Ring_Oscillator_Report.pdf** → Detailed explanation of the circuit and results.

## Simulation Images

### **Ring Oscillator Schematic**
![Ring Oscillator Circuit](images/ring_oscillator_circuit.png)

### **CMOS Inverter Schematic**
![CMOS Inverter Circuit](images/cmos_inverter_circuit.png)

### **Simulation Output Waveform**
![Simulation Result](images/simulation_result.png)

## How to Run the Simulation
1. Open **LTSpice**.
2. Load the **Ring_Oscillator.asc** schematic.
3. Ensure that **BSIM4_models.txt** is included in the simulation.
4. Run the transient analysis to observe oscillations.
5. Analyze the waveform output to determine the oscillation frequency.

## Future Enhancements
- Implementing different CMOS process nodes to compare performance.
- Optimizing the delay by modifying the number of stages.
- Adding a buffer stage to improve output drive capability.

---