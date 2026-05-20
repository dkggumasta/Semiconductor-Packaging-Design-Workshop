# Semiconductor Packaging - Course Progress

This repository documents my hands-on work, lecture notes, and simulation labs completed during the VSD Semiconductor Packaging Workshop.

## Course Progress Tracker

| Module # | Topic(s) Covered | Status |
| :--- | :--- | :--- |
| **Mod. 1** | Packaging Evolution: From Basics to 3D Integration | 🟢 Completed |
| **Mod. 2** | From Wafer to Package: Assembly and Manufacturing Essentials | 🟡 In Progress |
| **Mod. 3** | Labs: Thermal Simulation of Semiconductor Packages with ANSYS | ⚪ Not Started |
| **Mod. 4** | Ensuring Package Reliability: Testing and Performance Validation | ⚪ Not Started |
| **Mod. 5** | Package Design and Modeling: Building a Package from Scratch | ⚪ Not Started |

---

## 1. Packaging Evolution: From Basics to 3D Integration
* **Core Concept:** Packaging protects the fragile silicon die, provides electrical connections to the PCB, and manages thermal dissipation.
* **Ecosystem:** The industry relies on Fabless designers (Apple, Nvidia), Foundries (TSMC), and OSAT units (ASE, Amkor) for manufacturing and assembly.
* **Advanced Packaging:** Shifting from single-chip architectures to Multi-Chip Modules (MCM), 2.5D (side-by-side on an interposer), and 3D stacking using Through-Silicon Vias (TSVs) to scale system performance.

---

## 2. From Wafer to Package: Assembly Essentials
* **Wafer Prep:** Involves backside grinding to reduce silicon thickness (~700um to ~200um) followed by high-precision dicing.
* **Interconnects:** Traditional packaging uses copper leadframes and gold wire bonding; high-performance layouts use flipped chips and micro-solder bumps (Flip-Chip Assembly).

---

## 3 - Labs: Thermal Simulation of Semiconductor Packages with ANSYS tools

## 3.1 - Introduction And Getting Started With ANSYS Electronics Desktop
ANSYS Electronics Desktop (AEDT) is a multi-physics simulation software that combines Electromagnetic, Signal Integrity, Thermal and Electro-Mechanical simulation tools in a single integrated platform. It is widely used for designing and analyzing high-speed electronic circuits and systems.

## 3.2 - Setting Up A Flip-Chip BGA Package
We will be taking an already available FC-BGA package within the Icepak Toolkit for this simulation exercise.

* **Step 1:** Open AEDT and launch Icepak
  * *Drop your screenshot of launching Icepak here*

* **Step 2.1:** Create a Flipchip BGA Package
  * Navigate to: `Icepak` -> `Toolkit` -> `Geometry` -> `Packages` -> `Flipchip_BGA`

* **Step 2.2:** The Package Configuration window opens up
  * The dimensions and other aspects of the package, substrate, die, die underfill and the solder balls can be configured here. Once configured, click OK to generate the package model.
  * *Drop your screenshot of the Package Configuration window here*
    <img width="1142" height="643" alt="Capture" src="https://github.com/user-attachments/assets/1dcd18c4-6ffd-4e12-a61f-7822e75960b6" />
<img width="1910" height="1002" alt="Package Generated" src="https://github.com/user-attachments/assets/7597c2d9-19e3-4d54-be39-2e83a4b81af7" />


* **Step 3:** Explore the 3D Package Model Structure in Icepak
  * *Drop your screen<img width="1156" height="701" alt="Capture2" src="https://github.com/user-attachments/assets/44f4e98d-176e-4f2d-9c48-c26658d6bb58" />
shot of the generated 3D package model (showing Ball Group, Substrate, Die Underfill, and Die) here*

## 3.3 - Material Definitions And Thermal Power Sources

* **Step 4:** Review and modify the material and definition types for the different components of the model.
  * *Drop your screenshot of the Material Definitions window here*

* **Step 5.1:** Add/ Assign Source Thermal Model for Die
  * In the "Project Manager" sub-window, expand the Thermal section, open the `BGA1_die_source` and configure the thermal conditions.
  * *Drop your screenshot of the Die Source Thermal Model setup here*

* **Step 5.2:** Add/ Assign Source Thermal Model for Substrate
  * Right-click on `Flipchip_BGA1_substrate` under `Models` -> `Flipchip_BGA1_Group` -> `Solids` and assign a Thermal Source. Set the thermal condition on the substrate to *Fixed Temperature* and the temperature as *Ambient*.

* **Step 6:** Add Thermal monitors for the different components
  * Right-click on the substrate solid, choose `Assign Monitor` -> `Point...`, and select *Temperature*. Repeat this to add thermal monitors for the die and the die-underfill.
  * *Drop your screenshot of the added Thermal Monitors here*

## 3.4 - Meshing And Running The Thermal Analysis

* **Step 7.1:** Generate Mesh
  * Go to the Simulation tab and click on **Generate Mesh**. Save the project if prompted and wait for the mesh generation to complete.

* **Step 7.2:** Review Mesh Quality metrics
  * Once the mesh is generated, review the quality metrics such as Face Alignment, Skewness, and Volume.
  * *Drop your screenshot of the Mesh Quality charts here*

* **Step 8:** Add Thermal Analysis
  * Under Project Manager, right-click on **Analysis**, select **Add Analysis Setup**, and configure the solver settings (choose default settings for this analysis).

## 3.5 - Viewing Results And Exploring Other Package Types

* **Step 9:** Validate the Simulation setup
  * Click on the **Validate** button in the top ribbon and ensure all checks are validated successfully.
  * *Drop your validation check screenshot here*

* **Step 10:** Run the simulation and plot the temperature map
  * Click on **Analyze All** in the top ribbon. Once completed, select the complete FC-BGA package in the 3D view, right-click, and select `Plot Fields` -> `Temperature` -> `Temperature`.
  * Enable *Gaussian Smoothing* under Surface Smoothing options.
  * *Drop your final Top View and Bottom View Temperature Field Plots here*<img width="1142" height="643" alt="Capture" src="https://github.com/user-attachments/assets/29a9abd5-8b19-4a21-87ca-e8542c1f4f97" />

*Replace this text later by dragging and dropping your simulation field plots / thermal maps here.*

---

## 4. Package Reliability and Testing
* **Wafer Sorting & Probing:** Isolates and marks known-good dies before assembly begins.
* **Package Testing:** Employs Burn-in screening (elevated temperature/voltage) to catch early-life failures and Final Testing to validate hardware data sheets.

---

## 5. Package Design and Modeling from Scratch
*Replace this text later by dragging and dropping your final JEDEC 4-point wire-bond 3D model screenshot here.*

---
## Conclusion
This workshop bridges the gap between pure chip design and real-world system integration, demonstrating how physical constraints dictate layout and thermal performance.


