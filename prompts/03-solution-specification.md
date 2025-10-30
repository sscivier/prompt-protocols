# Solution Specification Prompt Template

Use this template to get AI assistance with specifying inputs, outputs, and requirements before implementation (Rule 3).

---

## Input/Output Specification Prompt

```
For [function/component] that will [purpose], help me specify the interface.

Functional goal: [what it accomplishes]

Please help me define:
1. **Inputs**: What parameters are needed?
   - For each: type, constraints, valid ranges, default values
   - What variations or formats should be accepted?
   
2. **Outputs**: What should be returned?
   - Type, structure, format
   - What information must be included?
   - How should errors/edge cases be represented?

3. **Interface design**: 
   - Should this be a function, class, or module?
   - Are there multiple related operations that should be grouped?
   - What flexibility should the interface provide?

Context:
- This will be used for: [use case]
- It will be called by: [caller/user]
- Integration requirements: [how it fits with other code]
```

---

## Success Criteria Prompt

```
For [component] that [does X], help me define concrete success criteria.

Functionality: [description]

Help me specify:
1. **Functional correctness**: What does correct output look like?
   - For typical inputs: [describe expected behavior]
   - For edge cases: [list key edge cases and expected handling]
   
2. **Performance requirements**:
   - Speed: [e.g., "process 10K records in <1 second"]
   - Memory: [e.g., "handle datasets up to 1GB without loading all in memory"]
   - Scalability: [how should it scale with input size?]
   
3. **Quality attributes**:
   - Reliability: [error handling, failure modes]
   - Usability: [API clarity, documentation]
   - Maintainability: [code clarity, modularity]

4. **Validation approach**: How will I verify these criteria are met?

What am I missing? What other success criteria are important for [problem type]?
```

---

## Constraint Specification Prompt

```
For [project/component], help me identify and specify all relevant constraints.

Context: [brief description]

Please help me catalog:
1. **Technical constraints**:
   - Language/framework limitations: [what I'm using]
   - Dependencies: [what's available, what's not]
   - Platform requirements: [where it runs]
   
2. **Resource constraints**:
   - Computational: [CPU, memory, time limits]
   - Data: [size limits, storage, bandwidth]
   
3. **Integration constraints**:
   - Must maintain compatibility with: [existing interfaces]
   - Must work with: [existing systems/data formats]
   - Cannot change: [what's locked]
   
4. **Domain constraints**:
   - Scientific/methodological requirements: [field-specific rules]
   - Accuracy/precision needs: [numerical considerations]
   - Validation requirements: [what must be verified]

What constraints am I likely overlooking for [problem type]?
```

---

## Interface Design Prompt

```
I'm designing the interface for [component] in [project].

Purpose: [what it does]
Users: [who/what will call it]

Help me design a clean interface:
1. **Function signature(s)**: What should the API look like?
   - Required parameters vs. optional
   - Parameter ordering and naming
   - Return type and structure
   
2. **Flexibility vs. simplicity**: 
   - What configuration options are needed?
   - What can be hard-coded vs. parameterized?
   - Should there be multiple functions or one with options?
   
3. **Error handling**:
   - What can go wrong?
   - Should errors raise exceptions or return error codes?
   - What information should error messages include?
   
4. **Consistency**: 
   - What patterns exist in similar code in [project/library]?
   - What conventions should I follow?

Current thinking: [your draft interface if you have one]

Help me design an interface that's easy to use correctly and hard to use incorrectly.
```

---

## Dependency Analysis Prompt

```
For [project/component] in [language/framework], help me analyze dependencies.

What I'm building: [description]
Key operations needed: [list main operations]

Please help me:
1. **Identify required libraries**:
   - What's the standard library for [specific task]?
   - What are the trade-offs between options?
   - What versions are recommended and why?
   
2. **Assess compatibility**:
   - Are these dependencies compatible with each other?
   - What Python version / runtime requirements exist?
   - Are there known conflicts?
   
3. **Evaluate maintenance status**:
   - Are these actively maintained?
   - Are there more modern alternatives?
   - What's the risk of deprecation?
   
4. **Consider alternatives**:
   - Can I accomplish this with fewer dependencies?
   - Are there lightweight alternatives?
   - What's the trade-off between rolling my own vs. using a library?

Current dependencies I'm considering: [list if known]
Constraints: [e.g., "must be pip-installable", "no commercial licenses"]
```

---

## Requirements Validation Prompt

```
Here are my requirements for [component/system]:

[Paste your requirements]

Please review and help me:
1. **Check completeness**: What's missing?
   - Have I specified all inputs and outputs?
   - Have I covered all edge cases?
   - Have I defined success criteria clearly?
   
2. **Check consistency**: Are there contradictions?
   - Do requirements conflict?
   - Are constraints compatible?
   - Are performance and quality requirements realistic?
   
3. **Check clarity**: Are requirements specific enough?
   - Is anything ambiguous?
   - Can these be tested objectively?
   - Would an implementer know exactly what to build?
   
4. **Suggest improvements**: How can I make these requirements better?

Domain context: [field/application]
```

---

## Quick Tips

- **Be precise about types and formats** - "array" vs "numpy array, shape (n,m), dtype float64"
- **Specify constraints explicitly** - "positive integer" vs "integer"
- **Think about the caller** - design interfaces for how they'll be used
- **Consider future changes** - what flexibility might you need later?
- **List what you're uncertain about** - AI can help you decide
- **Get feedback on your specs** - validate completeness before coding

---

## Example (Geophysics Context)

```
For a function that will compute seismic attributes from trace data, help me specify the interface.

Functional goal: Calculate various seismic attributes (instantaneous amplitude, phase, frequency) from seismic traces

Please help me define:
1. **Inputs**: What parameters are needed?
   - Seismic trace data format and type?
   - Which attributes to compute (all? specified list? one at a time?)
   - Time/sample range to compute over (all? specified window?)
   - Any algorithm-specific parameters (window size, etc.)
   
2. **Outputs**: What should be returned?
   - Single array with all attributes? Dictionary? Multiple arrays?
   - Same shape as input? Different sampling?
   - How to handle time information / sample indices?

3. **Interface design**: 
   - Single function with attribute parameter vs. separate functions per attribute?
   - How to handle multiple traces (batch processing)?
   - Configuration for Hilbert transform parameters?

Context:
- Will be used in: Interactive seismic interpretation workflow
- Called by: Analysis scripts processing hundreds of traces
- Integration: Should match conventions in ObsPy / Madagascar packages
```
