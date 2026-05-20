# Semiconductor Packaging - Course Progress

This repository documents my hands-on work, lecture notes, and simulation labs completed during the VSD Semiconductor Packaging Workshop.

## Course Progress Tracker

| Module # | Topic(s) Covered | Status |
| :--- | :--- | :--- |
| **Mod. 1** | Packaging Evolution: From Basics to 3D Integration               | Completed |
| **Mod. 2** | From Wafer to Package: Assembly and Manufacturing Essentials     | Completed |
| **Mod. 3** | Labs: Thermal Simulation of Semiconductor Packages with ANSYS    | Completed |
| **Mod. 4** | Ensuring Package Reliability: Testing and Performance Validation | Completed |
| **Mod. 5** | Package Design and Modeling: Building a Package from Scratch     | Completed |

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
 

* **Step 2.1:** Create a Flipchip BGA Package
  * Navigate to: `Icepak` -> `Toolkit` -> `Geometry` -> `Packages` -> `Flipchip_BGA`

* **Step 2.2:** The Package Configuration window opens up
  * The dimensions and other aspects of the package, substrate, die, die underfill and the solder balls can be configured here. Once configured, click OK to generate the package model.

   <img width="1142" height="643" alt="Capture" src="https://github.com/user-attachments/assets/1dcd18c4-6ffd-4e12-a61f-7822e75960b6" />
<img width="1910" height="1002" alt="Package Generated" src="https://github.com/user-attachments/assets/7597c2d9-19e3-4d54-be39-2e83a4b81af7" />


* **Step 3:** Explore the 3D Package Model Structure in Icepak
<img width="1156" height="701" alt="Capture2" src="https://github.com/user-attachments/assets/44f4e98d-176e-4f2d-9c48-c26658d6bb58" />


## 3.3 - Material Definitions And Thermal Power Sources

* **Step 4:** Review and modify the material and definition types for the different components of the model.
<img width="1912" height="1000" alt="design configure" src="https://github.com/user-attachments/assets/605d15ad-3744-4163-9127-ed7859f8ae62" />

* **Step 5.1:** Add/ Assign Source Thermal Model for Die
  * In the "Project Manager" sub-window, expand the Thermal section, open the `BGA1_die_source` and configure the thermal conditions.
<img width="1146" height="641" alt="ource thermal model die" src="https://github.com/user-attachments/assets/06325d94-201f-4174-a23d-943216122bd0" />


* **Step 5.2:** Add/ Assign Source Thermal Model for Substrate
  * Right-click on `Flipchip_BGA1_substrate` under `Models` -> `Flipchip_BGA1_Group` -> `Solids` and assign a Thermal Source. Set the thermal condition on the substrate to *Fixed Temperature* and the temperature as *Ambient*.
<img width="1164" height="353" alt="source for die" src="https://github.com/user-attachments/assets/92606db0-50d5-4838-98fe-8055401ede06" />

* **Step 6:** Add Thermal monitors for the different components
  * Right-click on the substrate solid, choose `Assign Monitor` -> `Point...`, and select *Temperature*. Repeat this to add thermal monitors for the die and the die-underfill.
<img width="1149" height="640" alt="thermal final" src="https://github.com/user-attachments/assets/9ed630da-65c9-4e17-8157-423511452f56" />


## 3.4 - Meshing And Running The Thermal Analysis

* **Step 7.1:** Generate Mesh
  * Go to the Simulation tab and click on **Generate Mesh**. Save the project if prompted and wait for the mesh generation to complete.
<img width="1157" height="640" alt="Mesh generation" src="https://github.com/user-attachments/assets/6cb9da7d-1c7e-48e1-a950-4da4b3cb5b17" />

* **Step 7.2:** Review Mesh Quality metrics
  * Once the mesh is generated, review the quality metrics such as Face Alignment, Skewness, and Volume.
<img width="1036" height="751" alt="mesh quality" src="https://github.com/user-attachments/assets/cb763b00-3cbe-4f15-bb87-4f8189c65730" />
<img width="538" height="751" alt="mesh qulity volume" src="https://github.com/user-attachments/assets/6dee88ef-ddda-4090-bbd2-7ef978bf9631" />




* **Step 8:** Add Thermal Analysis
  * Under Project Manager, right-click on **Analysis**, select **Add Analysis Setup**, and configure the solver settings (choose default settings for this analysis).
  <img width="658" height="714" alt="analysis" src="https://github.com/user-attachments/assets/f8884b41-95b1-4c25-b841-a57ca2345171" />


## 3.5 - Viewing Results And Exploring Other Package Types

* **Step 9:** Validate the Simulation setup
  * Click on the **Validate** button in the top ribbon and ensure all checks are validated successfully.
    

* **Step 10:** Run the simulation and plot the temperature map
  * Click on **Analyze All** in the top ribbon. Once completed, select the complete FC-BGA package in the 3D view, right-click, and select `Plot Fields` -> `Temperature` -> `Temperature`.
  * Enable *Gaussian Smoothing* under Surface Smoothing options.
  <img width="1148" height="706" alt="results" src="https://github.com/user-attachments/assets/1fd40e0a-4a3b-4a9d-94ec-6c8edc6d8f81" />


---

## 4 - Ensuring Package Reliability: Testing and Performance Validation

## 4.1 - Introduction to Package Testing and Electrical Functionality Checks
ICs are tested at multiple points during the manufacturing process to ensure they meet performance, reliability, and functionality requirements. Testing takes place both at the foundry and at OSAT facilities.


### 4.1.1 - Foundry Testing Stages
**1. Front-End Manufacturing**
* Involves fabrication of integrated circuits on silicon wafers.
* Leads to fine tuning of the Process parameters to improve yield, reduce IDDQ/ leakage and improve speed/ performance.

**2. Wafer Probe Test**
* Wafer is mounted on a probe station and a probe card with makes contact with the bond pads or bump pads of each die.
* An ATE can now send test patterns to mark the die as good or bad.

### 4.1.2 - OSAT Testing Stages
**1. Wafer Sorting**
* Dies are sorted based on probe test results.
* Only functional dies proceed to packaging.

**2. Package Manufacturing**
* Functional dies are packaged.

**3. Package Testing**
* Conducted in ISO Class 6/7 cleanroom zones.
* Testing includes:
  * **AOST (Assembly Open and Short Test):** Shorts/ Opens in Packages.
  * **Burn-in Test:** Elevated temperature and voltage and power cycling are applied to accelerate ageing to catch early failures.
  * **Final Test:** Validate the electrical performance of the packaged IC across temperature and voltage corners and ensure it meets the datasheet specifications.



**4. System Level Testing (SLT)**
* Testing is performed in conditions that closely mimic real-world system operation. SLT verifies how a chip behaves when it runs actual software or firmware inside a system-like environment.

---

## 4.2 - Reliability and Performance Testing of Semiconductor Packages

### 4.2.1 Burn-in and Final Test

**1. Burn-In Test**
* Burn-in testing is a reliability screening process where semiconductor devices are exposed to elevated temperatures, voltages, and operating conditions for an extended period to accelerate aging and failure mechanisms.
* It is used to identify and eliminate early-life failures (also called "infant mortality") in ICs before they are shipped to end users.


**2. Final Test (FT)**
* Final Test is the last major electrical test phase after the semiconductor die has been packaged.
* It verifies that the packaged device meets all functional, parametric, and performance specifications before it is shipped to customers.
* It is typically performed by OSATs (Outsourced Semiconductor Assembly and Test providers) or in-house test facilities.


**Summary: ATE & Test Categories**
<img width="1163" height="668" alt="ate" src="https://github.com/user-attachments/assets/df203a82-4fc1-4b97-8e17-28b73d0b98ca" />


---

## 5 - Package Design and Modeling: Building a Semiconductor Package from Scratch

This is a hands-on lab to design a semiconductor wire bond package from scratch using Ansys Electronics Desktop (AEDT).

## 5.1 - Introduction to Package Cross-Section Modeling in ANSYS Electronics Desktop (AEDT)

The main focus of this lab exercise is to build the complete cross-section of a wire bond package, including die, substrate, bonding wires, and mold compound, rather than performing any simulation or analyses.

*Package Specifications:*

| *Component* | *Properties* |
| :--- | :--- |
| **1. Die** | Material : Silicon<br>Dimensions : 3mm x 3mm<br>Die Height : 200 micron |
| **2. Substrate** | Material : FR4<br>Dimensions : 5mm x 5mm<br>Height : 500 micron |
| **3. Die Attach** | Material : Modified Epoxy<br>Dimensions : 3mm x 3mm<br>Thickness : 100 micron |
| **4. Die Bond Pads** | Material : Copper<br>Dimensions : 0.2mm x 0.2mm<br>Thickness : 5 micron |
| **5. Substrate Bond Pads** | Material : Copper<br>Dimensions : 0.2mm x 0.2mm<br>Thickness : 10 micron |
| **6. Bond Wire** | Material : Gold wire<br>Type: JEDEC 4-point |
| **7. Mold Compound** | Material : Epoxy<br>Thickness : 1.2mm |

* **Step 1 : Launch AEDT and select Q3D (or Icepak, Maxwell 3D)**
<img width="1054" height="557" alt="launch" src="https://github.com/user-attachments/assets/87fba776-0b18-47e2-ad3f-89c210f78342" />


## 5.2 - Creating the Die and Substrate in AEDT

* **Step 2 : Define the working unit**
  * Modeler -> Units...
  * Choose *mm* or *um* as the working unit for creating the model.
<img width="1215" height="387" alt="woking units" src="https://github.com/user-attachments/assets/b6351733-3eef-489b-a3e8-2f812360a330" />


* **Step 3.1 : Create the Die Geometry**
  * Select the rectangle tool from the ribbon or using the Menus ( Draw -> Rectangle ) to draw a rectangle
  * Now, double click on *CreateRectangle* Model -> Rectangle1 to open up its Properties Dialog box.
  * Specify the position with one corner at the origin (0, 0, 0) and the dimensions as 3mm x 3mm
  * Select Model -> Rectangle1 and from the menu bar: Modeler -> Surface -> Thicken Sheet... and set the thickness to 200 microns (0.2mm)

* **Step 3.2 : Assign Material Properties**
  * Open up the Properties Dialog box either by double clicking on Model -> Rectangle1
  * Rename the geometry to *Die*
  * Choose *Silicon* as the material from the Material Library.
 

* **Step 4.1 : Create the Substrate Geometry**
  * Draw another rectangle for the substrate (5mm x 5mm) and position (-1, -1, 0) it such that the die is at the center.
  * Set the thickness as -500 microns (-0.5mm). Note the negative sign so as to have the substrate lie beneath the die.
  * Adjust the substrate position along Z-axis to account for the die attach thickness. *Adjusted position: (-1, -1, -0.1)*
  

## 5.3 - Adding Die Attach Material and Bond Pads

* **Step 5 : Create the Die Attach Material**
  * Draw a rectangle of the same size as that of the die (3mm x 3mm) and at the same co-ordinates (0, 0, 0).
  * Set the thickness to -100 microns (-0.1mm) as the DAM lies beneath the die and the substrate
  * Assign the material to *Modified Epoxy*
  * *NOTE:* Assign different shades/ colours to adjacent components to easily discern in 3D view.
 

* **Step 6 : Create Bond pads on Die and Substrate**
  * Draw a small rectangle and configure its size to to that of the die pad (0.2mm x 0.2mm). We will place the first Die Pad at the co-ordinates (0.2, 0.2, 0.2) so that it sits on top of the die and is at one of the edges.
  * Set the thickness to 5 microns (0.005mm)
  *Drop your Die Bond Pad screenshot here*
  * Similarly, draw a small rectangle and configure its size to to that of the substrate bond pad (0.2mm x 0.2mm).
  * We will place this Substrate Bind Pad at the co-ordinates (0.2, -0.7, -0.1) so that it sits aligned to the Die bond pad created in the previous step, and also on top of the substrate.
  * Set the substrate bond pad thickness to 10 microns (0.010mm)
  *

## 5.4 - Wire Bond Creation and Material Assignment

* **Step 7 : Create Bond Wires**
  * Use the *Bondwire tool* under: Draw -> Bondwire
  * Connect the centre of the Die Bond pad to the centre of the Substrate Bond Pad. It might be easier to draw the wires from the Top view orientation.
  * Select the Bondwire type as JEDEC 4-point
  * Assign gold as the Bondwire material
  

  *Now, repeat the steps 6 and 7 to create and connect all the die and substrate bond pads using bondwires.*

## 5.5 - Applying Mold Compound and Finalizing the Package Model

* **Step 8 : Build the mold compound around the die**
  * Create a rectangular enclosure around the die and wires (5mm x 5mm, 1.2mm thickness)
  * Position at (-1, -1, -0.1) covering the top side of the substrate.
  * Set the thickness to 1.2mm so that it covers the die and the bondwires, while also leaving margin for any laser marking processes.
 <img width="1913" height="982" alt="final mold" src="https://github.com/user-attachments/assets/9086257b-2270-4878-b265-f0cdba2dd8ad" />

---



