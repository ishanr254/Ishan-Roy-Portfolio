---
layout: project
title: "MATLAB Design Optimization Program"
subtitle: "Multidisciplinary Design Optimization · AIAA DBF 2025–2026"
date: 2026-05-04
image: assets/images/dbf/mdo_code_diagram.jpg
hide_hero: true
tags: [MATLAB, optimization, aerodynamics]
hidden: true
---

<a href="{{ site.baseurl }}/projects/dbf-technical/" class="back-arrow">← Back to Technical Projects</a>

The core design tool underlying DF1 is a MATLAB-based high-fidelity multidisciplinary design optimization (MDO) framework that simulates the competition mission profiles and finds an optimal aircraft geometry. The program was developed the summer before the 2025-26 competition cycle by myself and my co-lead with assistance from previous leads. The framework is implemented in MATLAB and organized into modular subsystems that exchange data and perform verification tasks. A 31-variable design vector, defining aircraft geometry and configuration, is passed through each analysis module and ultimately evaluated by a genetic algorithm to identify high-performing designs. The module structure and data flow are shown in the figure below.

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/dbf/mdo_code_diagram.jpg"
       alt="Block diagram of the MDO framework's modular structure and data flow"
       class="project-image" style="width:85%; display:block; margin:0 auto;">
  <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">MDO framework module structure and data flow</p>
</div>

The aerodynamic module models aerodynamic properties of the aircraft's wings, empennage, and fuselage, combining geometric parameters with propulsion performance and mass properties to compute lift, drag, and aerodynamic moments across the operating envelope, and verifies static and dynamic stability by enforcing stall margin, thrust, and control constraints. The mechanical module estimates mass given dimensions and configuration using empirical models, calculates the aircraft's CG via a weighted average of individual components, and computes the moment of inertia tensor using the parallel axis theorem.

The propulsion module calculates thrust and power given incoming airspeed and throttle, identifies the characteristic thrust-velocity relationship, and evaluates aircraft flight time and battery endurance. The scoring module simulates performance across all three flight missions, calculates TMS, and applies penalty functions to account for relative performance in negotiable categories, including dynamic flight behavior and usable flight envelope.

Over 150,000 candidate designs were evaluated during the optimization run. Two primary design trends toward a high TMS emerged: one favoring M2 with a low-capacity battery and greater payload, and one prioritizing GM and M3 with a larger battery and longer banner. The genetic algorithm optimization results are presented as a parallel coordinates plot in the figure below, where each line represents a candidate design and line color denotes TMS. The sizing program ultimately identified an optimal configuration with 3 passengers, 1 cargo, and a 150.00 in banner, with these mission parameters driving the preliminary aircraft design.

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/dbf/parallel-coords-2.png"
       alt="Parallel coordinates plot of design parameter scoring study showing 150,000 evaluated designs"
       class="project-image" style="width:90%; display:block; margin:0 auto;">
  <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Design parameter scoring study</p>
</div>

I developed and maintained the mechanical module, which estimates structural mass and computes the mass distribution properties used for CG calculation and moment of inertia verification. I additionally implemented the optimization module and adapted the scoring model to the 2025-26 rules upon their release, refining both as the team's performance data and build capabilities became available throughout the season.

**Key outcomes:**
- Over 150,000 designs evaluated across the optimization run
- MDO output directly determined final aircraft configuration submitted to competition
- Competition results and other teams' designs proved the MDO directed us to a successful design concept

---

### Verifying the Optimizer Example: Wingspan and Taper

With the overall configuration fixed, the MDO was used to optimize the five most sensitive design parameters identified by the scoring sensitivity analysis: wingspan, GM time, passenger count, banner length, and battery capacity. Wingspan required the most deliberate judgment because it directly drives two competing outcomes. At a fixed wing area and lift coefficient, induced drag is proportional to the inverse of wingspan; a longer span reduces drag and increases M3 lap performance. However, wingspan also linearly increases RAC, which enters the M3 scoring equation directly and penalizes the team relative to competitors. The MDO converged to an optimal wingspan of 46.51 in and wing area of 562.31 in², balancing these competing effects within the full scoring model.

To verify that additional geometric complexity was not warranted, the effect of wing taper on aerodynamic efficiency was investigated independently in XFLR5 for taper ratios from 0.5 to 1 at a fixed planform area. The maximum improvement in CL/CD was 1.96% in M3. This did not justify the added manufacturing complexity, and a rectangular planform was retained. The same reasoning was applied to the empennage, where no taper was implemented in either stabilizer.

This example shows the broader pattern behind the tool: the MDO explored the design space rigorously, but each output was verified with independent analysis before being accepted, and complexity was only added where the performance gain was clearly justified.

---

### Future Plans
During the summer of 2026, the team and I are further developing the program as we prepare for the 2026-27 competition cycle. A key change we are making is switching the program over to Python. This will allow us to explore a larger design space, as Python runs quicker, and utilize more advanced aero simulation modules that exist only for Python. 
