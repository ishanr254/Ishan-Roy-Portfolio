---
layout: project
title: "Banner Deployment & Release Mechanism"
subtitle: "Mission 3 Systems · AIAA DBF 2025–2026"
date: 2026-05-06
image: assets/images/dbf/bannerFore.png
hide_hero: true
tags: [mechanisms, CFD]
hidden: true
---

<a href="{{ site.baseurl }}/projects/dbf-technical/" class="back-arrow">← Back to Technical Projects</a>

M3 requires the aircraft to deploy its banner remotely after the first upwind turn and release it remotely after crossing the finish line on the final lap. The mechanism I designed for this is a two-piece 3D-printed PLA assembly clamped to the tail boom, split into a deployment half and a release half, joined with heat-set fabric snaps so the entire unit can be attached and detached quickly during Ground Mission configuration swaps.

The deployment half wraps the stowed banner around a spacer using an elastic band, with a servo-actuated pin holding one end of the band in place. On the deploy signal, the pin retracts, releasing the band and letting the banner unfurl behind the aircraft.

<div style="display:flex; gap:1rem; clear:both; width:100%; margin:1rem 0 2rem; flex-wrap:wrap;">
  <div style="flex:1 1 0; min-width:260px;">
    <img src="{{ site.baseurl }}/assets/images/dbf/bannerFore.png" alt="CAD assembly of the forward deployment half" style="display:block; width:100%; height:auto;">
    <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Deployment half</p>
  </div>
  <div style="flex:1 1 0; min-width:260px;">
    <img src="{{ site.baseurl }}/assets/images/dbf/bannerAft.png" alt="CAD assembly of the aft release half" style="display:block; width:100%; height:auto;">
    <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Release half</p>
  </div>
</div>

The release half uses a similar 3D-printed clamp, but instead houses the spooled tow rope along with the avionics controlling both servos. The tow rope is held by a second servo-actuated pin rather than an elastic band; retracting this pin on command frees the banner entirely after the final lap.

Banner placement along the tail boom was verified in ANSYS Fluent using a steady k–ω SST CFD model, confirming the banner sits in comparatively uniform flow behind the empennage, clear of the propeller and fuselage wake.

<div class="image-block-full">
  <img src="{{ site.baseurl }}/assets/images/dbf/velocityMid.png"
       alt="CFD velocity contour at the aircraft midplane showing flow around the tail boom"
       class="project-image" style="width:85%; display:block; margin:0 auto;">
  <p style="text-align:center; font-size:0.85em; color:#666; margin-top:0.4rem;">Midplane velocity contour, ANSYS Fluent steady k–ω SST</p>
</div>

Holding strength was validated with a banner release strength test: the stowed clamp was pulled at a 45° angle with a force gauge until the fabric snaps detached, confirming the mechanism could withstand expected towing loads without releasing prematurely.
