# Debugging Prompt Template

Use this template to get AI assistance with debugging issues (Rule 8).

---

## Bug Investigation Prompt

```
I'm encountering a bug in [component]:

**Expected behavior:**
[What should happen]

**Actual behavior:**
[What's actually happening]

**Code:**
[Paste relevant code]

**Error message (if any):**
[Paste full error message and stack trace]

**Test case that reproduces it:**
[Minimal example that triggers the bug]

**What I've tried:**
- [Attempt 1]
- [Attempt 2]

Help me:
1. Identify the root cause
2. Explain why it's happening
3. Suggest a fix
4. Propose a test to prevent regression
```

---

## Unexpected Output Investigation Prompt

```
My code runs without errors but produces incorrect output:

**Function:**
[Paste code]

**Test case:**
Input: [specific input]
Expected output: [what you expect]
Actual output: [what you get]

**Analysis so far:**
- [What you've checked]
- [What you suspect]

Help me:
1. Trace through the logic to find where it diverges
2. Identify the bug
3. Explain why the current code produces this output
4. Suggest the fix

Domain context: [field] - is the output physically/scientifically plausible?
```

---

## Intermittent Bug Investigation Prompt

```
I have a bug that only occurs sometimes:

**Bug description:**
[What goes wrong]

**Frequency:**
[How often it occurs - e.g., "1 in 10 runs", "only with large inputs"]

**Code:**
[Paste code]

**Patterns I've noticed:**
- [When it occurs]
- [When it doesn't occur]
- [Any correlations]

**Environment:**
- Platform: [OS, versions]
- Dependencies: [relevant library versions]

Help me:
1. Identify potential sources of non-determinism
2. Suggest ways to make the bug reproducible
3. Propose debugging strategies
4. Identify the root cause if possible
```

---

## Performance Bug Investigation Prompt

```
This code is unexpectedly slow:

**Code:**
[Paste code]

**Performance issue:**
- Expected: [what you expected]
- Actual: [what you observe]
- Input size: [characteristics]

**Profiling data (if any):**
[Paste profiling results]

**What I've checked:**
- [What you've investigated]

Help me:
1. Identify the performance bottleneck
2. Explain why it's slow
3. Suggest optimizations
4. Estimate expected improvement

Is this algorithmic complexity or implementation issue?
```

---

## Integration Bug Investigation Prompt

```
Component A and Component B don't work together properly:

**Component A:**
[Description or code]
Output: [what it produces]

**Component B:**
[Description or code]
Expects: [what it expects as input]

**Error/Issue:**
[What goes wrong when you connect them]

**Integration code:**
[How you're connecting them]

Help me:
1. Identify the incompatibility
2. Determine which component should change
3. Suggest how to fix the integration
4. Propose validation to ensure they stay compatible
```

---

## Silent Failure Investigation Prompt

```
My code fails silently - no errors but doesn't work:

**Code:**
[Paste code]

**Expected:** [what should happen]
**Actual:** [nothing happens / wrong behavior]
**No errors or exceptions**

**Debugging attempted:**
- [What you've checked]
- [Print statements / logging output]

Help me:
1. Identify where execution is failing or deviating
2. Explain why no error is raised
3. Suggest where to add assertions or validation
4. Propose defensive programming improvements

Where should I add checks to catch this failure earlier?
```

---

## Type Error Investigation Prompt

```
I'm getting type-related errors:

**Error message:**
[Paste full error]

**Code:**
[Paste code]

**What I expect:**
- [Variable X should be type Y]
- [Function should accept type Z]

**What's happening:**
- [Actual types involved]

Help me:
1. Trace where the wrong type is introduced
2. Explain the type mismatch
3. Suggest the fix
4. Recommend type hints to prevent this

Should I convert types or change the function signature?
```

---

## Logic Error Investigation Prompt

```
The logic in this code isn't doing what I intended:

**Code:**
[Paste code]

**Intent:** [what you meant to implement]
**What it actually does:** [what it's doing]

**Specific example:**
Input: [example]
Expected: [what should happen]
Actual: [what happens]

Help me:
1. Identify where the logic is wrong
2. Explain the error in my reasoning
3. Show the correct logic
4. Suggest how to test the corrected version

Walk through the logic step-by-step.
```

---

## State Management Bug Prompt

```
Something about state is going wrong:

**Code:**
[Paste code]

**Problem:**
[Describe state-related issue - e.g., "state not updating", "state persisting incorrectly"]

**Sequence that triggers it:**
1. [Step 1]
2. [Step 2]
3. [Step 3 - bug occurs]

**State before/after:**
Before step 3: [state values]
After step 3: [state values]
Expected after step 3: [what state should be]

Help me:
1. Trace how state changes through the sequence
2. Identify where state management goes wrong
3. Suggest the fix
4. Recommend better state management approach if needed
```

---

## Exception Handling Bug Prompt

```
Exceptions aren't being handled correctly:

**Code:**
[Paste code with error handling]

**Problem:**
[What's wrong - e.g., "wrong exception caught", "error swallowed", "wrong recovery"]

**Test case:**
[Input that triggers the issue]

**Current behavior:**
[What happens with exceptions]

**Desired behavior:**
[How exceptions should be handled]

Help me:
1. Identify the error handling problem
2. Explain what's being caught/missed
3. Suggest correct exception handling
4. Recommend testing strategy for error paths
```

---

## Numerical Accuracy Bug Prompt

```
I'm getting numerical accuracy issues:

**Code:**
[Paste code]

**Problem:**
- Expected result: [value]
- Actual result: [value]
- Difference: [magnitude of error]

**Input:** [values involved]
**Operations:** [what computations are done]

**Context:**
- Working with: [data type, precision]
- Domain: [field] - is this error acceptable?

Help me:
1. Identify source of numerical error
2. Is this accumulation, cancellation, or overflow?
3. Suggest numerical fixes (reordering, higher precision, algorithms)
4. Recommend validation strategy

Is this a precision issue or algorithm issue?
```

---

## Concurrency Bug Investigation Prompt

```
I think I have a race condition or concurrency issue:

**Code:**
[Paste code]

**Concurrency setup:**
[How parallelism is implemented]

**Bug symptoms:**
[What goes wrong]

**Frequency:**
[How reliably it reproduces]

**Shared resources:**
[What's accessed by multiple threads/processes]

Help me:
1. Identify potential race conditions
2. Locate unsynchronized access to shared state
3. Suggest synchronization strategy
4. Recommend testing approach for concurrency bugs

What's the safe concurrency pattern for this use case?
```

---

## Quick Tips

- **Provide full error messages** - including stack traces
- **Show minimal reproducible example** - strip down to essentials
- **Include what you've tried** - helps AI avoid suggesting same things
- **State your hypothesis** - if you have suspicions, share them
- **Show context** - related code that might be relevant
- **Include test data** - actual values that trigger the bug
- **Ask for explanation** - understand why, not just how to fix

---

## Example (Geophysics Context)

```
I'm encountering a bug in my NMO correction function:

**Expected behavior:**
Apply moveout correction using t' = sqrt(t² + x²/v²), flatten events in gather

**Actual behavior:**
Some traces show discontinuities and artifacts after correction, especially at near offsets

**Code:**
```python
def apply_nmo(gather, velocity, dt, offsets):
    """Apply NMO correction."""
    corrected = np.zeros_like(gather)
    n_traces, n_samples = gather.shape
    
    for i, offset in enumerate(offsets):
        for t_idx in range(n_samples):
            t0 = t_idx * dt
            t_nmo = np.sqrt(t0**2 + offset**2 / velocity**2)
            t_nmo_idx = int(t_nmo / dt)
            
            if t_nmo_idx < n_samples:
                corrected[i, t_idx] = gather[i, t_nmo_idx]
    
    return corrected
```

**Error message (if any):**
No error, but output shows jagged/discontinuous events

**Test case that reproduces it:**
- Synthetic gather: 24 traces, flat event at t=0.5s
- Offsets: 0 to 575m in 25m steps
- Velocity: 2000 m/s
- dt: 0.004s
- Result: Event appears jagged after correction

**What I've tried:**
- Checked that velocity units are consistent (m/s)
- Verified offsets array is correct
- Printed intermediate t_nmo values - they look reasonable

Help me:
1. Why are traces showing discontinuities?
2. Is the NMO formula implemented correctly?
3. Is integer indexing causing the problem?
4. Should I be interpolating rather than nearest-neighbor sampling?

Domain: Seismic processing - NMO correction should produce smooth horizontally-aligned events.
```
