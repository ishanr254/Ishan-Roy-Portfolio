---
layout: project
title: "Aircraft Design & Configuration Selection"
subtitle: "Duck Force One (DF1) · AIAA DBF 2025–2026"
date: 2026-05-03
image: assets/images/dbf/df1Cad.png
tags: [aerodynamics, systems]
hidden: true
---

<a href="{{ site.baseurl }}/projects/dbf-technical/" class="back-arrow">← Back to Technical Projects</a>

As Full Team Lead, I dictated the design direction of Duck Force One (DF1), our aircraft for the 2025-26 competition. While our sizing and scoring script produced the mission configuration and key geometric quantities, it was up to us to turn those numbers and ideas into a functional and well performing aircraft. 

DF1 implements a high-wing, single-motor configuration with a conventional empennage. The aircraft is capable of carrying passengers and cargo in its fuselage, with a banner mounted on the tail boom.

#### Key Specifications

|---|---|
| Wingspan | 46.51 in (3.88 ft) |
| Wing chord | 12.09 in |
| Aspect ratio | 3.85 |
| Empty weight | 5.05 lb |
| MTOW (M2, heaviest) | 7.23 lb |
| Wing loading | 29.6 oz/ft² |
| Propulsion | Scorpion SII-4025-520KV · 15×6 in prop (M1/M3) · 14×7 in prop (M3) |
| Battery | Tattu 4200 mAh 6S 35C LiPo (M1/M3) · Liperior 4000 mAh 6S 30C LiPo (M2) |
| Airfoil | FX 60-126 (wing) · NACA 0012 (empennage surfaces) |
| Structure | CFRP monocoque fuselage · basswood spars · MonoKote covering |
| Rated Aircraft Cost | 0.94 |

---

### Design Philosophy & Configuration Selection

The conceptual design phase required selecting an overall aircraft configuration before entering preliminary design. Five structural configurations were evaluated, flying wing, lifting body, biplane, twin-boom, and single-boom, and assessed against weighted FoMs including mission performance, integration quality, aerodynamics, stability, and manufacturability. The flying wing and lifting body offered reduced drag but provided limited internal volume, reduced inherent stability, and poor control authority. The biplane offered improved low-speed lift but incurred increased drag, mass, and integration complexity. The twin-boom improved rotational stability, which would have been beneficial for banner deployment in M3, but introduced additional weight, drag, and reduced control efficiency due to HT-VT flow separation. The single-boom configuration was selected for its favorable balance of manufacturability and mission compatibility, with greater design flexibility to control weight, drag, and stability.

Within that single-boom framework, the same reliability-first logic drove each subsequent configuration choice. Three wing placements were evaluated: the high-wing was selected over mid- and low-wing configurations because it offered superior roll stability, maximized fuselage internal volume for payload access, and simplified integration; a mid-wing would have required a spar through the fuselage, disrupting payload storage entirely. For the tail, the conventional configuration was chosen over the T-tail despite the T-tail's aerodynamic advantage of operating outside the main wing downwash. The T-tail requires a stronger, heavier vertical structure to resist bending and is significantly more difficult to manufacture. Given that integration quality was the primary FoM, the conventional tail's robustness outweighed the aerodynamic tradeoff. For landing gear, the tricycle configuration was selected over the taildragger primarily for GM performance; it provides maximum payload accessibility during loading, and prior Wichita competition data confirmed that a well-executed tricycle is sufficiently stable in that environment.

The resulting configuration, high-wing, single-boom, conventional tail, tricycle gear, and single tractor propulsion, represented the most predictable and manufacturable design the team could build given its recent history, while remaining fully competitive within the scoring framework.
