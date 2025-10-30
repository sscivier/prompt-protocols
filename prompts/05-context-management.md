# Context Management Prompt Template

Use this template to get AI assistance with managing context effectively across sessions (Rule 5).

---

## Context Document Creation Prompt

```
I'm working on [project description] and need to create context documentation for AI coding sessions.

Project overview:
- Purpose: [what the project does]
- Key components: [main modules/systems]
- Tech stack: [languages, frameworks, key libraries]
- Current stage: [where you are in development]

Help me create a context document that includes:
1. **Project architecture**: High-level structure and component relationships
2. **Key decisions**: Important architectural and design choices made
3. **Conventions**: Code style, naming patterns, organization principles
4. **Constraints**: Technical limitations, compatibility requirements
5. **Dependencies**: Critical libraries and their roles

What else should I include to give AI assistants sufficient context across sessions?
```

---

## Context Pruning Prompt

```
My conversation with AI has gotten long and I'm seeing degraded performance.

Current conversation includes:
- [Topic 1]
- [Topic 2]
- [Topic 3]
- [Multiple failed attempts at X]

Help me:
1. **Identify what to preserve**: What context is critical to keep?
2. **Identify what to discard**: What's no longer relevant?
3. **Summarize key decisions**: How to capture important outcomes concisely?
4. **Plan fresh start**: What should go in the new session's opening prompt?

Create a condensed context summary I can use to restart effectively.
```

---

## Problem Tracking Document Prompt

```
I need a structured way to track problems and solutions across AI coding sessions.

Project: [name/description]

Help me design a problem tracking document that captures:
1. **Problem description**: Clear statement of issue
2. **Context**: When/where it occurs, what component
3. **Investigation**: What was tried, what didn't work
4. **Solution**: What worked, why it worked
5. **Prevention**: How to avoid this in future

Suggest a template and format that works well for [project type].
Also suggest what problems I should be tracking vs. ignoring.
```

---

## Session Restart Prompt

```
I'm starting a new AI coding session for [project].

Previous session summary:
- Accomplished: [what was completed]
- Decided: [key decisions made]
- Blocked on: [current issues/questions]
- Next steps: [what needs to happen]

Help me craft an opening prompt for the new session that:
1. Efficiently restates critical context
2. Clearly establishes current state
3. Specifies immediate objectives
4. Avoids reintroducing resolved issues

Generate a structured prompt I can use to start the new session effectively.
```

---

## Specification File Design Prompt

```
For [project/component], help me design external specification files for context management.

What I need to specify:
- [Aspect 1 - e.g., "API interfaces"]
- [Aspect 2 - e.g., "data schemas"]
- [Aspect 3 - e.g., "validation rules"]

Help me design:
1. **File structure**: How to organize specs? (Single file vs. multiple? Format?)
2. **Content organization**: What sections/categories make sense?
3. **Detail level**: How detailed should specs be? What to include/exclude?
4. **Maintenance**: How to keep specs updated as code evolves?
5. **AI consumption**: How to format for optimal AI understanding?

Project type: [description]
Expected use: [how these specs will be used]
```

---

## Context Verification Prompt

```
I'm about to start a complex implementation. Verify I have sufficient context.

What I'm implementing: [description]
What I plan to tell the AI: [your planned prompt]

Review and tell me:
1. **Missing context**: What critical information is absent?
2. **Unclear requirements**: What needs more specificity?
3. **Unstated assumptions**: What am I assuming without stating?
4. **Interface gaps**: What about integration with existing code?
5. **Success criteria**: Are they clear and testable?

Help me identify gaps before I start the implementation.
```

---

## Context Isolation Prompt

```
I need to work on [specific task] without polluting my main development conversation.

Task: [description]
Why isolated: [reason - e.g., "experimental", "tangent", "might fail"]

Help me:
1. **Extract relevant context**: What subset of project context is needed?
2. **Define scope boundary**: What's in/out of scope for this isolated work?
3. **Plan integration**: If successful, how to bring results back?
4. **Handle failure**: If unsuccessful, what to document?

Create a standalone context summary for this isolated work session.
```

---

## Documentation-as-Context Prompt

```
I want to use documentation as persistent context for AI sessions.

Project: [name/description]
Documentation I have: [list what exists]

Help me structure documentation to serve as AI context:
1. **Architecture docs**: What level of detail? What diagrams/descriptions?
2. **API docs**: How much to document? What format works best?
3. **Decision records**: What decisions to capture? How to format them?
4. **Code comments**: What should be in-code vs. external docs?
5. **Examples**: What examples help AI understand usage patterns?

Goal: Enable AI to understand my project from documentation alone.
```

---

## Context Handoff Prompt

```
I'm handing off [project/component] to another developer / future me.

Current state:
- What's completed: [summary]
- Current architecture: [brief description]
- Active problems: [known issues]
- Next priorities: [what should be done next]

Help me create a context handoff document that:
1. Brings someone up to speed quickly
2. Explains why things are the way they are
3. Identifies key things to know before modifying code
4. Points to where things are documented
5. Warns about gotchas and fragile areas

This will be used as context for AI-assisted development by the next person.
```

---

## Quick Tips

- **Create context files early** - easier to maintain than to construct later
- **Keep context focused** - include what's necessary, exclude what's not
- **Update context regularly** - stale context is worse than no context
- **Structure for skimming** - use headers, lists, clear sections
- **Include rationale** - explain why decisions were made
- **Version control context files** - track how understanding evolves
- **Test your context** - start a fresh AI session and see if it's sufficient

---

## Example (Geophysics Context)

```
I'm working on a seismic processing pipeline and need to create context documentation for AI coding sessions.

Project overview:
- Purpose: Process raw seismic data through QC, filtering, NMO correction, stacking
- Key components: Data loader, trace processors (filters, gains), velocity analysis, stacker
- Tech stack: Python 3.11, NumPy, SciPy, Matplotlib, ObsPy for I/O
- Current stage: Core processing modules done, working on velocity analysis optimization

Help me create a context document that includes:
1. **Project architecture**: Pipeline stages, data flow, how processors connect
2. **Key decisions**: 
   - Chose streaming processing (1 trace at a time) for memory efficiency
   - Using SEG-Y format via ObsPy, not custom readers
   - Velocity analysis using semblance (not AB semblance or other variants)
3. **Conventions**: 
   - All traces as NumPy arrays, shape (n_samples,)
   - Time axis always in seconds, not samples
   - Headers as dictionaries, following ObsPy conventions
4. **Constraints**: 
   - Must handle 10GB+ datasets without loading all in memory
   - Processing must be deterministic for reproducibility
   - Support both shot gathers and CMP gathers
5. **Dependencies**: ObsPy 1.4+ (SEG-Y), NumPy 1.24+ (processing), SciPy 1.10+ (filtering)

What else should I include? Consider seismic processing conventions, common gotchas with SEG-Y, trace coordinate systems, velocity units.
```
