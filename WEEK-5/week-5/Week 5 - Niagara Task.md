# Week 5 Task – Niagara VFX Systems
**Unit:** Technical Art (Level 5 Games Development)

## Brief
This week you will build a focused VFX showcase in Unreal Engine 5 using Niagara. You must produce six effects and demonstrate both technical control and gameplay integration:
- Fire
- Fireball projectile
- Lightning strike
- Slash attack VFX
- Decal impact spawned via an Animation Notify based on the Week 4 anim montage / notifiers content
- A flipbook (SubUV) variant of your Fire effect

Your work should show clear use of User parameters, Curves, and Blueprint/Animation integration. The approach you take and the specific renderers/materials you use are up to you; justify your choices in your documentation.

## Deliverables

You must create all six (6) of the following Niagara effects in a single UE5 project. Each effect must:
- Use at least two User parameters (prefix with `User.`) that can be set from Blueprint
- Use at least one Curve driven by Normalized Age to control size, alpha, color, etc.
- Be organized and named clearly (NS_ / NE_ conventions)
- At least one effect must be spawned via an Animation Notify (Decal Impact is required to use notifies)

---

### 1. Fire (stylized / realistic or both)
**Technical Requirements:**
- Believable looping fire effect with upward motion and turbulence
- Use at least one curve driven by Normalized Age (e.g., size, alpha, or color)
- Expose at least two user parameters (e.g., Color/Tint, Intensity/Brightness, Size Scale)
- Implementation approach is up to you; justify renderer/material choices in your documentation


---

### 2. Fireball Projectile
**Technical Requirements:**
- A projectile-style fireball with a readable core and trail
- Use at least one curve (e.g., width, alpha, brightness) to shape timing and readability
- Expose at least two user parameters (e.g., Core Color, Trail Width/Taper, Speed/Power)
- Implementation approach is up to you; justify your choices in documentation


---

### 3. Lightning Strike
**Technical Requirements:**
- Short-lived strike between a start and end point with a bright flash and quick decay
- Accept Start and End positions from Blueprint or world context
- Use at least one curve for quick on/off and color/alpha decay
- Expose at least two user parameters (e.g., Start, End, Color, Width)
- Implementation approach is up to you; justify choices in documentation

---

### 4. Slash Attack VFX
**Technical Requirements:**
- A stylized or realistic weapon slash effect that follows an attack motion
- Should be driven by an attack animation (via Anim Notify or Blueprint event) and/or attached to a weapon socket
- Use at least one curve (e.g., width, opacity, or color) to shape timing/readability
- Expose at least two user parameters (e.g., Color, Width, Length, Duration)
- Implementation approach is up to you; justify choices in documentation

---

### 5. Decal Impact (triggered by Animation Notify)
**Technical Requirements:**
- Must be spawned by an Animation Notify in your Week 4 attack montage at the impact frame
- On notify, determine the impact point and surface normal (e.g., via a trace) and align the effect accordingly
- Expose at least two user parameters (e.g., scale, SurfaceNormal)

---

### 6. SubUV Flipbook Implementation (Fire)
A flipbook-driven variant of your Fire effect.

**Technical Requirements:**
- Use a flipbook (texture sheet)
- Provide a side-by-side comparison in the demo level (flipbook vs non-flipbook)

---
## Assessment Criteria

Your work will be evaluated against the following criteria:

### Exploring
**Engaging in critical and creative inquiry through questioning, research, and material/process‑based investigations**
- Research real‑time VFX references (fire, lightning, slashes, projectiles, decals) and analyze readability, timing, and style
- Investigate renderer trade‑offs (Sprite/Mesh/Ribbon/Decal/Light) and simulation targets (CPU vs GPU) relevant to each effect
- Experiment with Curves driven by Normalized Age, User parameters, forces/noise, and SubUV flipbooks to discover best practice
- Document tests, failures, and insights; justify your final choices with technical reasoning

### Making
**Developing and refining creative work through iteration, risk‑taking, and material engagement**
- Technical proficiency in Niagara (system/emitter setup, module stacks, parameter exposure)
- Correct SubUV/flipbook playback and a clear comparison with a simulated variant (where applicable)
- Robust Blueprint/Animation integration (Anim Notify‑driven Decal Impact aligned to hit normal; parameterized spawns)
- Clean, performant materials (Depth Fade/soft particles where appropriate; additive/translucent choices justified)
- Polished iteration and problem‑solving: loop quality, trail tapering, color exposure, artifact reduction

### Connecting
**Communicating, collaborating, and engaging with audiences, industries, and networks**
- Clear documentation of technical decisions, parameter lists (User.*), and how designers/animators should use each effect
- Communication of renderer/material choices and why they support gameplay readability
- Industry‑aligned practice: naming conventions (NS_/NE_), organized folders and assets
- Demonstration video / Gifs that shows parameter control in‑editor or via Blueprint and Anim Notify triggering for the Decal Impact

### Situating
**Critically positioning work within social, cultural, environmental, ethical, and professional contexts**

- Maintains a concise reflective log
- Citation of influential sources used and notes on how they informed the works approach
- evidence to support reflections (screenshots, videos, GIFs)
- Acknowledgement of constraints and trade‑offs accepted, consideration of what could be improved / worked on with more time
- Shows knowledge of industry practice and understaning of how Niagara would be used in production (naming/organization, reusability via User parameters)

### Synthesizing
**Bringing together disparate elements into meaningful, cohesive outcomes**
- Integrated gameplay flow (e.g., Fireball projectile leading to Decal Impact? ; Slash synced to animation timing etc.)
- Evidence that research and testing informed the final systems and materials
- A tidy demo level showcasing the set working together and demonstrating key controls and integrations

---

## Optional Implementation considerations

These are optional ideas that build directly on your deliverables. Consider the following when building your effects.

- General Niagara & Workflow
  - Use Niagara Parameter Collections to drive global values across multiple effects (e.g., a global “Magic Power” or “Wind” influence)
  - Choose CPU vs GPU simulation intentionally. GPU handles huge counts; CPU supports events/collision. Set fixed bounds, enable Significance, and tune Scalability.
  - Blueprint patterns: Niagara Component vs Spawn System at Location; attach to sockets; pass User parameters at spawn and during tick; use Animation Notifies/Notify States for timing windows.

- Fire
  - Soft particles via material Depth Fade to avoid hard intersections with geometry
  - Turbulence with Curl Noise, Vector Fields, or wind‑like directional forces (Global wind from Niagara Parameter Collection?) ; layer low‑frequency and high‑frequency motion


- Fireball Projectile
  - Secondary impact FX: shockwave ring, ground scorch (decal), embers; brief Light Renderer flash on impact
  - Trail dynamics from parameters (width, taper, noise); camera‑facing vs velocity‑aligned choices
  - Surface‑type‑based variations (e.g., metal sparks vs dirt dust) by switching materials or user‑param sets

- Lightning Strike
  - Beam path jitter with noise; multi‑strike flicker by rapid re‑spawns
  - Width/opacity along path using curves; brief Light Renderer flash; impulse‑like audio sync
  - Drive Start/End from sockets, traces, or spline points

- Slash Attack VFX
  - Attach to weapon socket; sample motion to shape the trail; control width taper and color gradient by Normalized Age
  - Material stylization: additive glow plus edge outlines, UV stretch/flow for speed lines
  - Experiment with trail alignment modes and mesh vs ribbon approaches; ensure readability from main gameplay camera


## Resources

### Core Niagara
- Overview: https://dev.epicgames.com/documentation/en-us/unreal-engine/overview-of-niagara-effects-for-unreal-engine
- Creating Visual Effects in Niagara: https://dev.epicgames.com/documentation/en-us/unreal-engine/creating-visual-effects-in-niagara-for-unreal-engine

### Blueprints & Parameters
- Niagara Blueprint API (Set Niagara Variable nodes): https://dev.epicgames.com/documentation/en-us/unreal-engine/BlueprintAPI/Niagara
- Niagara Parameter Collections (API): https://dev.epicgames.com/documentation/en-us/unreal-engine/API/Plugins/Niagara/UNiagaraParameterCollection


### Renderers & How‑tos
- Renderers reference (Sprite, Mesh, Ribbon, Decal, Light): https://dev.epicgames.com/documentation/en-us/unreal-engine/render-module-reference-for-niagara-effects-in-unreal-engine
- How to create a Ribbon effect: https://dev.epicgames.com/documentation/en-us/unreal-engine/how-to-create-a-ribbon-effect-in-niagara-for-unreal-engine
- How to create a Beam effect: https://dev.epicgames.com/documentation/en-us/unreal-engine/how-to-create-a-beam-effect-in-niagara-for-unreal-engine

### Flipbooks / SubUV
- Niagara Flipbook Baker (Quick Start): https://dev.epicgames.com/documentation/en-us/unreal-engine/niagara-flipbook-baker-quick-start-guide-in-unreal-engine
- Sprite particles (useful basics for SubUV workflows): https://dev.epicgames.com/documentation/en-us/unreal-engine/how-to-create-a-smoke-effect-using-sprite-particles-in-niagara-for-unreal-engine

### Performance & Debugging
- Scalability and best practices for Niagara: https://dev.epicgames.com/documentation/en-us/unreal-engine/scalability-and-best-practices-for-niagara
- Niagara Debugger: https://dev.epicgames.com/documentation/en-us/unreal-engine/niagara-debugger-for-unreal-engine

### Decals
- Decals overview: https://dev.epicgames.com/documentation/en-us/unreal-engine/decals-in-unreal-engine
- Decal materials: https://dev.epicgames.com/documentation/en-us/unreal-engine/decal-materials-in-unreal-engine
- Decal Renderer in Niagara (tutorial): https://dev.epicgames.com/community/learning/tutorials/z0OW/unreal-engine-decal-renderer-in-niagara

### Events & CPU vs GPU
- Events and Event Handlers (CPU‑only limitation): https://dev.epicgames.com/documentation/en-us/unreal-engine/events-and-event-handlers-in-niagara-effects-for-unreal-engine
- GPU Sprite effect (sim target on GPU): https://dev.epicgames.com/documentation/en-us/unreal-engine/how-to-create-a-gpu-sprite-effect-in-niagara-for-unreal-engine

### Animation Notifies
- Animation Notifies (for spawning VFX from animations): https://dev.epicgames.com/documentation/en-us/unreal-engine/animation-notifies-in-unreal-engine


