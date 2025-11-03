# Problem Framing Prompt Template

Use this template to get AI assistance with framing your problem programmatically before implementation (Rule 2 & Rule 4).

---

## Problem Decomposition Prompt

```markdown
I need to solve [high-level problem description] as part of my [project type].

Help me break this down programmatically:
1. What are the core sub-problems that need to be solved?
2. What are the key algorithmic steps (language-agnostic)?
3. What data transformations are needed at each step?
4. What are the critical decision points or branching logic?
5. What are potential edge cases or failure modes?

Context:
- Input: [describe input data/parameters]
- Output: [describe desired output]
- Constraints: [list any constraints]

I want to understand WHAT needs to be solved, not yet HOW to code it.
```

---

## Architecture Design Prompt

```markdown
I'm designing [component/module] that will [purpose] in my [project].

Please help me think through:
1. Appropriate data structures for [describe data being manipulated]
2. Algorithm selection for [key operations] considering [constraints]
3. How this component should interface with [related components]
4. Separation of concerns - what responsibilities belong where?
5. Design patterns that fit this problem (e.g., factory, strategy, pipeline)

Architectural context:
- This fits into: [larger system description]
- It needs to work with: [existing components/interfaces]
- Key operations: [list main operations]
- Performance requirements: [any speed/memory constraints]

Help me design the structure before writing code.
```

---

## Algorithm Selection Prompt

```markdown
For [specific task], I need to choose an appropriate algorithm.

The problem characteristics:
- Input size/type: [description]
- Output requirements: [description]
- Performance constraints: [time/space complexity needs]
- Special considerations: [e.g., "must be deterministic", "needs to handle streaming data"]

Please compare:
1. What algorithms are commonly used for this problem type?
2. What are the time/space complexity trade-offs?
3. Which is most appropriate given my constraints?
4. Are there domain-specific variations I should know about (in [field])?
5. What are the implementation considerations for each?

Help me understand the algorithmic approach before implementation details.
```

---

## Data Flow Design Prompt

```markdown
I'm working on [system/pipeline] that processes [type of data].

Help me design the data flow:
1. What are the stages of data transformation from input to output?
2. What intermediate representations make sense?
3. Where should validation/error checking occur?
4. What state needs to be maintained between operations?
5. Are there opportunities for parallelization or streaming?

Data characteristics:
- Input: [format, size, frequency]
- Output: [format, purpose]
- Processing steps I envision: [your initial thoughts]
- Scale: [how much data, how often]

Map out the data flow architecture before implementation.
```

---

## Integration Planning Prompt

```markdown
I need to integrate [new functionality] into my existing [project description].

Current setup:
- Existing code structure: [brief description]
- Relevant interfaces/APIs: [what needs to stay compatible]
- Dependencies: [relevant libraries/modules]
- Constraints: [what can't be changed]

Help me plan:
1. Where should this new functionality live in the codebase?
2. What interfaces/APIs should it expose?
3. How should it interact with existing components?
4. What existing patterns should I follow for consistency?
5. What potential conflicts or integration challenges should I anticipate?

Guide me on how this fits architecturally before implementation.
```

---

## Edge Case Identification Prompt

```markdown
For [function/component] that [description], help me identify edge cases.

Core functionality:
- Inputs: [types, expected ranges, formats]
- Processing: [what the function does]
- Outputs: [expected results]

Please identify:
1. Boundary conditions (empty inputs, extreme values, limits)
2. Invalid inputs (wrong types, malformed data, violations of assumptions)
3. Resource constraints (memory limits, computation time, file size)
4. Domain-specific edge cases in [field] for [operation]
5. Race conditions or state issues (if applicable)

For each edge case, suggest:
- Expected behavior (error, default value, graceful degradation)
- How it should be detected
- How it should be handled

Help me think through what could go wrong before writing code.
```

---

## Quick Tips

- **Describe the problem, not the code** - think in terms of transformations and logic
- **Work from high-level to details** - decompose complex problems into simpler sub-problems
- **Consider data characteristics** - algorithm choice depends on data size and properties
- **Think about interfaces early** - how components connect affects overall design
- **Identify edge cases before coding** - they influence architectural decisions
- **Use pseudocode** - express logic without language syntax constraints

---

## Example (Geophysics Context)

```markdown
I need to solve stratigraphic layer correlation across seismic sections as part of my seismic interpretation project.

Help me break this down programmatically:
1. What are the core sub-problems that need to be solved?
2. What are the key algorithmic steps (language-agnostic)?
3. What data transformations are needed at each step?
4. What are the critical decision points or branching logic?
5. What are potential edge cases or failure modes?

Context:
- Input: Two 2D arrays representing seismic amplitude sections, each with marked interpreted horizons (x, depth, horizon_id)
- Output: Mapping between horizon IDs in section A to horizon IDs in section B (dictionary or pairs)
- Constraints: Horizons may not all correlate (faults, erosion), need to handle missing/partial horizons

I want to understand WHAT needs to be solved: similarity metrics, matching algorithms, confidence scoring, handling of non-correlating horizons - but not yet HOW to code it.
```
