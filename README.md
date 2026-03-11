# 🛰️ GnieSat - Mechanical & Structural Design (ESA CanSat)

[![CAD](https://img.shields.io/badge/CAD-Fusion%20360-red.svg)](https://www.autodesk.com/products/fusion-360/)
[![Manufacturing](https://img.shields.io/badge/Manufacturing-FDM%203D%20Printing-blue.svg)]()
[![Material](https://img.shields.io/badge/Material-PA6%2BCF15-black.svg)]()
[![Simulation](https://img.shields.io/badge/Simulation-FEA%20%7C%20CFD-orange.svg)]()

This repository contains the complete mechanical design, structural analysis, and manufacturing data for the **GnieSat** probe, developed for the European Space Agency (ESA) CanSat competition. 

The physical model was designed from scratch to meet strict competition regulations: a cylindrical shape with external dimensions of **64 mm (diameter) × 113 mm (height)** and a maximum weight limit. 

---

## 🏗️ Mechanical Architecture

The mechanical design emphasizes compactness, modularity, and survival under extreme dynamic overloads. The total weight of all mechanical components is approximately **104g**.

* **Core Structure:** The internal stack is built on two vertical M3 threaded rods (42 mm spacing), securing all PCBs and ensuring structural integrity.
* **Component Stack:** Includes top cover (parachute/GNSS), Geiger-Müller tube with dedicated vibration damping, stacked PCBs, central battery module, magnetometer, and bottom cover with a camera.
* **Modular Housing:** Consists of 5 external parts (base, top, 2 side segments, sliding panel) allowing for rapid field maintenance and direct access to electronics without full disassembly.

*(Insert your CAD render here showing the internal layout - e.g., image8.png)*
`![Internal CAD View](link_to_your_image)`

---

## 🔬 Materials & Advanced Manufacturing

To withstand the rigorous flight conditions, standard PLA/PETG was insufficient. The housing was manufactured using **Nylon PA6+CF15** (polyamide reinforced with 15% carbon fiber) via FDM 3D printing.

* **Material Properties:** High stiffness, thermal stability, low moisture absorption, and excellent impact resistance.
* **Hardware Setup:** Printed using a 0.4 mm ruby nozzle (to withstand the abrasive carbon fiber) at 40 mm/s to optimize layer adhesion.
* **Variable Infill Strategy:** Standard structural components use 30% infill for weight reduction, while the bottom base (exposed to landing impacts) utilizes 50% infill for maximum compression resistance.
* **Post-processing:** All exterior surfaces were sanded and painted to smooth the aerodynamics and seal the carbon fiber skin.

*(Insert your exterior CAD render or physical photo here - e.g., image5.png)*
`![External CanSat View](link_to_your_image)`

---

## 📊 Structural & Aerodynamic Simulations

The design was validated using Autodesk Fusion 360 Simulation workspaces to ensure the payload survives the launch phase (20G) and the descent phase.

**1. Static Stress Analysis (FEA)**
* **Conditions:** 20G acceleration (~200 m/s²) with a fully loaded mass of ~325g.
* **Results:** The maximum structural stress remains well below the PA6+CF15 yield strength. The FR-4 PCBs experience a maximum stress of ~129.5 MPa (below the 300 MPa limit), effectively mitigated by rubber dampening washers on the M3 rods.

**2. Modal Analysis**
* **Results:** The first natural frequency of the structure is **897 Hz**, successfully placing it far above typical rocket vibration frequencies and eliminating the risk of resonance destruction.

**3. Computational Fluid Dynamics (CFD)**
* **Conditions:** Post-separation free-flight at 40 m/s, 10° angle of attack, at an altitude of ~2000 m (-4°C, 794 hPa).
* **Results:** The aerodynamic drag was calculated at **1.2 N**, with a minimal lift force of 0.15 N and a negligible aerodynamic moment (0.04 Nm). This confirms the cylindrical design maintains stable descent characteristics without inducing destructive spin.
