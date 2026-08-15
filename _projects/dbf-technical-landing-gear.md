---
layout: project
title: "Landing Gear Design"
subtitle: "Mechanical and Structural Subteam Co-Lead · 2024–2025"
date: 2026-05-07
image: assets/images/dbf/landing_gear.jpg
hide_hero: true
tags: [structures, mechanisms]
hidden: true
---

<a href="{{ site.baseurl }}/projects/dbf-technical/" class="back-arrow">← Back to Technical Projects</a>

During my year as Mechanical and Structural Subteam Co-Lead, I led the redesign of the landing gear for Yeagerflug, the team's 2024-25 competition aircraft, alongside the team's first composite fuselage. Together these changes reduced overall aircraft weight by 45%.

---

### Configuration Selection

Two landing gear configurations were compared: a four-wheel taildragger and a tricycle design. The taildragger, with two large main wheels and two small rear wheels, gave four points of ground contact and a wide lateral stance, making it more stable under the heavy loads the aircraft was carrying. Tricycle gear offered better ground clearance and easier steering through a powered nosewheel, but the taildragger's clearance was already sufficient for the aircraft's payloads and test vehicle, and the aircraft only needed to take off and land rather than taxi around a course. Rudder authority alone, with P-factor negated by counter-rotating propellers, was enough to steer the aircraft on the ground, so the added complexity and failure risk of a powered nosewheel wasn't worth it. Weighted against clearance, steering, stability, and reliability, the taildragger scored 4.6 versus the tricycle's 4.1 and was selected for its superior strength, stability, and reliability.

### Physical Design

Each main gear assembly is a curved carbon fiber strut set at a 13.75° angle to the chord line, terminating in a 3.54 in diameter rubber wheel on an axle. The top of each strut is a flat, drilled section that bolts through a 3D-printed integration piece directly into the tail spars using 1/4 in bolts. That integration piece does double duty: it raises ground clearance enough to clear the propellers, the X-1 test vehicle, and the external payloads, and it carries the shear and torsional loads the gear sees on landing.

### Testing

The strut was load tested to verify it could handle real landing loads without being pushed to failure in the lab, given the safety risk of carbon fiber fracturing under extreme load. Using a load cell, load was applied in 4 lb increments up to a maximum of 37.5 lb, producing about 4 in of vertical deflection, within the clearance margin designed into the gear. That result demonstrated a static load margin 1.3 times greater than the required factor of safety, and the gear passed.

### What the First Flight Test Taught Us

The gear's real test came during flight test preparations on December 12, 2024. The elevator failed to deflect correctly due to an insufficient number of hinges, which grounded the flight attempt, so the team ran a taxi test instead to gather what data it could. The aircraft taxied stably and was controllable on the rudders, confirming the taildragger didn't need active steering. But at the end of the taxi run, the landing gear's integration piece sheared off after hitting a bump, and the ESC short-circuited.

Digging into the failure, the root cause was material choice rather than geometry. The integration piece was printed in Onyx, which is strong but essentially rigid, so it had no way to absorb the shock of hitting a bump on an uneven runway. All of that impact energy went straight into the part as stress instead of being dissipated, and it sheared. I redesigned the piece to address that directly: I added sections specifically shaped to flex under load rather than resist it outright, and built in mounting locations for shock-absorbing foam to cushion impacts before they reached the rigid structure.

That taxi test surfaced landing gear integration as one of three manufacturing-quality issues from Iteration 1 that needed rework before the next flight attempt, alongside the elevator hinge count and the propeller-motor mounting. It's a good example of why the team tested early and iteratively, and of how a failure that looks like a strength problem can actually be a stiffness problem.
