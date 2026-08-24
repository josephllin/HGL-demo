# Cloud 9 Water Supply - Hydraulic Grade Line

Two interactive teaching sheets for water supply engineering: a gravity main feeding three offtakes, and the same scheme on a single common main where a pump at the far end can reverse the flow.

| Sheet | Live |
| --- | --- |
| 01 - Gravity main, Cloud 9 Reservoir to Snow Town | https://josephllin.github.io/HGL-demo/ |
| 02 - Pumped main, one common pipe with reversing flow | https://josephllin.github.io/HGL-demo/pumped-main.html |

## Sheet 01 - Gravity main

It shows how the hydraulic grade line (HGL) behaves along a 5,000 m gravity main from Cloud 9 Reservoir to Snow Town, and what that means for residual pressure at each offtake.

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

## Sheet 02 - Pumped main

Sheet 02 puts the whole scheme on one pipe. The corridor continues past Snow Town to the Lake Wombat Treatment Plant at ch 6000, surface 20.0 m AHD, and a pump station there injects flow back into the same main that feeds the three offtakes. There is no second pipe.

Cloud 9 Reservoir is a fixed-head boundary at TWL 120.00; the pump is a fixed-flow boundary at ch 6000. With one reservoir and one pump on a branchless line, continuity alone fixes the flow in every reach: each reach carries the sum of everything still drawn downstream of it, less the pump flow. Head falls in whichever direction the water actually travels, so a reversed reach has a grade line that rises with chainage.

Raising pump flow reverses the main from the far end backwards. At 100 L/s of town demand on DN300 at k = 0.06 mm:

| Pump | Reach 1 | Reach 2 | Reach 3 | Reach 4 | Falls Creek | Mt Hotham | Snow Town |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 L/s | 100 out | 70 out | 45 out | dead | 27.4 m | 25.9 m | 60.2 m |
| 60 L/s | 40 out | 10 out | 15 back | 60 back | 34.4 m | 38.3 m | 74.5 m |
| 100 L/s | dead | 30 back | 55 back | 100 back | 36.0 m | 41.1 m | 79.6 m |
| 140 L/s | 40 back | 70 back | 95 back | 140 back | 37.6 m | 47.1 m | 89.9 m |

At 100 L/s the pump exactly covers demand, reach 1 goes dead, and Cloud 9 neither fills nor drains. Past that, surplus runs back into the reservoir and the grade line sits above TWL along the whole main. Every offtake gains pressure as the pump comes up, most of all the ones nearest it.

Reaches are coloured by direction in both the long section and the 3D grade surface: teal for flow running away from Cloud 9, violet for flow running back toward it, with matching arrows on the pipe.

| Readout | Meaning |
| --- | --- |
| Static lift | TWL minus the plant water level, fixed at 100.00 m |
| Pump head required | The grade line the pump must hold at ch 6000, above the plant water level |
| Friction in main | Total loss summed over all four reaches |
| Velocity at pump | Velocity in the reach leaving the plant |
| Shaft power | Hydraulic power at 75 % combined pump and motor efficiency |
| Specific energy | kWh per megalitre delivered |

A balance line under the reach table says in words what is happening: how much Cloud 9 is still supplying, how many reaches have reversed, or how much is running back into storage. With the pump off, Sheet 02 reproduces Sheet 01 exactly, which is the check that the two models agree.

## Design basis

| Parameter | Value |
| --- | --- |
| Scheme | Cloud 9 Reservoir to Snow Town |
| Gravity main length | 5,000 m |
| Corridor length | 6,000 m to Lake Wombat TP |
| Top water level | 120.00 m AHD |
| Method | Darcy-Weisbach with Colebrook-White |
| Minimum residual | 15 m |
| Water temperature | 15 C |
| Treatment plant level | 20.00 m AHD |
| Pump set efficiency | 75 % |

Offtakes: Falls Creek Village at ch 1600, surface 84.0 m. Mount Hotham at ch 3600, surface 80.0 m. Snow Town at ch 5000, surface 44.0 m.

## Running it

Two self-contained HTML files, no build step. Open index.html or pumped-main.html in any modern browser, or use the live links above. Three.js is loaded from a CDN for the isometric view.

Figures are illustrative and intended for teaching, not for the design of a real scheme.

## Credits

Idea by Joseph Lin, coded by Claude. 23 Aug 2026
