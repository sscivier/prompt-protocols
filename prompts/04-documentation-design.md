# Documentation Design Prompt Template

Use this template to get AI assistance with designing documentation structure and content (Rules 1, 4, 5).

---

## Documentation Strategy Prompt

```markdown
I'm planning documentation for [project/package].

Project overview:
- Purpose: [what it does]
- Audience: [who will use it - expertise level]
- Scope: [small script, package, large application]
- Distribution: [internal, open-source, published]

Help me plan documentation strategy:
1. **Documentation types needed**: README? API docs? Tutorials? Theory docs?
2. **Priority order**: What to document first?
3. **Documentation tools**: What tools/frameworks to use?
4. **Maintenance approach**: How to keep docs updated?
5. **Examples and tutorials**: What examples are essential?

Context:
- Similar projects: [projects with good docs to emulate]
- Time constraints: [how much effort can go into docs]
- User needs: [what users will need to know]

What documentation is essential vs. nice-to-have for [project type]?
```

---

## README Design Prompt

```markdown
I'm writing a README for [project].

Project details:
- What it does: [brief description]
- Key features: [main capabilities]
- Target users: [who will use this]
- Current status: [development stage]

Help me design the README structure:
1. **Essential sections**: What must be included?
2. **Section ordering**: What order makes sense?
3. **Content depth**: How detailed should each section be?
4. **Code examples**: What examples to include?
5. **Visual elements**: Badges? Diagrams? Screenshots?

Specific questions:
- Should I include theory/background or keep it purely practical?
- How much installation detail?
- Quick start vs. detailed tutorials?

Design a README that helps users quickly understand and use the project.
```

---

## API Documentation Design Prompt

```markdown
I'm documenting the API for [package/module].

API overview:
- Public functions: [list main functions]
- Key classes: [list main classes]
- Main use cases: [how users will interact]

Help me design API documentation:
1. **Documentation style**: [Docstring format - Google, NumPy, Sphinx?]
2. **What to document**: Parameters, returns, examples, theory?
3. **Level of detail**: How thorough should docstrings be?
4. **Examples in docs**: Standalone examples vs. inline?
5. **Organization**: How to structure API reference?
6. **Auto-generation**: Tools to generate docs from docstrings?

Domain: [field] - any domain-specific documentation conventions?

Example function that needs documentation:
[Paste function signature or description]

Show me what good API documentation looks like for this.
```

---

## Tutorial/Guide Content Planning Prompt

```markdown
I need to create tutorials/guides for [project].

What users need to learn:
- [Concept/task 1]
- [Concept/task 2]
- [Concept/task 3]

User background: [what they know, what they don't]

Help me plan tutorial content:
1. **Tutorial structure**: What tutorials are needed?
2. **Learning path**: What order should tutorials follow?
3. **Tutorial length**: How long/detailed should each be?
4. **Running examples**: What dataset/examples to use throughout?
5. **Incremental complexity**: How to build from simple to complex?

Specific tutorials I'm considering:
- [Tutorial idea 1]
- [Tutorial idea 2]

Are these the right tutorials? What am I missing?

Design a tutorial series that brings users from beginner to proficient.
```

---

## Scientific Documentation Design Prompt

```markdown
I'm documenting scientific software for [project].

Scientific context:
- Methods implemented: [algorithms, approaches]
- Domain: [scientific field]
- Target audience: [researchers, students, practitioners]

Help me design scientific documentation:
1. **Theory documentation**: How much mathematical detail?
2. **Method descriptions**: How to explain algorithms?
3. **Citations**: Where and how to cite papers?
4. **Validation**: How to document correctness/validation?
5. **Limitations**: How to document assumptions and limitations?
6. **Reproducibility**: What to include for reproducibility?

Specific challenges:
- [Challenge 1 - e.g., "complex math notation"]
- [Challenge 2 - e.g., "multiple algorithm variants"]

References:
- Key papers: [papers to cite]
- Similar software: [examples of well-documented scientific software]

Design documentation that meets scientific standards while remaining accessible.
```

---

## Documentation Site Structure Prompt

```markdown
I'm creating a documentation website for [project] using [tool - e.g., Sphinx, MkDocs, etc.].

Project scale: [size and complexity]
Documentation types: [API docs, tutorials, theory, etc.]

Help me design the site structure:
1. **Navigation**: How to organize the menu/sidebar?
2. **Page hierarchy**: What pages/sections at what levels?
3. **Landing page**: What should the homepage contain?
4. **Search/discovery**: How users find information?
5. **Cross-referencing**: How to link related content?

Content I have:
- [Content type 1 and amount]
- [Content type 2 and amount]

User journeys:
- [Journey 1 - e.g., "new user needs quick start"]
- [Journey 2 - e.g., "experienced user needs API reference"]

Design a site structure that serves different user needs.
```

---

## Example Documentation Planning Prompt

```markdown
I need to plan examples and code samples for [project].

Project: [description]
Main use cases:
- [Use case 1]
- [Use case 2]
- [Use case 3]

Help me plan examples:
1. **Example types**: Minimal examples? Real-world examples? Gallery?
2. **Example topics**: What scenarios to cover?
3. **Example complexity**: Range from simple to complex?
4. **Example organization**: Where do examples live?
5. **Running examples**: Jupyter notebooks? Scripts? Both?
6. **Example data**: What data to use? How to distribute?

What I want users to learn from examples:
- [Learning goal 1]
- [Learning goal 2]

Design an example set that demonstrates key functionality effectively.
```

---

## Docstring Standards Prompt

```markdown
I need consistent docstring standards for [project].

Project context:
- Language: [language]
- Domain: [field]
- Documentation tool: [if using auto-doc generation]

Help me establish docstring standards:
1. **Format choice**: Google? NumPy? Sphinx? Other?
2. **Required elements**: What must every docstring include?
3. **Optional elements**: What to include when relevant?
4. **Examples**: Should all functions have examples?
5. **Types**: Type hints? Type descriptions? Both?
6. **Theory/math**: How to include equations and theory?

Specific to my domain ([field]):
- What domain-specific information to document?
- Standard ways to document [domain concept]?

Example function types in my project:
- [Type 1 - e.g., "data processing functions"]
- [Type 2 - e.g., "plotting/visualization functions"]

Show me docstring templates for each function type.
```

---

## Inline Comment Strategy Prompt

```markdown
I need a strategy for inline comments in [project].

Current situation:
- [Issue - e.g., "too many comments", "too few", "inconsistent"]

Code characteristics:
- Complexity: [simple, moderate, complex]
- Domain: [field - how specialized?]
- Audience: [who will read the code]

Help me develop a comment strategy:
1. **What to comment**: When is a comment necessary?
2. **What not to comment**: What's obvious from code?
3. **Comment style**: Format and conventions?
4. **Domain explanation**: When to explain domain concepts?
5. **TODOs and FIXMEs**: How to use them?
6. **Comment maintenance**: How to keep comments current?

Specific question: 
- Scientific code often has complex math - how much to explain in comments vs. docstrings vs. separate docs?

Design a comment strategy that adds value without clutter.
```

---

## Documentation Maintenance Strategy Prompt

```markdown
I need a strategy to keep documentation updated as [project] evolves.

Current challenges:
- [Challenge 1 - e.g., "docs get out of sync with code"]
- [Challenge 2 - e.g., "too much effort to update docs"]

Project context:
- Development pace: [frequency of changes]
- Team size: [solo, small team, large team]
- Documentation scope: [how much documentation exists]

Help me design a maintenance strategy:
1. **Sync mechanisms**: How to keep docs and code in sync?
2. **Automated checks**: What can be automated? (doctest, link checking, etc.)
3. **Update triggers**: When should docs be updated?
4. **Review process**: Who reviews documentation changes?
5. **Version management**: How to document different versions?
6. **Deprecation**: How to document deprecated features?

Tools available: [CI/CD, doc generation tools, etc.]

Design a sustainable documentation maintenance approach.
```

---

## Contributing Documentation Prompt

```markdown
I want to create contributor documentation for [project].

Project context:
- Type: [open-source, internal, research]
- Seeking: [what kind of contributions]
- Current contributors: [just me, small team, community]

Help me design contributor docs:
1. **CONTRIBUTING file**: What to include?
2. **Development setup**: How much detail on environment setup?
3. **Code standards**: What standards to document?
4. **Contribution workflow**: PR process? Review process?
5. **Testing requirements**: What testing is expected?
6. **Documentation requirements**: When to update docs?

Specific questions:
- How to make contributing approachable for [target contributor profile]?
- What barriers to contribution should I address?

Design contributor documentation that welcomes and guides contributors.
```

---

## Documentation Review Prompt

```markdown
Please review my documentation plan/content:

[Paste documentation outline or content]

Project: [description]
Audience: [target users]
Purpose: [what documentation should achieve]

Review for:
1. **Completeness**: What's missing?
2. **Organization**: Does structure make sense?
3. **Clarity**: Is it clear and understandable?
4. **Accessibility**: Can target audience understand it?
5. **Examples**: Are examples sufficient and clear?
6. **Discoverability**: Can users find what they need?

Domain: [field] - any domain-specific issues?

Suggest improvements and identify gaps.
```

---

## Quick Tips

- **Write for your audience** - match their expertise level
- **Show, don't just tell** - examples are crucial
- **Start with README** - most users start here
- **Keep docs close to code** - easier to maintain
- **Test documentation** - run code examples to ensure they work
- **Use consistent terminology** - define terms once, use them consistently
- **Update docs with code** - treat docs as part of the feature
- **Get feedback** - have others read your docs

---

## Example (Geophysics Context)

```markdown
I'm planning documentation for a seismic data processing package.

Project overview:
- Purpose: Load, process, and visualize seismic data (shot gathers, velocity analysis, stacking)
- Audience: Geophysics grad students and researchers, some experienced programmers, some not
- Scope: Python package with ~10 modules, CLI tools, interactive workflow
- Distribution: Open-source on GitHub, possibly publish on PyPI

Help me plan documentation strategy:
1. **Documentation types needed**: README? API docs? Tutorials? Theory docs?
   - Users need to understand both the code AND the seismic processing theory
   - Some users may know theory but not programming
   - Some may know programming but not seismic processing
   
2. **Priority order**: What to document first?
   - Quick start for common workflow?
   - Theory background for algorithms?
   - Complete API reference?
   
3. **Documentation tools**: Sphinx with Napoleon? MkDocs? readthedocs hosting?

4. **Maintenance approach**: How to keep docs updated as processing methods evolve?

5. **Examples**: Need examples with real seismic data - how to distribute? Synthetic data?

Context:
- Similar projects: ObsPy has excellent docs (Sphinx), Madagascar has detailed but dense docs
- Time constraints: Solo developer, want docs that are maintainable
- User needs: Need to understand WHAT each processing step does physically/geologically, not just how to call functions

Specific questions:
- Should I separate theory docs from usage docs?
- How to document algorithms: just cite papers, or explain the math?
- Velocity analysis has complex math - where does that explanation go?

What documentation is essential vs. nice-to-have for scientific software like this?
```
