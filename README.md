# Cealith Shaders 1.1.0

### 1.1.0 changes

- Preserves the original Cealith water look instead of reducing Fresnel/specular response.
- Reworked water wave normals to calculate the same wave field analytically, avoiding repeated wave-function evaluations.
- Keeps animated water ripples and caustic shimmer enabled by default, with an optional low-cost switch.
- Restored the original terrain/entity/local-light tuning from 1.0.0.
- Shadow filtering is configurable: 1, 2, or 4 taps. BALANCED uses 2 taps; HIGH uses the original 4-tap quality.
- Shadow-pass geometry culling is enabled through `shadowDistanceRenderMul` to avoid rendering unnecessary distant casters.
- Cloud edge shading now uses screen-space derivatives instead of four additional texture lookups.
- Full-screen color grading keeps the Cealith palette while replacing the most expensive per-channel `pow()` operation with a close, cheaper approximation.
- Profiles are arranged so LOW favors FPS, BALANCED keeps the intended look, and HIGH restores the original shadow quality.
- The shader pack no longer relies on a shared include containing a second `#version` directive, avoiding an avoidable GLSL compatibility hazard.

## Compatibility target

- Minecraft Java shader pipeline using Iris or OptiFine-compatible shader loading.
- GLSL 330 compatibility shaders.
- Designed around the standard `gbuffers_*`, `shadow`, `composite`, and `final` programs.

## Visual direction

- Bright, natural daylight with richer colors.
- More atmospheric dawn and sunset colors.
- Darker blue nighttime sky with readable stars.
- Naturally shaded clouds with soft highlights and cool undertones.
- Clear translucent water with animated waves, Fresnel highlights, depth tinting, soft sun reflections, and subtle caustic shimmer.
- Natural fog blending and gentle color grading.

## Performance profiles

**LOW**  
512 shadow map, 48-block shadow distance, 1-tap shadows, reduced cloud edge work and reduced water ripple/shimmer work.

**BALANCED**  
1024 shadow map, 80-block shadow distance, 2-tap shadows, full cloud shading and full water detail. This is the recommended starting point.

**HIGH**  
1536 shadow map, 112-block shadow distance, 4-tap shadows, full visual detail.

## Installation

1. Install Iris or OptiFine for your Minecraft version.
2. Put `Cealith-Shaders-1.1.0.zip` inside your `.minecraft/shaderpacks` folder.
3. Select **Cealith Shaders** from the Shader Packs menu.
4. Start with **BALANCED**. If FPS is limited, switch to **LOW** before lowering Minecraft's render distance.

## License

MIT License. See `LICENSE`.


### Performance / night pass
This build keeps the original look while reducing redundant fragment work and slightly deepening nighttime exposure.

## 1.1.0 visual/performance notes
- Final night tuning: darker global night exposure/gamma and a deeper night sky while preserving the daytime look, water, and performance changes.
