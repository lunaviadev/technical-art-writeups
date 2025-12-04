# Week 1 Task – Engine Understanding  
 

## Brief  
This week focuses on developing an understanding of how modern game engines manage rendering, optimisation, and technical workflows. To build your knowledge base, you are required to research and write a **500–1000 word essay** on **one** of the following topics.  

Your essay should demonstrate critical and creative inquiry, supported by research, and should contextualise your findings within the field of **technical art and games development**.  

---

## Topics (choose one)  

### 1. Nanite and the Rendering Pipeline  
**Guiding questions:**  
- How does Nanite fit into the rendering pipeline compared to traditional geometry handling?  
- What technical challenges does Nanite solve for developers and artists?  
- What limitations or drawbacks does it introduce?  
- How does Nanite affect performance, optimisation, and asset workflows?  
- What does the future of Nanite (and similar technologies) look like?  



### 2. The Evolution of Anti-Aliasing in Games  
**Guiding questions:**  
- What were the earliest forms of anti-aliasing in games?  
- How did MSAA, FXAA, and SMAA contribute to visual improvements?  
- How do temporal methods like TAA differ from older techniques?  
- What role do machine-learning solutions (e.g., DLSS, FSR, XeSS) play today?  
- How do these techniques balance visual fidelity with performance?  
- What does this evolution say about hardware capabilities and player expectations?  



### 3. The Evolution of Shader Graphs in Game Development
**Guiding questions:**
- What were workflows like before shader graphs existed?
- How did node-based editors change accessibility for artists and non-programmers?
- What are the strengths and weaknesses of shader graphs compared to handwritten shaders?
- How have different engines (Unreal, Unity, proprietary) approached shader graphs?
- What role do shader graphs play in bridging art and technical workflows?
- How might shader authoring evolve in the future?



### 4. Technical Art Optimization for Indie Game Development
**Guiding questions:**
- How do indie developers choose between forward and deferred rendering pipelines with limited resources?
- What anti-aliasing techniques offer the best quality-to-performance ratio for indie games targeting diverse hardware?
- How do shader graphs versus hand-coded shaders impact iteration speed and visual quality in small teams?
- What rendering optimizations are most critical when developing for multiple platforms with a small team?
- How do indie developers balance visual fidelity with performance constraints compared to AAA studios?
- What creative technical solutions have successful indie games employed to achieve distinctive visual styles efficiently?
- How does the choice of rendering pipeline and shader workflow affect an indie game's scalability and maintainability?

---

## Assessment Criteria

Your work will be evaluated against the following four criteria:  

- **Exploring**: Engaging in critical and creative inquiry through questioning, research, and analysis of tools, technologies, and processes.
- **Connecting**: Communicating ideas clearly while linking to industry practices, professional workflows, and wider technical art contexts.
- **Situating**: Critically positioning your research within social, cultural, environmental, ethical, and professional frameworks.
- **Synthesizing**: Bringing together research, examples, and critical reflection into a cohesive, well-structured essay.

---

## Essay Structure Guide

### Recommended Structure in Markdown

Your essay should follow a clear academic structure that addresses all assessment criteria. Below is a suggested template:

```markdown
# [Your Essay Title]
**Student Name** | **Student ID** | **Date**

---

## Introduction (100-150 words)
*Assessment Focus: Exploring + Synthesizing*

- **Hook**: Open with a compelling statement or industry example
- **Context**: Briefly introduce the topic and its relevance to technical art
- **Thesis Statement**: Clearly state your main argument or perspective
- **Roadmap**: Outline what the essay will cover

Example opening:
> "As game engines evolve, [topic] has become increasingly critical for..."


## Background/Historical Context (150-200 words)
*Assessment Focus: Exploring + Connecting*

- Provide technical foundation and definitions
- Explain the evolution or current state of the technology
- Reference key developments or milestones
- Use academic and industry sources to support claims

**Research Integration:**
- Include at least 2-3 academic or industry sources
- Use inline citations: "According to Smith (2023), [concept]..."
- Reference technical documentation, GDC talks, or research papers


## Critical Analysis (300-400 words)
*Assessment Focus: Exploring + Connecting + Situating*

This is the core of your essay. Address multiple perspectives:

### Technical Perspective
- How does the technology work?
- What are the technical advantages and limitations?
- Include specific examples from game engines (Unity, Unreal, etc.)

### Industry Practice
- How do professional studios implement this?
- What workflows or best practices have emerged?
- Reference real game examples or case studies

### Critical Considerations
- Performance implications
- Accessibility for different team sizes/budgets
- Platform-specific considerations
- Environmental/ethical considerations (e.g., power consumption, accessibility)

**Use subheadings** to organize complex analysis:
```markdown
### Performance Trade-offs
[Analysis content...]

### Workflow Implications
[Analysis content...]
```


## Future Implications/Conclusion (100-150 words)
*Assessment Focus: Synthesizing + Situating*

- Synthesize your key findings
- Discuss future trends or developments
- Consider broader implications for the industry
- Reflect on what this means for technical artists
- End with a strong concluding statement

Example:
> "The evolution of [topic] demonstrates how technical art continues to bridge..."


## References
*Required for academic integrity*

Use a consistent citation format (Harvard, APA, or IEEE). List all sources alphabetically:

```markdown
## References

Epic Games. (2023). *Nanite Virtualized Geometry*. Unreal Engine Documentation.
Available at: https://docs.unrealengine.com/... [Accessed: 1 Nov 2024]

Karis, B. (2021). "A Deep Dive into Nanite Virtualized Geometry".
*SIGGRAPH 2021*. ACM Digital Library.

Smith, J. and Jones, A. (2023). "Real-time Rendering Techniques in Modern Game Engines".
*Journal of Computer Graphics Techniques*, 12(3), pp. 45-67.
```
```

---

### Markdown Formatting Tips for Academic Writing

#### Emphasis and Structure
```markdown
**Bold** for key terms and emphasis
*Italics* for technical terms on first use or titles
> Blockquotes for important quotes from sources
`Code formatting` for technical terms, shader code, or API names
```

#### Lists for Clarity
```markdown
- Use bullet points for features or characteristics
1. Use numbered lists for sequential processes or rankings
```

#### Headings Hierarchy
```markdown
# Main Title (H1)
## Major Sections (H2)
### Subsections (H3)
#### Minor Points (H4)
```

#### Tables for Comparisons
```markdown
| Technique | Performance | Quality | Use Case |
|-----------|-------------|---------|----------|
| MSAA      | Medium      | High    | Desktop  |
| FXAA      | High        | Medium  | Mobile   |
| TAA       | Medium      | High    | Modern   |
```

#### Images and Diagrams
```markdown
![Rendering Pipeline Diagram](path/to/image.png)
*Figure 1: Overview of the rendering pipeline stages*
```

---

### Mapping Structure to Assessment Criteria

| Essay Section | Primary Criteria | How to Address |
|---------------|------------------|----------------|
| **Introduction** | Exploring, Synthesizing | Pose critical questions; establish clear thesis |
| **Background** | Exploring, Connecting | Research-backed context; link to industry standards |
| **Analysis** | All Four Criteria | Deep technical analysis; industry examples; critical positioning; ethical/social considerations |
| **Conclusion** | Synthesizing, Situating | Bring together insights; reflect on broader implications |
| **Throughout** | Connecting | Use industry terminology; reference professional workflows; cite practitioners |

---

### Research and Citation Guidelines

#### Quality Sources to Use:
- **Academic**: SIGGRAPH papers, IEEE publications, academic journals
- **Industry**: GDC talks, official engine documentation, technical blogs from studios
- **Professional**: Gamasutra/Game Developer articles, technical artist blogs
- **Primary**: Engine documentation (Unity, Unreal), GPU vendor whitepapers (NVIDIA, AMD)

#### Minimum Research Expectations:
- **5-8 sources** minimum for a well-researched essay
- Mix of academic and industry sources
- At least 2-3 technical/primary sources (documentation, whitepapers)
- Recent sources (within last 5 years preferred, unless discussing history)

#### Citation Best Practices:
```markdown
Inline citation: "Nanite uses a hierarchical level of detail system (Karis, 2021)..."

Multiple sources: "This approach has been widely adopted (Smith, 2022; Jones, 2023)..."

Direct quote: According to Epic Games (2023), "Nanite allows for film-quality
source art comprising hundreds of millions of polygons."
```

---

### Word Count Management

| Section | Target Words | Percentage |
|---------|--------------|------------|
| Introduction | 100-150 | 15% |
| Background | 150-200 | 20% |
| Critical Analysis | 300-400 | 50% |
| Conclusion | 100-150 | 15% |
| **Total** | **650-900** | **100%** |

*Note: Aim for 700-850 words to stay comfortably within the 500-1000 word range while allowing for editing.*

---

### Checklist Before Submission

- [ ] Essay addresses the chosen topic's guiding questions
- [ ] Clear thesis statement in introduction
- [ ] 5-8 quality sources cited throughout
- [ ] All four assessment criteria addressed
- [ ] Technical accuracy verified against documentation
- [ ] Industry examples and real-world applications included
- [ ] Critical analysis includes multiple perspectives
- [ ] Proper markdown formatting applied
- [ ] References section complete and formatted consistently
- [ ] Word count between 500-1000 words
- [ ] Proofread for clarity and academic tone
- [ ] Converted to PDF or Word format for submission

---

**Submission format:** Word or PDF document (500–1000 words).
**Deadline:** Formative - 7th of November | Summative - 5th of December.

---

