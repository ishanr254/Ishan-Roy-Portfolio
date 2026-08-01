---
layout: project
title: "Carbon Fiber Monocoque Fuselage & Layup Process"
subtitle: "Structures · AIAA DBF"
date: 2026-05-05
image: assets/images/dbf/fuselage_layup.jpg
tags: [structures, composites]
hidden: true
---

<a href="{{ site.baseurl }}/projects/dbf-technical/" class="back-arrow">← Back to Technical Projects</a>

Transitioning the team to a carbon fiber fuselage was a two year process that I started as Mechanical and Structural Subteam Lead. In prior years, the fuselage had been constructed out of a semi-monocoque wood and MonoKote structure. However, this method led to heavy designs that were prone to structural failures. In prior years, structural failures had been a significant contributor to unsuccessful competition outcomes along with the heavy aircraft being difficult to control.

---

### Layup Process

The layup process I implemented for the 2024-25 competition and then improved upon the following year follows a traditional wet layup process using sheets of carbon fiber twill weave fabric reinforced with an epoxy resin. The shape of the fuselage is created by 3D printed molds in which the layup is placed and then allowed to cure using a vacuum bagging process.

Initial layups, including the 2025 competition aircraft, utilized a fuselage layup that had been vacuum bagged surrounded by a peel ply release film along with the other necessary felt materials required to pull out and dry the epoxy in the fabric. After conducting further research and discussing with other teams, we switched to a wax mold remover instead of the release film. Additionally, I tested several methods of vacuum bagging during our research period in 2026, and was able to finally reach our goal vacuum pressure of 30 inHg by ensuring that the vacuum pump attachment went directly on the felt breather and that there was plenty of excess bagging material. This method, combined with the wax mold release, allowed final versions of the 2026 aircraft to have much smoother corners and weigh less because all of the excess epoxy was pulled out.

---

### Fuselage Construction

DF1 employs a CFRP monocoque consisting of two 3-ply shells fastened together with nylon hardware. Each shell uses alternating 45-degree ply orientations to improve torsional stiffness and load distribution. Three basswood bulkheads subdivide the fuselage into electrical, cargo, and passenger compartments, with basswood plates used at the wing and tail interfaces to distribute concentrated loads into the CFRP shell. The 2025 aircraft employed a fully monocoque structure with no bulkheads because the missions did not require anything beyond the propulsion system to be carried inside the fuselage. 

---

### Fuselage Analysis

 For the 2025-26 competition report, I learned how to perform a structural analysis on the composite fuselage. This analysis was not only used in the report but will also allow us to improve our designs in the future by cutting weight while being able to analytically show they will still perform well. 

 Structural performance was verified using ANSYS ACP, evaluating a governing combined loading case that included a distributed wing attachment load of 200 lbf representing a worst-case scenario, longitudinal electronics and tail-induced moments, and a landing load from the landing gear. All other loads were calculated based on a structural limit load factor of 3.5. The composite failure tool indicated a specific FoS of 5.6 against this worst-case loading scenario.

The decision to carry significant structural margin was deliberate. A FoS of 5.6 is conservative for this type of aircraft, but given that our primary goal for the 2026 competition was to field a reliable  aircraft, the added confidence in structural integrity was judged to be worth the modest weight penalty. However, I hope to use and pass on my new skills during the design of next year's aircraft to engineer a more mass efficient fuselage design.



