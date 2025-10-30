# Prompt Development Templates

This directory contains focused templates to help you use AI assistance effectively at each stage of developing an implementation prompt. Each template addresses specific rules from the [Ten Simple Rules for AI-Assisted Coding](../ten-simple-rules-reference.md).

---

## Template Overview

### Preparation & Research
- **[01-domain-research.md](01-domain-research.md)** - Gather domain knowledge before implementation (Rule 1)
- **[02-problem-framing.md](02-problem-framing.md)** - Frame problems programmatically and design solutions (Rules 2, 4)

### Specification & Design
- **[03-solution-specification.md](03-solution-specification.md)** - Specify inputs, outputs, and requirements (Rule 3)
- **[04-test-design.md](04-test-design.md)** - Design comprehensive test cases (Rules 6, 7)
- **[05-context-management.md](05-context-management.md)** - Manage context effectively (Rule 5)

### Implementation & Quality
- **[06-code-review.md](06-code-review.md)** - Review generated code critically (Rule 9)
- **[07-code-refinement.md](07-code-refinement.md)** - Refine code incrementally (Rule 10)
- **[08-debugging.md](08-debugging.md)** - Debug issues systematically (Rule 8)

### Final Implementation
- **[implementation.md](implementation.md)** - Complete template for final implementation prompts

---

## How to Use These Templates

### 1. Start with Research & Framing
Before jumping into code, use these templates to build understanding:
```
01-domain-research.md → Learn domain standards, tools, approaches
02-problem-framing.md → Decompose problem, design architecture
```

### 2. Specify Solution Requirements
Clarify exactly what you need before implementation:
```
03-solution-specification.md → Define inputs, outputs, constraints
04-test-design.md → Design test cases that define success
05-context-management.md → Organize information for AI sessions
```

### 3. Implement with Monitoring
Use the final template and monitor progress:
```
implementation.md → Create comprehensive implementation prompt
(Monitor as AI implements, use debugging template if issues arise)
```

### 4. Review & Refine
Ensure quality through systematic review:
```
06-code-review.md → Review generated code critically
07-code-refinement.md → Incrementally improve working code
08-debugging.md → Systematically resolve any issues
```

---

## Quick Start Guide

### For New Projects
1. **Research** (01-domain-research.md): Understand the domain
2. **Frame** (02-problem-framing.md): Break down the problem
3. **Specify** (03-solution-specification.md): Define requirements
4. **Test Design** (04-test-design.md): Define success criteria
5. **Implement** (implementation.md): Create full implementation prompt

### For Existing Code
1. **Review** (06-code-review.md): Assess current implementation
2. **Refine** (07-code-refinement.md): Improve specific aspects
3. **Debug** (08-debugging.md): Resolve any issues

### For Context Management
- **Starting a session**: Use 05-context-management.md to create context docs
- **Long sessions**: Use pruning prompts to restart effectively
- **Handoffs**: Use context handoff prompts for transitions

---

## Template Philosophy

Each template follows these principles:

### Concise & Digestible
- Clear structure with specific prompt formats
- Quick tips for effective use
- No unnecessary verbosity

### Flexible
- Adaptable to different problems and situations
- Multiple variants for different needs
- Customizable to your context

### AI-Focused
- Designed to help AI help you develop components
- Structured to get actionable responses
- Guides AI toward useful outputs

### Domain-Aware
- Space for domain-specific context
- Examples from geophysics/scientific computing
- Emphasis on scientific correctness

---

## Tips for Best Results

### Be Specific
Replace placeholders with concrete details:
- ❌ "my project"
- ✅ "seismic data processing pipeline for velocity analysis"

### Provide Context
Always include:
- What domain you're working in
- What you already know/understand
- What constraints you have
- How this fits into the bigger picture

### Iterate
Don't expect perfect results first try:
1. Use template to get initial response
2. Refine your prompt based on response
3. Follow up with targeted questions
4. Build understanding incrementally

### Combine Templates
Templates work together:
- Use research to inform problem framing
- Use problem framing to guide specification
- Use specification to drive test design
- Use all of the above to create implementation prompt

---

## Examples

Each template includes:
- **Generic prompt formats** - adaptable to any situation
- **Domain-specific example** - typically from geophysics/scientific computing
- **Quick tips** - common pitfalls and best practices

The examples demonstrate how to fill in templates for real-world scenarios in computational geophysics, but the templates themselves are field-agnostic.

---

## Relationship to Ten Simple Rules

| Rule | Primary Templates | Secondary Templates |
|------|-------------------|---------------------|
| Rule 1: Gather Domain Knowledge | 01-domain-research | 02-problem-framing |
| Rule 2: Distinguish Problem from Coding | 02-problem-framing | 03-solution-specification |
| Rule 3: Choose Appropriate AI Tools | *(tool selection guidance)* | 05-context-management |
| Rule 4: Think Through Solutions | 02-problem-framing | 03-solution-specification |
| Rule 5: Manage Context | 05-context-management | all templates |
| Rule 6: Test-Driven Development | 04-test-design | implementation |
| Rule 7: Leverage AI for Testing | 04-test-design | 06-code-review |
| Rule 8: Monitor Progress | 08-debugging | 05-context-management |
| Rule 9: Review Code Critically | 06-code-review | 04-test-design |
| Rule 10: Refine Incrementally | 07-code-refinement | 06-code-review |

---

## Getting Help

If you're unsure which template to use:

**"I need to understand X better"** → 01-domain-research.md

**"I need to design how to solve Y"** → 02-problem-framing.md

**"I need to specify what I want built"** → 03-solution-specification.md

**"I need to define success criteria"** → 04-test-design.md

**"I'm managing long AI sessions"** → 05-context-management.md

**"I need to review generated code"** → 06-code-review.md

**"I need to improve working code"** → 07-code-refinement.md

**"Something's not working right"** → 08-debugging.md

**"I'm ready to implement"** → implementation.md
