# Package Structure Design Prompt Template

Use this template to get AI assistance with designing the overall structure and organization of a code package or module (Rules 2, 4).

---

## Project Structure Design Prompt

```
I'm designing the structure for [project/package name] that will [purpose].

Project scope:
- Main functionality: [what it does]
- Key components: [major pieces - e.g., "data loading, processing, visualization"]
- Expected users: [who will use it - e.g., "researchers in my lab", "public package"]
- Scale: [size - e.g., "single module", "multi-module package", "application"]

Help me design the project structure:
1. **Directory layout**: What folders/files should exist?
2. **Module organization**: How to group related functionality?
3. **Separation of concerns**: What goes where and why?
4. **Entry points**: How will users interact with the code?
5. **Configuration**: Where do settings, constants, configs belong?

Context:
- Language/framework: [e.g., "Python", "Julia", "C++"]
- Similar projects: [examples of well-structured projects in this domain]
- Constraints: [any structural requirements]

What's the standard structure for [project type] in [language]?
```

---

## Module Decomposition Prompt

```
I have [complex functionality] that needs to be organized into modules.

Functionality includes:
- [Feature/capability 1]
- [Feature/capability 2]
- [Feature/capability 3]

Current thinking: [if you have initial ideas]

Help me decompose this into modules:
1. **Module boundaries**: What should each module be responsible for?
2. **Dependencies**: How should modules depend on each other?
3. **Public APIs**: What should each module expose?
4. **Internal organization**: How to structure within modules?
5. **Reusability**: What can be shared across modules?

Constraints:
- [What must stay together]
- [What must be separate]
- [Performance or deployment considerations]

Suggest a modular architecture that's maintainable and extensible.
```

---

## Package Scaffolding Prompt

```
I'm creating a [Python/Julia/R] package for [purpose].

Package details:
- Name: [package name]
- Functionality: [what it does]
- Target audience: [who will use it]
- Distribution: [how it will be shared - e.g., "PyPI", "GitHub only", "internal"]

Help me create the initial scaffolding:
1. **Essential files**: What files are required? (setup.py, __init__.py, etc.)
2. **Directory structure**: Standard layout for [language] packages?
3. **Configuration files**: What configs needed? (pyproject.toml, etc.)
4. **Testing setup**: Where do tests go? What test structure?
5. **Documentation structure**: Where do docs live?
6. **Development files**: .gitignore, requirements, etc.

Language: [specific language and version]
Standards: [any specific standards to follow - e.g., "PEP 517", "SciML style"]

Show me the complete file tree and explain each component.
```

---

## Code Organization Refactoring Prompt

```
My code has grown organically and needs better organization:

Current structure:
[Describe current organization or paste tree]

Problems:
- [Issue 1 - e.g., "everything in one file"]
- [Issue 2 - e.g., "unclear where new code should go"]
- [Issue 3 - e.g., "circular dependencies"]

What the code does:
- [Main functionality areas]

Help me reorganize:
1. **New structure**: What should the organization look like?
2. **Migration path**: How to get from current to new structure?
3. **Dependency fixes**: How to resolve circular dependencies?
4. **Backward compatibility**: How to maintain existing APIs?

Constraints:
- [What can't break]
- [What must be preserved]

Suggest a refactoring plan with clear steps.
```

---

## Interface Design Between Modules Prompt

```
I'm designing interfaces between modules in [project].

Modules:
- **Module A**: [purpose] - produces [output]
- **Module B**: [purpose] - needs [input]
- **Module C**: [purpose] - coordinates [what]

Help me design clean interfaces:
1. **Data contracts**: What data structures should be passed between modules?
2. **API design**: What functions/classes should each module expose?
3. **Dependency direction**: Which modules should depend on which?
4. **Abstraction layers**: Where are abstractions needed?
5. **Extension points**: How to allow future additions?

Principles I want to follow:
- [E.g., "minimize coupling", "dependency inversion", "composition over inheritance"]

Suggest interface designs and explain the architectural decisions.
```

---

## Namespace Design Prompt

```
I'm designing the namespace/API structure for [package].

Package purpose: [what it does]
Main concepts: [key entities/operations - e.g., "models, data, pipelines"]

Help me design the namespace:
1. **Top-level API**: What should users import? (e.g., `import package`)
2. **Submodules**: How should functionality be divided in the namespace?
3. **Import patterns**: What import styles should be supported?
4. **Naming conventions**: How to name modules, classes, functions?
5. **Discoverability**: How do users find what they need?

Example usage I want to enable:
```python
# Example of how users should interact with the package
from package import ...
```

Domain: [field] - what are namespace conventions in this domain?

Design a clear, intuitive API structure.
```

---

## Plugin/Extension Architecture Prompt

```
I want [project] to support plugins/extensions.

Core functionality: [what's built-in]
Extension points: [where users should be able to extend]

Help me design an extension architecture:
1. **Extension mechanism**: How should plugins be implemented?
2. **Discovery**: How to find and load extensions?
3. **API contract**: What interface must extensions implement?
4. **Registration**: How do extensions register themselves?
5. **Configuration**: How to configure extensions?
6. **Isolation**: How to keep extensions from breaking each other?

Use cases:
- [Use case 1 - what kinds of extensions]
- [Use case 2]

Language: [language] - what are standard patterns for plugins in this language?

Design an extensible architecture with clear examples.
```

---

## Data Flow Architecture Prompt

```
I'm designing data flow through [system/package].

System overview: [what it does]

Data flow:
- **Input**: [where data comes from, format]
- **Processing stages**: [transformations that occur]
- **Output**: [where data goes, format]

Help me architect the data flow:
1. **Pipeline stages**: What are the distinct stages?
2. **Data structures**: What representations at each stage?
3. **State management**: What state is needed where?
4. **Error propagation**: How do errors flow through?
5. **Validation points**: Where to validate data?
6. **Parallelization**: Where can stages run concurrently?

Constraints:
- [Memory limits, streaming requirements, etc.]

Design a clean data flow architecture.
```

---

## Testing Structure Design Prompt

```
I'm designing the testing structure for [project].

Project structure:
[Describe code organization]

Testing needs:
- **Unit tests**: [what components need unit tests]
- **Integration tests**: [what interactions to test]
- **Functional tests**: [what workflows to test]
- **Other**: [performance, property-based, etc.]

Help me design test organization:
1. **Directory structure**: How to organize test files?
2. **Test discovery**: How will tests be discovered and run?
3. **Test fixtures**: Where do shared fixtures live?
4. **Test data**: How to manage test data?
5. **Test utilities**: Where do test helpers go?
6. **Coverage strategy**: What to test at each level?

Test framework: [pytest, unittest, etc.]
Standards: [any conventions to follow]

Design a maintainable test structure.
```

---

## Configuration Architecture Prompt

```
I'm designing configuration management for [project].

Configuration needs:
- [Config type 1 - e.g., "user preferences"]
- [Config type 2 - e.g., "runtime parameters"]
- [Config type 3 - e.g., "deployment settings"]

Help me design configuration architecture:
1. **Configuration sources**: Where do configs come from? (files, env vars, CLI, defaults)
2. **Configuration format**: What format(s) to use? (YAML, TOML, JSON, .ini)
3. **Precedence**: What order to apply configs?
4. **Validation**: How to validate configuration?
5. **Documentation**: How to document available options?
6. **Distribution**: What configs ship with the package?

Use cases:
- [How users will configure - e.g., "scientific workflows need experiment configs"]
- [What needs to be configurable]

Design a flexible, user-friendly configuration system.
```

---

## Quick Tips

- **Follow language conventions** - look at well-regarded projects in your language
- **Start simple** - can always refactor as complexity grows
- **Separate concerns** - each module should have a clear purpose
- **Think about users** - structure should make sense to people using the code
- **Plan for growth** - where will new features go?
- **Consider testing** - structure should facilitate testing
- **Document structure** - explain organization in README/docs

---

## Example (Geophysics Context)

```
I'm designing the structure for a seismic data processing package that will handle loading, filtering, velocity analysis, and stacking of seismic data.

Project scope:
- Main functionality: Load SEG-Y files, apply processing steps, output processed data
- Key components: I/O (SEG-Y), filtering (bandpass, FK), velocity analysis (semblance, picking), NMO correction, stacking, visualization
- Expected users: Geophysics researchers in my group, potentially open-source later
- Scale: Multi-module Python package, ~5000-10000 lines expected

Help me design the project structure:
1. **Directory layout**: What folders/files should exist?
2. **Module organization**: How to group related functionality?
3. **Separation of concerns**: What goes where and why?
4. **Entry points**: Command-line tools? Python API? Both?
5. **Configuration**: Where do processing parameters, defaults go?

Context:
- Language: Python 3.11+
- Similar projects: ObsPy (seismology), Madagascar (seismic), SciPy (signal processing)
- Constraints: Must handle large files (streaming), reproducible processing

Similar packages I know: ObsPy has obspy.io, obspy.signal structure. Madagascar has separate programs. Which model fits better for interactive processing workflows?

What's the standard structure for scientific Python packages like this?
```
