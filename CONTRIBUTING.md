# Contributing to Prompt Protocols

Thank you for considering contributing to Prompt Protocols! This project helps scientific software developers work more effectively with AI coding assistants.

## Ways to Contribute

### 🔧 Template Improvements
- Clarify existing prompt templates
- Add missing prompt variants
- Improve template structure or formatting

### 📚 Domain-Specific Examples
- Add examples from your scientific field
- Demonstrate template applications

### 📖 Documentation Fixes
- Fix typos, broken links, or formatting issues
- Add missing documentation
- Update outdated information

## First Time Contributing?

**Not sure where to start?**
- Look for issues labeled `good first issue`
- Fix typos or unclear explanations you notice
- Add an example from your field
- Share feedback on what's confusing

**Questions?** Open a discussion!

---

## Getting Started

### Summary
1. Fork the repository
2. Create a branch for your changes
3. Make your improvements
4. Submit a pull request

**No local development environment needed!** All files are Markdown and can be edited directly on GitHub.

### Development Setup (Optional)

If you prefer working locally:

```bash
# Fork repository on GitHub, then:
git clone https://github.com/YOUR-USERNAME/prompt-protocols.git
cd prompt-protocols
```

---

## Contribution Guidelines

### For Template Improvements

**Template structure:**
````markdown
## [Template Name] Prompt

```markdown
[Prompt template with clear placeholders]
```
````

### For Domain-Specific Examples

**Where to add:**
- Add to existing template's "Examples" section
- Reference your field in example heading
- Keep generic template structure unchanged

**Example format:**
````markdown
### Example: [Your Scientific Field]

**Context:** [Brief description of the problem/scenario]

**Prompt:**
```markdown
[Filled template with your domain specifics]
```

**Why this example is useful:** [Brief explanation]

**Outcome (optional):** [What happened when you used this prompt]
````

**Guidelines:**
- Make examples realistic but anonymize sensitive information
- Focus on demonstrating template usage, not solving your specific problem

### For Documentation Fixes

**Guidelines:**
- Fix errors you notice while using templates
- Improve clarity where you got confused
- Add links between related content

**Common improvements:**
- Fixing broken links
- Correcting typos or grammar
- Clarifying confusing sections
- Adding missing cross-references
- Improving formatting consistency

---

## Contribution Workflow

### 1. Before You Start
- Check existing issues/PRs to avoid duplication
- For major changes, open an issue first to discuss
- For minor fixes, proceed directly to PR

### 2. Setting Up
- Fork the repository.
- (Optional) Clone your forked repository to work locally:
    ```bash
    git clone https://github.com/YOUR-USERNAME/prompt-protocols.git
    cd prompt-protocols
    ```

### 2. Making Changes

**On GitHub (easiest for small changes):**
1. Navigate to the file you want to edit
2. Click the pencil icon to edit
3. Make your changes
4. Scroll down to "Propose changes"
5. Add a commit message and description
6. Click "Propose changes"
7. Click "Create pull request"

**Locally (for larger changes):**
```bash
# Create a branch
git checkout -b fix/template-clarification
# or
git checkout -b feature/add-chemistry-example

# Make your changes

# Commit with clear message
git commit -m "Clarify edge case handling in problem-framing template"

# Push to your fork
git push origin fix/template-clarification
```

### 3. Submitting Pull Request

Use our [PR template](.github/pull_request_template.md).

### 4. PR Review Process
- May request changes or clarification
- Discussion happens in PR comments
- Once approved, changes are merged

### 5. After Merge
- Delete your branch: `git branch -d fix/your-branch`
- Pull latest changes: `git pull upstream main`

---

## Style Guidelines

### Markdown Formatting
- Use `## ` for main sections, `### ` for subsections, `#### ` for sub-subsections
- Use ` ```markdown ` for prompt templates
- Use ` ```bash ` for shell commands
- Use bullet lists (`-`) for unordered items
- Use numbered lists (`1.`) for sequential steps
- Use **bold** for emphasis, `code` for technical terms, *italic* for mild emphasis

### Template Design Principles
- **Flexible:** Adaptable to different problems
- **Structured:** Clear sections and placeholders
- **Guided:** Provide enough scaffolding without over-constraining
- **Contextual:** Space for domain-specific information
- **Practical:** Focus on real-world usage

### Placeholder Conventions
- Use `[information]` for required information
- Use `[optional: information]` for optional information
- Use `[e.g., "example"]` to show what kind of information is expected
- Keep placeholders specific enough to guide but flexible enough to adapt
- Use descriptive names: `[package-name]` not `[name]`

---

## Testing Requirements

Since this is a documentation project, "testing" means:

### Before Submitting
- ✅ **Markdown renders correctly:** Preview in GitHub or Markdown editor
- ✅ **Links work:** Test all internal and external links
- ✅ **Code blocks display properly:** Check language specification and formatting
- ✅ **Examples make sense:** Read through your examples as if you're a new user
- ✅ **Placeholders are clear:** Ensure placeholders guide without confusing

### Self-Check Questions
- Can someone from a different scientific domain understand this?
- Are instructions complete and unambiguous?
- Does this improve the user experience?
- Have I maintained consistency with existing templates?
- Would I find this helpful if I were using these templates for the first time?

---

## Documentation Requirements

### Documentation Standards
- **Cross-reference:** Link to related templates and sections
- **Maintain index:** Keep `TEMPLATES-INDEX.md` current
- **Update examples:** Ensure examples reflect current template structure
- **Version awareness:** Note if changes affect existing user workflows

---

## What NOT to Contribute

Please avoid:
- ❌ Language/tool-specific implementations (keep templates generic)
- ❌ Complete codebases or large code snippets
- ❌ Promotional content for specific AI tools
- ❌ Major restructuring without discussion first
- ❌ Domain-specific jargon without explanation

---

## Questions or Ideas?

- 💬 **GitHub Discussions:** Start a discussion for ideas or questions
- 🐛 **GitHub Issues:** Open an issue for bugs or specific improvements

---

## Code of Conduct

We are committed to providing a welcoming and inclusive environment. Please:
- Be respectful and considerate
- Welcome newcomers and help them learn
- Focus on what's best for the community
- Show empathy towards others

See our [Code of Conduct](CODE_OF_CONDUCT.md) for details.

---

## License

By contributing to Prompt Protocols, you agree that your contributions will be licensed under the same license as the project (see [LICENSE](LICENSE)).
