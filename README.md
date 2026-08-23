# Gravity Main - Hydraulic Grade Line

An interactive teaching tool for water supply engineering. It shows how the hydraulic grade line (HGL) behaves along a 5,000 m gravity main from Cloud 9 Reservoir to Snow Town, and what that means for residual pressure at each offtake.

Live demo: https://josephllin.github.io/HGL-demo/

## What it shows

| Panel | Detail |
| --- | --- |
| Isometric view | Ground surface, pipeline and piezometers standing at each offtake. Drag to orbit, scroll to zoom. |
| Long section | Chainage 0 to 5,000 m, with the HGL drawn over the ground profile and the available pressure head shaded between them. The line kinks to a flatter slope past every offtake. |
| Hydraulics readout | Velocity, Reynolds number, friction factor, friction slope and velocity head for the upstream reach, plus total head loss for the whole main. |
| Reach table | Flow, velocity, friction slope and head loss for each of the three reaches between offtakes. |
| Residual pressure | Surface level, HGL and residual head at each offtake, checked against the minimum. |

## What you can change

| Control | Range |
| --- | --- |
| Draw-off at Falls Creek Village | 0 to 120 L/s |
| Draw-off at Mount Hotham | 0 to 120 L/s |
| Draw-off at Snow Town | 0 to 120 L/s |
| Pipe size | DN200, DN250, DN300, DN375, DN450 |
| Wall roughness k | 0.015 mm new PE / GRP, up to 1.50 mm old CI, tuberculated |

Each offtake draws its own flow, so the main carries the sum of everything still downstream of it: 100 L/s leaving the reservoir might be 70 L/s past Falls Creek Village and 45 L/s past Mount Hotham. Head loss is worked out reach by reach, which is why the grade line steepens where the pipe is fully loaded and flattens after each draw-off.

Sweep flow ramps all three demands together, from zero up to a 30 / 25 / 45 L/s pattern, and animates the grade line falling away from the static level. It is the quickest way to see friction eat into residual pressure.

## Design basis

| Parameter | Value |
| --- | --- |
| Scheme | Cloud 9 Reservoir to Snow Town |
| Main length | 5,000 m |
| Top water level | 120.00 m AHD |
| Method | Darcy-Weisbach with Colebrook-White |
| Minimum residual | 15 m |
| Water temperature | 15 C |

Offtakes: Falls Creek Village at ch 1600, surface 84.0 m. Mount Hotham at ch 3600, surface 80.0 m. Snow Town at ch 5000, surface 44.0 m.

## Running it

Single self-contained HTML file, no build step. Open index.html in any modern browser, or use the live link above. Three.js is loaded from a CDN for the isometric view.

Figures are illustrative and intended for teaching, not for the design of a real scheme.

## Credits

Idea by Joseph Lin, coded by Claude. 23 Aug 2026
