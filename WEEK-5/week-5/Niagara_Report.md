# Week 5 - Niagara VFX Technical Report

## Overview
This report details the technical specifications and analysis of the Niagara VFX assets created for the Week 5 task. The analysis focuses on User Parameters, Curves, and Material dependencies for the key effects: `NS_FireNormal`, `NS_Fireball`, and `NS_FireFlipbook`.

## Asset Analysis

### 1. NS_FireNormal
**Description:** A standard fire effect using sprite particles.

![NS_FireNormal Screenshot](placeholder_NS_FireNormal.png)

*   **User Parameters:**
    *   `User.MinVelocity` (Float): Controls the minimum velocity of the fire particles.
    *   `User.MaxVelocity` (Float): Controls the maximum velocity of the fire particles.
    *   `User.Curve for Colors` (Curve): A color curve driving the particle color over its life.
    *   `User.SpawnRate` (Float): Controls the rate at which particles are spawned.

*   **Curves:**
    *   `Scale Alpha.FloatCurve`: Drives the alpha/opacity of the particles over their normalized age.
    *   `ScaleSpriteSize_Uniform_Curve_Sprite_Scale`: Drives the uniform scale of the sprites over their normalized age.

### 2. NS_Fireball
**Description:** A projectile-based fire effect, likely utilizing ribbon renderers for trails.

![NS_Fireball Screenshot](placeholder_NS_Fireball.png)

*   **User Parameters:**
    *   No explicit `User.` parameters were identified in the system definition.
    *   The effect relies on **Dynamic Parameters** passed to the material `M_Trail`.

*   **Curves:**
    *   `FloatFromCurve_FloatCurve`: Used internally to drive particle attributes.

*   **Dependencies:**
    *   **Material:** `M_Trail`
    *   **Blueprint:** `BP_Projectile` (contains the Niagara Component)

### 3. NS_FireFlipbook
**Description:** A volumetric-style fire effect using flipbook textures (SubUV).

![NS_FireFlipbook Screenshot](placeholder_NS_FireFlipbook.png)

*   **User Parameters:**
    *   No explicit `User.` parameters were identified in the system definition.
    *   The effect relies on **Dynamic Parameters** passed to the material `M_Smoke`.

*   **Curves:**
    *   `ColorFromCurve_ColorCurve`: Drives the color and intensity of the flipbook particles.

## Material Dependencies

### M_Trail
Used by `NS_Fireball` (likely for the trail ribbon).
*   **Dynamic Parameters:**
    *   `U(1)`
    *   `V(1)`
    *   `Speed(1)`
    *   `Density(1)`
*   **Scalar Parameters:**
    *   `Speed` (Default: -0.5)

### M_Smoke
Used by `NS_FireFlipbook` (and likely `NS_FireNormal` or variants).
*   **Dynamic Parameters:**
    *   `UVs`
    *   `Density`
*   **Texture:** `T_Smoke_Tiled_D`

## Recommendations
*   **Parameter Exposure:** For `NS_Fireball` and `NS_FireFlipbook`, consider exposing the material dynamic parameter drivers (like Density or Speed) as `User.` parameters in the Niagara System. This would allow for easier tuning directly from the Level Editor or Blueprint without diving into the Niagara stack.
*   **Consistency:** Ensure all effects follow the naming convention `NS_[EffectName]` and utilize `User.` parameters for key artistic controls (Color, Size, Speed) to maintain consistency with `NS_FireNormal`.
