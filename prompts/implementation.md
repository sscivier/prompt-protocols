# AI Coding Implementation Prompt Template

Use this template to structure your implementation requests to AI coding assistants. Fill in each section thoughtfully to ensure your prompt aligns with best practices and passes quality assessment.

---

## 1. Domain Context & Current Understanding

**What I know about this problem:**
- [Describe your current understanding of the domain/problem]
- [List relevant libraries, tools, or standards you're aware of]
- [Reference any existing implementations or approaches you've researched]

**What I'm uncertain about:**
- [Identify specific knowledge gaps]
- [List areas where you need guidance on best practices]

**Data characteristics:**
- Input types/shapes: [e.g., "pandas DataFrame with columns X, Y, Z; ~10K rows"]
- Expected output: [e.g., "dictionary mapping IDs to normalized scores"]
- Edge cases: [e.g., "missing values in column Y, duplicate IDs possible"]
- Constraints: [e.g., "must handle datasets up to 1M rows; memory < 2GB"]

---

## 2. Problem Statement (High-Level)

**What needs to be solved (not how):**

[Describe the problem conceptually, independent of implementation details. What are you trying to accomplish algorithmically?]

**Key steps in the solution approach:**
1. [Step 1 - conceptual]
2. [Step 2 - conceptual]
3. [Step 3 - conceptual]

**Architectural decisions:**
- Data structures: [e.g., "use hash map for O(1) lookups"]
- Algorithms: [e.g., "streaming processing to handle large files"]
- Design patterns: [e.g., "factory pattern for different data source types"]

---

## 3. Solution Plan & Requirements

**Inputs:**
- Parameter 1: [type, constraints, example value]
- Parameter 2: [type, constraints, example value]

**Outputs:**
- [Describe expected output format, structure, and validation criteria]

**Success criteria:**
- [What does successful execution look like?]
- [Performance requirements: speed, memory, accuracy]

**Integration context:**
- Existing codebase: [e.g., "fits into module X, uses interface Y"]
- Dependencies: [list libraries/versions, e.g., "pandas>=2.0, numpy>=1.24"]
- Interfaces to maintain: [e.g., "must accept same signature as existing function Z"]

---

## 4. Test Specifications

**Required test cases:**
1. **Happy path:** [Describe expected normal operation with sample input/output]
2. **Edge case 1:** [e.g., "empty input" - expected behavior]
3. **Edge case 2:** [e.g., "extremely large values" - expected behavior]
4. **Error condition:** [e.g., "invalid type" - should raise TypeError with message X]

**Acceptance criteria (as assertions):**
```python
# Example format - adapt to your language
assert function(valid_input) == expected_output
assert function(edge_case) handles correctly
assert function(invalid_input) raises ExpectedError
```

**Additional validation:**
- [What scenarios might I be missing? Ask AI to identify gaps]

---

## 5. Implementation Request

**Specific task:**

[Be explicit about what you want implemented. Reference the sections above.]

"Based on the context, problem statement, and test specifications above, please implement [specific function/class/module]. Start by generating the test suite that validates the requirements, then implement the solution."

**Scope constraints:**
- [What should NOT be changed: e.g., "don't modify the database schema"]
- [Preferred patterns: e.g., "use functional approach, avoid classes"]
- [Code style: e.g., "follow PEP 8, use type hints"]

**Verification approach:**
- [How will you verify correctness: e.g., "run tests against sample dataset X"]
- [What manual checks will you perform: e.g., "inspect outputs for scientific plausibility"]

---

## 6. Context Files (Attach/Reference)

- [ ] Relevant existing code files
- [ ] Project documentation (README, API docs)
- [ ] Data samples or schemas
- [ ] Configuration files showing dependencies
- [ ] Related test files

---

## Template Usage Tips

1. **Don't skip sections.** Each addresses a specific rule from the ten simple rules framework.

2. **Be specific.** "Handle errors" → "Raise ValueError with descriptive message when input contains negative values"

3. **Tests first.** Specify tests before implementation to clarify requirements and guide AI output.

4. **Iterate on context.** If AI outputs don't match expectations, revisit sections 1-3 to add missing details.

5. **One focus at a time.** Don't bundle "implement feature X" with "refactor module Y" in one prompt.

6. **Restate context.** In follow-up prompts, briefly restate critical requirements rather than assuming AI remembers perfectly.

---

## Example Minimal Prompt (Filled Template)

```markdown
## 1. Domain Context & Current Understanding

**What I know:**
- Working with neuroimaging data (fMRI time series)
- Standard format is 4D numpy arrays (x, y, z, time)
- Need to compute correlation matrices between voxel time series
- Standard library is nilearn, but exploring custom implementation for specific preprocessing

**What I'm uncertain about:**
- Best approach for memory-efficient computation with large arrays
- Whether to use Fisher z-transformation before or after correlation

**Data characteristics:**
- Input: 4D numpy array, shape (64, 64, 30, 200) - spatial dims + time
- Output: correlation matrix (n_voxels × n_voxels) as 2D numpy array
- Edge cases: constant time series (zero variance), NaN values in data
- Constraints: memory efficient for up to 100k voxels

## 2. Problem Statement

Extract time series from 4D array, compute pairwise correlations efficiently, handle edge cases where voxels have zero variance or missing data.

**Solution approach:**
1. Reshape 4D to 2D (voxels × time)
2. Compute correlation using numpy's corrcoef or custom implementation
3. Handle invalid correlations (NaN from zero-variance voxels)
4. Return symmetric correlation matrix

## 3. Solution Plan & Requirements

**Inputs:**
- fmri_data: numpy array, shape (x, y, z, t), dtype float32
- mask: optional boolean array, shape (x, y, z), to select voxels

**Outputs:**
- correlation_matrix: numpy array, shape (n_voxels, n_voxels), dtype float32
- Range [-1, 1], symmetric, diagonal = 1.0

**Success criteria:**
- Handles 100k voxels without memory errors
- Results match scipy.stats.pearsonr for sample pairs
- NaN voxels produce NaN correlations, not crashes

**Integration:**
- Part of preprocessing pipeline module
- Dependencies: numpy>=1.24, scipy>=1.10
- Should match signature of existing `compute_connectivity()` function

## 4. Test Specifications

1. **Happy path:** 4D array with known correlations → correct matrix
2. **Zero variance voxel:** Include constant time series → NaN in output
3. **NaN values:** Include masked/missing data → propagate NaN correctly
4. **Memory test:** Large array (100k voxels) → completes without error
5. **Symmetry:** Output matrix is symmetric and diagonal is all 1.0

```python
def test_known_correlations():
    # Two voxels with perfect positive correlation
    data = create_test_4d_array()  # specific test case
    corr = compute_voxel_correlations(data)
    assert np.isclose(corr[0, 1], 1.0)
    
def test_zero_variance():
    # Include constant time series
    data = create_test_with_constant_voxel()
    corr = compute_voxel_correlations(data)
    assert np.isnan(corr[0, 1])  # where voxel 1 is constant
```

## 5. Implementation Request

Please implement `compute_voxel_correlations(fmri_data, mask=None)` based on the specifications above. First generate a comprehensive test suite covering all specified cases, then implement the function. Use memory-efficient approaches for large arrays (consider chunking if needed). Include docstring with parameter descriptions and examples.

**Scope constraints:**
- Don't modify existing preprocessing functions
- Use numpy/scipy only (no custom C extensions)
- Include type hints (numpy typing)

**Verification:**
- I'll run tests against synthetic data with known correlations
- Will validate on real fMRI dataset (100 subjects) for memory/performance
```

---

## Quick Self-Check Before Submitting

- [ ] Have I provided sufficient domain context and data characteristics?
- [ ] Have I described WHAT to solve, not just HOW to code it?
- [ ] Have I specified clear inputs, outputs, and success criteria?
- [ ] Have I included concrete test cases with expected behavior?
- [ ] Have I explained how this fits into my larger project?
- [ ] Have I attached/referenced relevant existing code and documentation?
- [ ] Is my request focused on ONE clear objective (not multiple features)?

If any checkbox is unchecked, revisit that section of the template before submitting your prompt.
