# Code Refinement Prompt Template

Use this template to get AI assistance with improving working code incrementally (Rule 10).

---

## Targeted Refactoring Prompt

```markdown
I want to refactor this code to improve [specific aspect]:

[Paste code]

Current issue: [what you want to improve]
Goal: [specific improvement you want]

Please refactor to:
- [Specific objective 1]
- [Specific objective 2]
- [Keep constraint 1 - e.g., "maintain same interface"]
- [Keep constraint 2 - e.g., "don't change performance characteristics"]

Show the refactored version and explain the changes.
```

---

## Performance Optimization Prompt

```markdown
This code works correctly but is too slow:

[Paste code]

Performance problem:
- Current: [observed performance]
- Required: [performance requirement]
- Bottleneck: [where time is spent, if known]

Context:
- Typical input: [size/characteristics]
- Called: [how often/in what context]
- Constraints: [memory limits, etc.]

Please optimize for:
1. [Primary goal - e.g., "reduce time complexity"]
2. [Secondary goal - e.g., "reduce memory usage"]

Constraints:
- [What must stay the same - e.g., "maintain numerical accuracy"]
- [What's acceptable - e.g., "can use more memory if needed"]

Suggest specific optimizations and expected improvements.
```

---

## Readability Improvement Prompt

```markdown
This code works but is hard to understand:

[Paste code]

Readability issues I've noticed:
- [Issue 1 - e.g., "unclear variable names"]
- [Issue 2 - e.g., "complex nested logic"]

Please improve readability by:
1. Clarifying names and organization
2. Simplifying complex logic
3. Adding appropriate comments/docstrings
4. Breaking up large functions if appropriate

Maintain:
- Same functionality and interface
- Same performance characteristics

Show improved version with explanation of changes.
```

---

## Modularity Improvement Prompt

```markdown
This code is monolithic and needs better modularity:

[Paste code]

Current structure: [describe current organization]
Problems: [why it's hard to work with]

Please refactor to:
1. Separate concerns into logical components
2. Extract reusable pieces
3. Reduce coupling between parts
4. Improve testability

Context:
- This is part of: [larger system]
- Needs to interact with: [other components]
- Likely future changes: [anticipated modifications]

Suggest a modular structure and implement it.
```

---

## Error Handling Enhancement Prompt

```markdown
This code works for happy path but error handling needs improvement:

[Paste code]

Current error handling: [describe what exists]
Problems: [what's inadequate]

Enhance error handling to:
1. Detect all error conditions properly
2. Provide informative error messages
3. Use appropriate exception types
4. Enable recovery where possible
5. Fail gracefully where recovery isn't possible

Edge cases to handle:
- [Case 1]
- [Case 2]
- [Case 3]

Don't change core logic, only improve error handling.
```

---

## Type Safety Improvement Prompt

```markdown
Add type hints and improve type safety for this code:

[Paste code]

Current state: [type hints present? static analysis done?]

Please:
1. Add comprehensive type hints (parameters, returns, variables)
2. Use appropriate types from typing module
3. Handle Optional/Union types correctly
4. Add runtime type checking if appropriate
5. Make code pass [type checker - e.g., mypy] strict mode

Constraints:
- Maintain backward compatibility
- Don't change functionality

Show improved version and any type-related issues found.
```

---

## Documentation Enhancement Prompt

```markdown
This code needs better documentation:

[Paste code]

Current documentation: [what exists]
Problems: [what's missing or unclear]

Add documentation:
1. **Docstrings**: Function/class descriptions with parameters, returns, raises
2. **Inline comments**: Explain non-obvious logic
3. **Examples**: Usage examples in docstrings
4. **Type information**: Document types in docstrings
5. **Constraints**: Document assumptions and limitations

Audience: [who will use/maintain this]
Standards: [documentation style - e.g., Google, NumPy, Sphinx]

Don't change code, only add/improve documentation.
```

---

## Test Improvement Prompt

```markdown
These tests work but need improvement:

[Paste tests]

Current issues:
- [Issue 1 - e.g., "tests are flaky"]
- [Issue 2 - e.g., "unclear what's being tested"]
- [Issue 3 - e.g., "poor test organization"]

Improve tests by:
1. Making them more reliable
2. Clarifying what each test validates
3. Improving test structure and organization
4. Adding better assertions
5. Reducing duplication through fixtures

Test framework: [pytest, unittest, etc.]

Show improved test suite.
```

---

## Interface Simplification Prompt

```markdown
This API works but is too complicated:

[Paste interface/function signatures]

Current problems:
- [Issue 1 - e.g., "too many parameters"]
- [Issue 2 - e.g., "unclear parameter purposes"]
- [Issue 3 - e.g., "non-intuitive usage"]

Simplify by:
1. Reducing number of parameters (sensible defaults, parameter objects)
2. Making common cases easy, complex cases possible
3. Following principle of least surprise
4. Improving parameter naming and organization

Constraints:
- [What compatibility must be maintained]
- [What can break]

Suggest simplified interface and migration path if breaking.
```

---

## Code Consolidation Prompt

```markdown
I have similar code in multiple places that should be consolidated:

**Instance 1:**
[Paste code 1]

**Instance 2:**
[Paste code 2]

**Instance 3 (if applicable):**
[Paste code 3]

Similarities: [what's common]
Differences: [what varies]

Please:
1. Extract common logic into reusable function/class
2. Parameterize the differences
3. Show how to call the consolidated version from each location
4. Ensure no functionality is lost

Where should the consolidated code live? [in what module/class]
```

---

## Dependency Reduction Prompt

```markdown
This code has too many dependencies:

[Paste code]

Current dependencies: [list what it depends on]
Problem: [why this is an issue]

Help me reduce dependencies by:
1. Identifying which dependencies are truly necessary
2. Finding lightweight alternatives
3. Implementing simple functionality directly if appropriate
4. Restructuring to decouple from heavy dependencies

Constraints:
- [What functionality must be preserved]
- [What dependencies are acceptable]

Suggest approach to reduce dependencies while maintaining functionality.
```

---

## Design Pattern Application Prompt

```markdown
This code could benefit from a design pattern:

[Paste code]

Current approach: [describe structure]
Problem: [what's difficult or error-prone]

I think [pattern name] might help, but unsure.

Please:
1. Confirm if [pattern] is appropriate here
2. If yes, show how to apply it
3. If no, suggest a better pattern
4. Explain benefits and trade-offs

Context:
- This code is used for: [purpose]
- Likely future changes: [what might change]
- Complexity tolerance: [how much abstraction is acceptable]
```

---

## Naming Improvement Prompt

```markdown
Help me improve naming in this code:

[Paste code]

Naming issues:
- [Issue 1 - e.g., "unclear variable names"]
- [Issue 2 - e.g., "inconsistent naming conventions"]

Please suggest better names that:
1. Clearly indicate purpose
2. Follow [language/framework] conventions
3. Are appropriately concise/detailed
4. Are consistent within this codebase

For each renaming, explain why the new name is better.

Context: [domain/application]
Existing conventions: [any project-specific naming patterns]
```

---

## Quick Tips

- **Be specific about what to improve** - "make it better" is too vague
- **State what must stay the same** - interface, performance, behavior
- **One improvement at a time** - don't ask for multiple refactorings together
- **Explain the problem** - why does it need improvement?
- **Consider backward compatibility** - what changes are breaking?
- **Test after refactoring** - ensure behavior hasn't changed
- **Review incrementally** - refactor small pieces, not whole systems

---

## Example (Geophysics Context)

````markdown
This code works correctly but is too slow:

```python
def compute_all_semblances(gather, velocities, window=10):
    """Compute semblance for all velocities."""
    results = []
    for vel in velocities:
        sem = compute_semblance(gather, vel, window)
        results.append(sem)
    return np.array(results)
```

Performance problem:
- Current: 45 seconds for 100 velocities on 1000-trace gather
- Required: <5 seconds
- Bottleneck: Repeated gather traversal in compute_semblance

Context:
- Typical input: 48 traces, 1000 samples, 100 test velocities
- Called: Once per CMP in velocity analysis (thousands of CMPs)
- Constraints: Memory usage should stay reasonable (<2GB)

Please optimize for:
1. Reduce time by vectorizing or reducing redundant computation
2. Maintain accuracy (same semblance values)

Constraints:
- Must maintain same output format and values
- Can use more memory if needed for speed
- Prefer NumPy solutions over Numba/Cython if possible

The current implementation calls compute_semblance() in a loop, and each call iterates over all samples and traces. Can we vectorize this or compute all velocities at once?

Suggest specific optimizations and expected improvements.
````
