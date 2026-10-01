# Cealith Shaders 1.1.1

### 1.1.1 changes

* Fixes vanilla star detection in sky rendering to improve compatibility with different rendering configurations.
* Restores proper entity color overlay handling for effects such as damage tinting.
* Smooths the terrain shadow transition between daytime and nighttime to avoid abrupt shadow changes during twilight.
* Improves water depth sampling to reduce potential edge-related rendering artifacts.
* Adds safeguards against invalid vector normalization that could produce isolated visual artifacts.
* Makes render target usage explicit in programs that only write to the main color buffer.
* Preserves the original Cealith visual style, lighting balance, water appearance, clouds, fog, and performance profiles.

## Compatibility target

* Minecraft Java shader pipeline using Iris or OptiFine-compatible shader loading.
* GLSL 330 compatibility shaders.
* Designed around the standard `gbuffers_*`, `shadow`, `composite`, and `final` programs.

## Visual direction

* Bright, natural daylight with richer colors.
* More atmospheric dawn and sunset colors.
* Darker blue nighttime sky with readable stars.
* Naturally shaded clouds with soft highlights and cool undertones.
* Clear translucent water with animated waves, Fresnel highlights, depth tinting, soft sun reflections, and subtle caustic shimmer.
* Natural fog blending and gentle color grading.

## Performance profiles

**LOW**
512 shadow map, 48-block shadow distance, 1-tap shadows, reduced cloud edge work and reduced water ripple/shimmer work.

**BALANCED**
1024 shadow map, 80-block shadow distance, 2-tap shadows, full cloud shading and full water detail. This is the recommended starting point.

**HIGH**
1536 shadow map, 112-block shadow distance, 4-tap shadows, full visual detail.

## Installation

1. Install Iris or OptiFine for your Minecraft version.
2. Put `Cealith-Shaders-1.1.1.zip` inside your `.minecraft/shaderpacks` folder.
3. Select **Cealith Shaders** from the Shader Packs menu.
4. Start with **BALANCED**. If FPS is limited, switch to **LOW** before lowering Minecraft's render distance.

## License

MIT License. See the [LICENSE](https://github.com/santimakes/Cealith-Shaders?tab=License-1-ov-file).

### 1.1.1 bug-fix / stability pass

This build keeps the original Cealith look while addressing several rendering and compatibility issues identified in 1.1.0.

## 1.1.1 visual / compatibility notes

* No intentional visual redesign was made.
* Existing lighting, water, cloud, fog, color grading, and performance profile behavior are preserved.
* Sky star handling is more robust across compatible shader configurations.
* Entity overlays are handled correctly.
* Twilight shadow transitions are smoother.
* Water depth sampling is more stable around geometry edges.
* Additional safeguards reduce the chance of isolated rendering artifacts.
* Explicit render target declarations improve clarity and compatibility without changing the intended output.

## 1.1.0 visual/performance notes

* Final night tuning: darker global night exposure/gamma and a deeper night sky while preserving the daytime look, water, and performance changes.
