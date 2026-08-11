---
layout: project
title: "Structural & CFD Analysis"
subtitle: "Detailed Design Verification · AIAA DBF 2025–2026"
date: 2026-05-08
image: assets/images/dbf/wingStress.png
hide_hero: true
tags: [FEA, CFD, structures, aerodynamics]
hidden: true
---

<a href="{{ site.baseurl }}/projects/dbf-technical/" class="back-arrow">← Back to Technical Projects</a>

I verified DF1's subsystem-level detailed design with a series of FEA and CFD studies in ANSYS, beyond the fuselage and banner-placement analyses covered on their own pages. I ran each of these myself, and results were reviewed by the team before being included in the final design report. Each study fed directly into a go/no-go decision on the corresponding subsystem.

---

### Wing Assembly FEA

To validate the structural integrity of the wing, I conducted FEA in ANSYS Static Structural on the full wing assembly. I applied a force of 32 lbf, representing the aircraft's 3.5 structural limit load factor, to the underside of the wing ribs, with a fixed displacement support applied at the base of the wing-fuselage integration piece.

| | Basswood | CFRP |
|---|---|---|
| Max deflection (in) | 0.14 | 0.08 |
| Max stress (psi) | 426.78 | 1269.60 |
| FoS | 20 | 236 |

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/dbf/wingStress.png"
       alt="ANSYS Static Structural equivalent stress contour on the wing assembly"
       class="project-image" style="width:70%; display:block; margin:0 auto;">
  <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Wing assembly stress distribution, CFRP configuration</p>
</div>

### Empennage FEA

I validated the horizontal and vertical stabilizers in ANSYS Static Structural using an 8 lbf upward load applied to the underside of the horizontal stabilizer, representing a worst-case aggressive maneuvering condition.

| | Basswood | CFRP |
|---|---|---|
| Max deflection (in) | 0.55 | 0.30 |
| Max stress (psi) | 2,800 | 13,510 |
| FoS | 3 | 22 |

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/dbf/tail-stress.png"
       alt="ANSYS Static Structural equivalent stress contour on the empennage assembly"
       class="project-image" style="width:70%; display:block; margin:0 auto;">
  <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Empennage stress distribution, CFRP configuration</p>
</div>

### Landing Gear FEA

I sized the tricycle landing gear to withstand landing loads at DF1's 7.4 lb MTOW using the same 3.5 landing load factor, then ran FEA on both the main and nose gear assemblies to verify strength margins.

| FoM | Main Gear | Front Gear |
|---|---|---|
| Load (lbf) | 22.02 | 2.89 |
| Max Stress (psi) | 41,000 | 17,300 |
| FoS | 7.5 | 2.5 |

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/dbf/mainGear.png"
       alt="ANSYS Static Structural equivalent stress contour on the main landing gear"
       class="project-image" style="width:70%; display:block; margin:0 auto;">
  <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Main gear stress distribution</p>
</div>

### Landing Gear Fairing CFD Study

I evaluated adding fairings around the landing gear as a potential drag-reduction measure, comparing the baseline gear against a faired configuration in ANSYS Fluent. The results showed a minor drag reduction, main gear drag decreasing from 0.38 lbf to 0.37 lbf (2.6%), but a much larger increase in lift, from 0.08 lbf to 0.27 lbf (238%). The added fairing mass was equivalent to a 0.44 lbf increase in required lift, offsetting the aerodynamic gains, so I concluded fairings weren't worth incorporating into the competition aircraft.

<div style="display:flex; gap:1rem; clear:both; width:100%; margin:1rem 0 2rem; flex-wrap:wrap;">
  <div style="flex:1 1 0; min-width:260px;">
    <img src="{{ site.baseurl }}/assets/images/dbf/vectors-no-fairing.png" alt="CFD velocity vectors around the baseline landing gear wheel" style="display:block; width:100%; height:auto;">
    <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Baseline (no fairing)</p>
  </div>
  <div style="flex:1 1 0; min-width:260px;">
    <img src="{{ site.baseurl }}/assets/images/dbf/vectors-fairing.png" alt="CFD velocity vectors around the faired landing gear wheel" style="display:block; width:100%; height:auto;">
    <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">With fairing</p>
  </div>
</div>

### Nosecone Motor Cooling CFD

The motor is enclosed within a 3D-printed PLA nosecone mounted to the forward fuselage bulkhead, so I verified thermal performance to ensure adequate cooling. I ran a CFD analysis in ANSYS Fluent at M3 cruise conditions, the lowest-airflow case, which predicted an average internal velocity of 26.25 ft/s through the vented nosecone and motor housing. Using that velocity with the motor's exposed surface area, I calculated a predicted steady-state motor temperature of 80°F, well below the PLA glass transition temperature of 140°F.

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/dbf/nosecone-airflow-2.png"
       alt="CFD velocity streamlines showing airflow into the nosecone and motor housing"
       class="project-image" style="width:80%; display:block; margin:0 auto;">
  <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Nosecone motor cooling airflow, ANSYS Fluent</p>
</div>

I later confirmed the thermal prediction with wind tunnel testing: motor temperature reached a steady-state of roughly 90°F after about 300 seconds of full-discharge operation, about 10° above the CFD prediction but still well below the PLA glass transition temperature, for a FoS of 1.15.

---

### XFLR5 Verification

Alongside the FEA and CFD work above, I used XFLR5 to independently verify decisions coming out of the MDO. The wing taper sensitivity study, showing at most a 1.96% improvement in CL/CD across taper ratios from 0.5 to 1, is covered on the [MDO Program page]({{ site.baseurl }}/projects/dbf-technical-mdo/).
