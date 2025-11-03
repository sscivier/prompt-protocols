# Test Design Prompt Template

Use this template to get AI assistance with designing comprehensive test cases before implementation (Rule 6 & Rule 7).

---

## Test Case Generation Prompt

```markdown
For [function/component] that [description], help me design comprehensive test cases.

Functionality:
- Inputs: [describe parameters and types]
- Processing: [what it does]
- Outputs: [what it returns]
- Edge cases I've identified: [list any you know]

Please generate test scenarios for:
1. **Happy path**: Normal, expected operation
2. **Boundary conditions**: Empty inputs, minimum/maximum values, limits
3. **Invalid inputs**: Wrong types, out-of-range values, malformed data
4. **Edge cases**: Null values, special values (inf, nan), zero-length arrays
5. **Domain-specific cases**: [field]-specific scenarios for [operation]

For each test case, specify:
- Input values (concrete examples)
- Expected output or behavior
- Rationale (why this case matters)

What test cases am I likely missing for [problem type]?
```

---

## Behavioral Specification Prompt

```markdown
I need to specify the behavior of [function/component] through tests.

High-level requirements:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

Help me translate these into concrete, testable assertions:
1. What specific conditions should I test?
2. What are the acceptance criteria for each requirement?
3. How can I verify correct behavior programmatically?
4. What are examples of inputs that should pass/fail?

Convert requirements into test specifications that clearly define success.
```

---

## Edge Case Discovery Prompt

```markdown
For [function/component] with this signature:
[Function signature or API description]

That does: [description of functionality]

Help me systematically identify edge cases:
1. **Input space boundaries**: What are extreme valid inputs?
2. **Invalid inputs**: What shouldn't be accepted?
3. **Numerical issues**: Overflow, underflow, precision, inf, nan?
4. **Data structure issues**: Empty, single element, very large?
5. **State issues**: Order dependencies, initialization, cleanup?
6. **Resource limits**: Memory, time, file handles, network?
7. **Domain-specific**: What goes wrong in [field] for [operation]?

For each edge case:
- Should it be handled gracefully or raise an error?
- If handled, what's the expected behavior?
- If error, what type and message?

Assume inputs are [data type/structure] with [characteristics].
```

---

## Test Coverage Review Prompt

```markdown
Here are my current test cases for [component]:

[List or paste your test cases]

Please review and identify gaps:
1. **Missing scenarios**: What situations haven't I tested?
2. **Insufficient coverage**: Where do I need more test cases?
3. **Redundant tests**: Are any tests overlapping unnecessarily?
4. **Assertions**: Are my assertions specific and complete enough?
5. **Test independence**: Do tests properly isolate the component?

Domain: [field/application]
Suggest additional test cases to improve coverage.
```

---

## Error Handling Test Design Prompt

```markdown
For [function/component], help me design tests for error handling.

Function: [signature/description]
Potential errors I anticipate:
- [Error type 1]: [when it occurs]
- [Error type 2]: [when it occurs]

Help me specify:
1. **What errors should be raised**: For which invalid inputs?
2. **Error types**: What exception classes are appropriate?
3. **Error messages**: What information should messages contain?
4. **Test structure**: How to test exceptions properly?
5. **Recovery**: Should any errors be recoverable? How?

Additional error conditions in [domain] I should test for [operation]?
```

---

## Performance Test Design Prompt

```markdown
For [component] that [description], help me design performance tests.

Performance requirements:
- [Requirement 1 - e.g., "process 10K items in <1 second"]
- [Requirement 2 - e.g., "memory usage <100MB for 1M items"]
- [Requirement 3 - e.g., "scales linearly with input size"]

Help me design tests for:
1. **Timing tests**: What input sizes should I test? What's acceptable range?
2. **Memory tests**: How to measure memory usage? What's the threshold?
3. **Scalability tests**: How to verify scaling behavior?
4. **Stress tests**: At what point should it fail gracefully?
5. **Benchmarking**: What metrics should I track?

Input characteristics: [typical data size/properties]
Running environment: [hardware/platform considerations]
```

---

## Test Data Design Prompt

```markdown
For testing [function/component], help me design appropriate test data.

What the component does: [description]
Current test approach: [if you have one]

Help me design:
1. **Synthetic data**: What controlled test cases should I create?
   - Simple cases with known outputs
   - Edge cases with predictable behavior
   - How to generate programmatically?

2. **Realistic data**: What realistic scenarios should I test?
   - Typical real-world inputs
   - Representative edge cases from actual use
   - How to create or obtain?

3. **Fixture organization**: How to structure test data?
   - Reusable fixtures vs. one-off test data
   - Setup and teardown needs
   - File-based test data vs. generated

Domain: [field] - what kinds of test data are standard in this field?
```

---

## Test Infrastructure Prompt

```markdown
I'm setting up testing infrastructure for [project type].

Current setup:
- Language/framework: [e.g., "Python with pytest"]
- Project structure: [brief description]
- Existing tests: [what you have if any]

Help me design:
1. **Test organization**: How should tests be structured?
   - Directory structure
   - File naming conventions
   - Grouping related tests

2. **Test fixtures**: What reusable setup do I need?
   - Common test data
   - Mock objects
   - Configuration

3. **Test utilities**: What helper functions would be useful?
   - Custom assertions
   - Test data generators
   - Comparison functions

4. **Automation**: What should be automated?
   - Running tests on commit/push
   - Coverage reporting
   - Performance regression detection

What testing patterns are standard for [project type] in [language]?
```

---

## Assertion Design Prompt

```markdown
For this test case: [describe test scenario]

Help me write precise assertions:
1. **What to check**: What aspects of the output matter?
   - Exact values vs. approximate?
   - Structure/shape/type?
   - Specific properties or invariants?

2. **How to check it**: What assertions are appropriate?
   - Equality, inequality, containment?
   - Numeric tolerance for floating point?
   - Type checking?

3. **Assertion messages**: What should failure messages include?
   - What context helps debug failures?

4. **Completeness**: Am I checking enough?
   - What could pass this assertion but still be wrong?

Output type: [e.g., "numpy array", "dict of lists", "custom class"]
Domain: [field - any domain-specific validation?]
```

---

## Quick Tips

- **Write tests before implementation** - they clarify requirements
- **Be specific about expected behavior** - "raises ValueError" not just "handles errors"
- **Include edge cases early** - they often reveal design issues
- **Think about failure modes** - what could go wrong?
- **Test at the right level** - unit tests for components, integration tests for interactions
- **Make tests reproducible** - avoid randomness unless testing random behavior
- **Ask AI to identify gaps** - it's good at finding cases you missed

---

## Example (Geophysics Context)

```markdown
For a function that computes semblance on seismic gathers, help me design comprehensive test cases.

Functionality:
- Inputs: 3D array (traces, samples, offsets), velocity to test, time window length
- Processing: Computes semblance (coherence measure) along moveout curve
- Outputs: 1D array of semblance values per time sample
- Edge cases I've identified: Empty gather, single trace, constant traces

Please generate test scenarios for:
1. **Happy path**: Normal gather with clear event
2. **Boundary conditions**: Single trace, two traces, very wide offset range
3. **Invalid inputs**: Wrong shape array, negative velocity, zero window
4. **Edge cases**: All-zero traces, NaN values, identical traces, no moveout
5. **Domain-specific cases**: Flat event (zero moveout), curved event, crossing events, muted traces

For each test case, specify:
- Concrete input arrays (or how to generate them)
- Expected semblance values or properties (high/low/specific value)
- Rationale (e.g., "flat event should give semblance=1.0")

What semblance-specific test cases am I missing? Consider numerical stability, velocity extremes, window edge effects.
```
