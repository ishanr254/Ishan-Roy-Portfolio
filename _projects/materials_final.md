---
layout: project
title: "Torque Wrench Design & Finite Element Analysis - MAE 3270 Final Project"
subtitle: ""
date: 2025-12-05
image: assets/images/materials-final/cadRender.jpg
tags: [materials, fem, analysis]
---

### Summary
The goal of this project was to design a non-ratcheting torque wrench capable of meeting several design and performance specifications. I used a MATLAB script to perform analytical calculations and run through possible designs. I then created a CAD model in SOLIDWORKS and created a Finite Element Model (FEM) using Ansys Static Structural. I conducted analysis and then compared it to the results of the analytical calculations.

---

### 1) CAD Model
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/cad-dimensions.jpg" alt="CAD model with key dimensions" class="project-image" style="width:100%;">
</div>

---

### 2) Material & Relevant Mechanical Properties
- Material: **Ti-6Al-4V (Annealed)**
- E = **119 GPa** *(= 17.3 Msi)*
- ν = **0.31**
- σᵧ = **910 MPa** *(= 132 ksi)*,
- Fracture toughness **K₁C ≈ 107 MPa√m** *(= 97.3 ksi√in)*
- Fatigue/Endurance limit **≈ 517 MPa** *(= 75 ksi)*
- Source: **Ansys Granta**

Ti-6Al-4V (annealed) was selected for its high specific strength and corrosion resistance. With E = 119 GPa and ν = 0.31, it provides sufficient stiffness and produces measurable surface strain without approaching the allowable σy = 910 MPa under the applied loads. Some trade-offs, including the higher cost and lower modulus than steel, are acceptable given the goal of this project was to maximize the sensitivity of the design.

---

### 3) Finite Element Model Setup (Loads and Boundary Conditions)
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/fem-setup.png" alt="Loads and boundary conditions" class="project-image" style="width:100%;">
</div>
- Constraints: four faces of the block above the drive were constrained to have zero displacement
- Load: A load of 600 lbf * in was applied at the end of the wrench handle

---

### 4) Normal Strain Contours
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/strain-sgdir.png" alt="Normal strain contours in gauge direction" class="project-image" style="width:100%;">
</div>

---

### 5) Maximum Principal Stress Contour
<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/stress-maxP.png" alt="Maximum principal stress contour" class="project-image" style="width:100%;">
</div>

---


### 7) Max Normal Stress
- **Value:** **1.457 x 10^5 psi**

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/stress-max.png"
       alt="Max normal stress contour from FEM">
</div>

---

### 8) Deflection at Load Point
- **Value: 0.8275 in**

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/materials-final/deflection-loadpoint.png"
       alt="Deflection field and load-point displacement">
</div>

---


### 9) Strain at Gauge
- **Value:** **1599.3 µε** at the set gauge location

<div style="display:flex; gap:1rem; clear:both; width:100%; margin:1rem 0 2rem;">
  <!-- Main image (~2/3 width) -->
  <div style="flex:2 1 0; min-width:0;">
    <img src="{{ site.baseurl }}/assets/images/materials-final/strainGauge.png"
         alt="Strain at gauge location (field view)"
         style="display:block; width:100%; height:auto;">
  </div>

  <!-- Secondary image (~1/3 width, a bit larger) -->
  <div style="flex:1 1 0; min-width:260px;">
    <img src="{{ site.baseurl }}/assets/images/materials-final/strainGaugeZoom.png"
         alt="Strain gauge zoom / vertical detail"
         style="display:block; width:100%; height:auto;">
  </div>
</div>





---

### 10) Torque-Wrench Sensitivity
- Measured strain from the strain gauge in the model **ε = 1599.3 µε**
- Gauge factor: **K = 2**
- Bridge setup used:  **half**
- **Sensitivity: 1.5993 mV/V** - meets the required criteria


---

### 11) Strain Gauge Selection
- Gauge Type: **Bonded Foil Strain Gauge**
- Dimensions: **~ 7mm x 4mm**
- Bonding area on the part is larger than this, providing enough room
