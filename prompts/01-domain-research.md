# Domain Research Prompt Template

Use this template to get AI assistance with gathering domain knowledge before implementation (Rule 1).

---

## Basic Research Prompt

```markdown
I'm working on [brief description of problem/task] in [domain/field].

Please help me research:
1. Standard libraries/tools used for [specific task] in [domain]
2. Common data formats and structures for [type of data]
3. Typical approaches or algorithms for [problem type]
4. Key papers or references I should be aware of
5. Common pitfalls or edge cases in this domain

Current context:
- My data: [brief description of input/output data]
- My constraints: [any known limitations]
- What I already know: [list key concepts/tools you're familiar with]
```

---

## Deep Dive Research Prompt

```markdown
I need to understand [specific concept/technique] better for my [project description].

Please provide:
1. A conceptual explanation (assume I know [your background level])
2. How this is typically implemented in [language/framework]
3. Trade-offs between different approaches
4. What expert practitioners prioritize when implementing this
5. References to authoritative sources (papers, documentation, examples)

Specific questions I have:
- [Question 1]
- [Question 2]
- [Question 3]

I want to understand this well enough to: [your goal - e.g., "evaluate whether an AI-generated implementation is correct"]
```

---

## Comparative Analysis Prompt

```markdown
I'm deciding between [approach A] and [approach B] for [task] in my [project type].

For each approach, please explain:
1. Typical use cases and when it's preferred
2. Performance characteristics (speed, memory, scalability)
3. Implementation complexity
4. Common libraries that support it
5. Domain-specific considerations in [field]

My specific constraints:
- Data size/characteristics: [description]
- Performance requirements: [requirements]
- Integration needs: [how it fits in your project]

Help me understand which approach best fits my situation and why.
```

---

## Existing Implementation Review

```markdown
I found this [library/implementation/approach] for [task]: [link or description]

Please help me evaluate it:
1. Is this a standard/well-regarded solution in [domain]?
2. What are its key strengths and limitations?
3. What alternatives exist and how do they compare?
4. Are there any red flags or concerns I should be aware of?
5. How would I adapt/extend this for [your specific needs]?

My use case: [brief description]
My data characteristics: [description]
```

---

## Quick Tips

- **Be specific about your domain** - "geophysics" is better than "science", "seismic data processing" is even better
- **State your current knowledge level** - helps AI pitch explanations appropriately
- **Include data characteristics** - real-world constraints shape practical solutions
- **Ask for references** - "what should I read?" gets you authoritative sources
- **Request comparisons** - understanding trade-offs is crucial for decision-making
- **Follow up iteratively** - use responses to formulate deeper questions

---

## Example (Geophysics Context)

```markdown
I'm working on seismic velocity model interpolation for my geophysics PhD project.

Please help me research:
1. Standard libraries/tools used for 3D spatial interpolation of geophysical data
2. Common approaches for handling irregular sampling in seismic surveys
3. How practitioners typically validate interpolated velocity models
4. Key considerations for interpolating discontinuous features (e.g., layer boundaries)
5. References to papers on seismic velocity interpolation methods

Current context:
- My data: Irregularly sampled velocity measurements from wells (100-1000 points in 3D space)
- My constraints: Need physically plausible results respecting geological structure
- What I already know: Basic interpolation methods (linear, cubic), aware of kriging but haven't used it

I want to understand the domain well enough to choose an appropriate method and evaluate AI-generated implementations.
```
