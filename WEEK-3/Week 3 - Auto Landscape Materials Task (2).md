# Week 3 Task – Auto Landscape Materials
**Unit:** Technical Art (Level 5 Games Development)  

## Brief  
This week focuses on developing advanced landscape material systems that automatically blend textures based on environmental conditions and procedural generation techniques. You are required to create a **comprehensive auto landscape material system** that demonstrates sophisticated blending techniques, foliage integration, and procedural generation workflows used in modern open-world game development.

Your project should showcase technical mastery of landscape materials, understanding of procedural generation principles, and awareness of performance optimization strategies used in professional game development.

---

## Core Deliverable: Comprehensive Auto Landscape Material System

You must create a **single, sophisticated landscape material** that incorporates **all four** of the following auto-blending systems:

---

### 1. Height-Based Blending System  
**Technical Requirements:**  
- Implement **automatic texture blending** based on world height/elevation
- Create smooth transitions between at least **3 height zones** (e.g., valley floor, hillside, mountain peak)
- Use **LandscapeLayerBlend** nodes with height-driven alpha masks
- Include **transition falloff controls** for artistic adjustment
- Demonstrate **snow region**, **grass region** and **mountain region** transitions


**Guiding Questions:**
- How do you prevent harsh transitions while maintaining distinct biome characteristics?
- What height ranges work best for different landscape scales?
- How does height blending interact with other blending systems?

---

### 2. Slope-Based Blending System  
**Technical Requirements:**  
- Implement **automatic texture blending** based on surface angle/slope
- Create distinct materials for **flat surfaces** (grass, sand) vs **steep surfaces** (rock, cliff faces)
- Use **LandscapeLayerWeight** with slope calculations
- Include **slope threshold controls** with smooth falloff


**Technical Implementation:**
- Calculate slope using world normal vectors
- Implement slope masking with adjustable thresholds
- Create realistic rock/cliff materials for steep angles


**Guiding Questions:**
- How do you handle overhangs and complex geometry?
- What slope angles create the most natural-looking transitions?
- How can slope blending enhance the sense of geological realism?

---

### 3. Foliage Type Integration and Generation  
**Technical Requirements:**  
- Create **at least 3 distinct foliage types** with different environmental preferences
- Implement **foliage placement rules** based on material blend zones
- Use **Foliage Tool** with **procedural spawning** based on landscape layers
- Create **density variation** based on environmental factors (slope, height)


**Advanced Systems:** (optional)
- Foliage exclusion zones (paths, rocky areas, water edges)
- Seasonal variation support (deciduous vs evergreen placement)
- Wind exposure effects on foliage distribution
- Realistic clustering and natural distribution patterns

**Guiding Questions:**
- How do you create believable ecosystem distributions?
- What factors determine foliage density in real environments?
- How do you balance visual richness with performance?

---

## Assessment Criteria

### Exploring
**Engaging in critical and creative inquiry through questioning, research, and material/process-based investigations**
- Research real-world landscape formation and ecosystem distribution
- Investigate professional landscape material techniques used in AAA games
- Experiment with different blending algorithms and mathematical approaches
- Document your research process and technical discoveries

### Making
**Developing and refining creative work through iteration, risk-taking, and material engagement**
- Technical proficiency in complex material graph construction
- Quality of visual output and attention to naturalistic detail
- Iterative refinement of blending algorithms and visual results
- Creative problem-solving in technical implementation challenges
- Risk-taking in attempting advanced procedural techniques

### Connecting
**Communicating, collaborating, and engaging with audiences, industries, and networks**
- Clear documentation of technical systems and artistic decisions
- Understanding of professional landscape material workflows
- Communication of complex technical concepts to different audiences
- Engagement with industry-standard tools and practices
- Demonstration of collaborative potential (modular, reusable systems)

### Situating
**Critically positioning work within social, cultural, environmental, ethical, and professional contexts**
- Understanding of real-world ecological and geological principles
- Awareness of performance implications and scalability considerations
- Consideration of environmental storytelling and world-building
- Ethical awareness of representation and cultural sensitivity in landscape design
- Professional context awareness (production pipelines, team workflows)

### Synthesizing
**Bringing together disparate elements into meaningful, cohesive outcomes**
- Integration of multiple complex systems into a unified landscape material
- Coherent visual and technical approach across all blending systems
- Demonstration of how different systems complement and enhance each other
- Creation of believable, immersive landscape environments
- Synthesis of technical requirements with artistic vision


