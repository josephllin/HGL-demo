# Gravity Main - Hydraulic Grade Line

An interactive teaching tool for water supply engineering. It shows how the hydraulic grade line (HGL) behaves along a 5,000 m gravity main from Bald Hill Reservoir to town, and what that means for residual pressure at each offtake.

Live demo: https://josephllin.github.io/HGL-demo/

## What it shows

| Panel | Detail |
| --- | --- |
| Isometric view | Ground surface, pipeline and piezometers standing at each offtake. Drag to orbit, scroll to zoom. |
| Long section | Chainage 0 to 5,000 m, with the HGL drawn over the ground profile and the available pressure head shaded between them. |
| Hydraulics readout | Velocity, Reynolds number, friction factor, friction slope, total head loss and velocity head. |
| Residual pressure | Surface level, HGL and residual head at each offtake, checked against the minimum. |

## What you can change

| Control | Range |
| --- | --- |
| Flow in main | 0 to 200 L/s |
| Pipe size | DN200, DN250, DN300, DN375, DN450 |
| Wall roughness k | 0.015 mm new PE / GRP, up to 1.50 mm old CI, tuberculated |

Sweep flow ramps the flow from zero to full and animates the grade line falling away from the static level. It is the quickest way to see friction eat into residual pressure.

## Design basis

| Parameter | Value |
| --- | --- |
| Scheme | Bald Hill Reservoir to Town |
| Main length | 5,000 m |
| Top water level | 120.00 m AHD |
| Method | Darcy-Weisbach with Colebrook-White |
| Minimum residual | 20 m |
| Water temperature | 15 C |

Offtakes: Upper Vale at ch 1600, surface 84.0 m. Knoll Rise at ch 3600, surface 80.0 m. Town Reticulation at ch 5000, surface 44.0 m.

## Running it

Single self-contained HTML file, no build step. Open index.html in any modern browser, or use the live link above. Three.js is loaded from a CDN for the isometric view.

Figures are illustrative and intended for teaching, not for the design of a real scheme.

## Credits

Idea by Joseph Lin, coded by Claude. 23 Aug 2026
