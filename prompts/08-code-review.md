# Code Review Prompt Template

Use this template to get AI assistance with reviewing generated code for correctness and appropriateness (Rule 9).

---

## General Code Review Prompt

```markdown
Please review this code for [component/function]:

[Paste code]

Context:
- Purpose: [what it's supposed to do]
- Domain: [field/application area]
- Requirements: [key requirements it should meet]

Review for:
1. **Correctness**: Does the logic actually do what it claims?
2. **Edge cases**: Are edge cases handled properly? Are there cases that will break it?
3. **Efficiency**: Are there obvious performance issues or inefficiencies?
4. **Clarity**: Is the code readable and well-organized?
5. **Standards**: Does it follow [language/framework] best practices?
6. **Domain appropriateness**: Is this how [problem] should be solved in [field]?

Identify specific issues with line numbers and suggest improvements.
```

---

## Scientific Correctness Review Prompt

```markdown
Please review this scientific computing code:

[Paste code]

Scientific context:
- What it computes: [description]
- Domain: [field]
- Expected behavior: [what results should look like]
- Validation criteria: [how to know if it's correct]

Review specifically for:
1. **Algorithm correctness**: Is the algorithm implemented properly?
2. **Numerical stability**: Are there precision or overflow issues?
3. **Units and conventions**: Are units handled correctly? Domain conventions followed?
4. **Physical plausibility**: Do the computations make physical sense?
5. **Edge cases in domain**: How does it handle [field-specific edge cases]?
6. **Comparison with standards**: How does this compare to standard implementations?

Is this scientifically sound for [problem] in [field]?
```

---

## Implementation vs. Specification Review Prompt

```markdown
Please verify this implementation matches my specifications.

**Specification:**
[Paste your requirements/specification]

**Implementation:**
[Paste code]

Check:
1. **Functional requirements**: Does it do everything specified?
2. **Interface contract**: Does the signature match? Are types correct?
3. **Edge cases**: Are all specified edge cases handled as required?
4. **Error handling**: Does error handling match specification?
5. **Performance**: Does it meet specified performance requirements?
6. **Deviations**: What differs from the spec, and why?

List any discrepancies between specification and implementation.
```

---

## Test Coverage Review Prompt

```markdown
Review these tests for [component]:

**Code being tested:**
[Paste implementation]

**Test suite:**
[Paste tests]

Evaluate:
1. **Coverage**: What's tested? What's missing?
2. **Test quality**: Are tests actually validating behavior or just syntax?
3. **Edge cases**: Are important edge cases tested?
4. **Assertions**: Are assertions specific and meaningful?
5. **Test independence**: Do tests properly isolate the component?
6. **False confidence**: Could these tests pass with broken code?

What additional tests are needed to ensure correctness?
```

---

## Architecture Review Prompt

```markdown
Review the architecture of this component:

[Paste code or describe structure]

Context:
- Purpose: [what it does]
- Part of: [larger system]
- Interacts with: [other components]

Evaluate:
1. **Separation of concerns**: Are responsibilities clearly separated?
2. **Modularity**: Is it broken into appropriate pieces?
3. **Coupling**: Are dependencies appropriate and minimal?
4. **Extensibility**: How easy to modify or extend?
5. **Testability**: Is it structured for easy testing?
6. **Design patterns**: Are appropriate patterns used? Inappropriately complex?

Suggest architectural improvements or confirm design is sound.
```

---

## Error Handling Review Prompt

```markdown
Review error handling in this code:

[Paste code]

Context: [what the code does]

Check:
1. **Error detection**: Are all error conditions detected?
2. **Error types**: Are appropriate exception types used?
3. **Error messages**: Are messages informative for debugging?
4. **Error propagation**: Are errors handled at the right level?
5. **Recovery**: Is graceful degradation possible where appropriate?
6. **Edge cases**: What errors could occur that aren't handled?

What error scenarios am I missing? How could error handling be improved?
```

---

## Performance Review Prompt

```markdown
Review performance characteristics of this code:

[Paste code]

Context:
- Input size: [typical data size]
- Performance requirements: [requirements if any]
- Current observations: [any performance issues noticed]

Analyze:
1. **Time complexity**: What's the algorithmic complexity? Optimal?
2. **Space complexity**: What's memory usage? Any waste?
3. **Bottlenecks**: What operations are most expensive?
4. **Unnecessary work**: Any redundant computations or operations?
5. **Optimization opportunities**: Where can this be improved?
6. **Trade-offs**: What trade-offs exist between approaches?

Suggest specific optimizations with expected impact.
```

---

## Domain Conventions Review Prompt

```markdown
Review this code for adherence to [field] conventions:

[Paste code]

Domain: [field/subfield]
Standards: [any specific standards or conventions]

Check:
1. **Terminology**: Are standard terms used correctly?
2. **Units**: Are units standard for the field? Handled properly?
3. **Coordinate systems**: Are conventions followed (e.g., origin, axis order)?
4. **Algorithms**: Are standard algorithms used? Implemented correctly?
5. **Data structures**: Do data representations match field standards?
6. **Citations**: Should any methods reference papers or standards?

Does this code follow [field] best practices? What would domain experts flag?
```

---

## Security & Robustness Review Prompt

```markdown
Review this code for security and robustness:

[Paste code]

Context: [what it does, where it runs]

Check:
1. **Input validation**: Are inputs validated before use?
2. **Resource limits**: Can inputs cause excessive resource use?
3. **Injection risks**: Any code/SQL/command injection possibilities?
4. **Error exposure**: Do error messages leak sensitive information?
5. **Dependencies**: Are third-party libraries trustworthy and updated?
6. **Failure modes**: How does it fail? Gracefully or catastrophically?

What could go wrong? What hardening is needed?
```

---

## Code Smell Detection Prompt

```markdown
Review this code for common issues and "code smells":

[Paste code]

Look for:
1. **Complexity**: Overly complex logic, deep nesting, long functions?
2. **Duplication**: Repeated code or logic?
3. **Magic values**: Hard-coded constants that should be named?
4. **Poor naming**: Unclear variable/function names?
5. **Tight coupling**: Excessive dependencies between components?
6. **Incomplete implementation**: TODOs, placeholders, commented-out code?
7. **Anti-patterns**: Common mistakes for [language/framework]?

Identify issues and suggest refactoring approaches.
```

---

## Comparison Review Prompt

```markdown
Compare these two implementations of [functionality]:

**Implementation A:**
[Paste code A]

**Implementation B:**
[Paste code B]

Compare:
1. **Correctness**: Do both work? Any differences in behavior?
2. **Clarity**: Which is more readable and maintainable?
3. **Performance**: Which is more efficient?
4. **Robustness**: Which handles edge cases better?
5. **Simplicity**: Which is simpler without sacrificing functionality?
6. **Appropriateness**: Which better fits [domain/use case]?

Which should I use and why? Or suggest a hybrid approach?
```

---

## Quick Tips

- **Review in context** - provide purpose and requirements
- **Be specific about concerns** - guide the review to what matters
- **Include test results** - show what passes and what fails
- **Ask about domain fit** - generic code might not fit your field
- **Request alternatives** - there might be better approaches
- **Check your understanding** - explain the code back to verify comprehension
- **Review incrementally** - review small pieces as they're generated

---

## Example (Geophysics Context)

````markdown
Please review this scientific computing code:

```python
def compute_semblance(gather, velocity, window_samples=10):
    """Compute semblance along NMO curve."""
    n_traces, n_samples = gather.shape
    semblance = np.zeros(n_samples)
    
    for t in range(n_samples):
        stack = 0
        sum_sq = 0
        for i in range(n_traces):
            offset = i * 25  # offset increment
            nmo_time = int(t + (offset**2 / velocity**2) / (2 * t))
            if 0 <= nmo_time < n_samples:
                stack += gather[i, nmo_time]
                sum_sq += gather[i, nmo_time]**2
        
        if sum_sq > 0:
            semblance[t] = (stack**2 / n_traces) / sum_sq
    
    return semblance
```

Scientific context:
- Computes semblance (coherence measure) for velocity analysis
- Domain: Seismic processing
- Expected: High semblance at true velocity, low elsewhere
- Validation: Should give semblance ~1.0 for flat event at correct velocity

Review specifically for:
1. **Algorithm correctness**: Is NMO correction formula right? Is semblance formula correct?
2. **Numerical stability**: Issues with division by zero? Small denominators?
3. **Units and conventions**: Time in samples or seconds? Velocity units?
4. **Physical plausibility**: Does NMO time calculation make physical sense?
5. **Edge cases in domain**: What about muted traces? Near-offset? Time=0?
6. **Comparison with standards**: How does this compare to standard semblance implementations?

Issues I'm concerned about: The hardcoded offset increment, the integer time calculation, whether semblance formula is right.

Is this scientifically sound for semblance computation in seismic processing?
````
