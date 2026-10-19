# LampShade Studio Pro

A browser-based parametric 3D lamp shade and cylindrical lithophane generator built with Three.js. Exports watertight binary `.stl` files oriented for 3D printing.

## Recommended 3D Slicer Settings (Orca-Flashforge / OrcaSlicer)

All profiles below assume a standard **0.4 mm nozzle**.

### 1. Lithophane Lamp Shades (Image Embossed)
Lithophanes require **100% solid plastic walls** so light transmission is governed strictly by wall thickness rather than internal infill grids.

| Parameter | Recommended Setting | Notes |
| :--- | :--- | :--- |
| **App Min Wall Thickness** | `0.8 mm` | 2 perimeters at 0.4 mm line width for brightest highlights |
| **App Max Emboss Depth** | `2.0 mm – 2.4 mm` | Yields `2.8 mm – 3.2 mm` total thickness in darkest shadows |
| **Wall Generator** | **Arachne** | Essential for smooth variable-width lithophane micro-details |
| **Layer Height** | `0.12 mm` or `0.16 mm` | Use `0.20 mm` for the first layer |
| **Wall Loops (Perimeters)** | `7 – 9 loops` | Ensures walls remain 100% solid perimeter loops |
| **Sparse Infill Density** | `100%` (Rectilinear) | Backup solid fill for the thickest embossed regions |
| **Outer Wall Speed** | `40 – 60 mm/s` | Prevents ghosting/ringing on high-frequency image textures |
| **Seam Position** | `Aligned` or `Back` | Keeps Z-seam along a single vertical line at the rear |
| **Brim** | `Outer Brim Only (5 mm)` | Recommended for tall shades (>150 mm) |
| **Supports** | `Disabled` | Bottom/top fitter spokes bridge cleanly without supports |
| **Filament** | Warm White / Natural PLA | Avoid heavily titanium-dioxide loaded bright white filaments |

---

### 2. Geometric, Ribbed & Twisted Shades (Non-Lithophane)

| Parameter | Recommended Setting | Notes |
| :--- | :--- | :--- |
| **App Wall Thickness** | `1.2 mm – 1.6 mm` | Clean diffusion with structural rigidity |
| **Layer Height** | `0.16 mm – 0.20 mm` | Standard quality |
| **Wall Loops (Perimeters)** | `3 – 4 loops` | Matches wall thickness without needing infill |
| **Sparse Infill Density** | `0%` | Prevents internal infill shadow lines |
| **Filament** | PLA, Matte PLA, Wood PLA, or PETG | Use PETG if pairing with warmer bulbs |

---

### 3. Spiral Vase Mode (Single-Wall Print)
1. In the app, set **Attachment Style** to `Solid Base (Tea Light / LED Puck)` and set **Rib Depth** or **Twist** as desired.
2. In Orca-Flashforge, check **Spiral Vase** under the *Others* tab.
3. Set **Outer Wall Line Width** to `0.60 mm – 0.80 mm` (even with a 0.4 mm nozzle) for extra rigidity.
4. Set **Bottom Shell Layers** to `5`.
5. If you need a socket mount hole in the solid base, right-click the model in the slicer → **Add Negative Part → Cylinder** and scale it to your socket diameter (e.g., `40 mm` for E27).

---

### Thermal Safety
* **LED Bulbs Only:** Standard PLA has a glass transition temperature near **60°C (140°F)**. Pair PLA shades strictly with low-wattage LED bulbs (≤ 10W LED).
* For higher-wattage fixtures or enclosed environments, print using **PETG** or **ASA**.