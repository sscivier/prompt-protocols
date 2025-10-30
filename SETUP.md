# Setup Instructions

This guide explains how to set up `prompt-protocols` for use across multiple projects through symlinks.

## Overview

The `prompt-protocols` repository is designed to be cloned once to a central location and symlinked into individual projects. This approach allows you to:

- Maintain one authoritative source of prompt templates and assessment tools
- Update templates across all projects with a single `git pull`
- Keep project repositories clean (symlinks, not copies)
- Version control your prompt development workflow

---

## Initial Setup

### 1. Clone the Repository

Clone `prompt-protocols` to a central location on your system:

```bash
# Choose a location for tools/resources (adjust path as needed)
cd ~/Developer/phd/tools

# Clone the repository
git clone git@github.com:sscivier/prompt-protocols.git
```

**Note**: The exact path doesn't matter, but using a consistent location for shared tools makes management easier.

### 2. Verify Contents

Confirm the repository structure:

```bash
cd prompt-protocols
ls -la
```

You should see:
- `prompts/` - Template files for prompt development
- `assessment/` - Prompt quality assessment checklist
- `ten-simple-rules-reference.md` - Core principles reference
- Other documentation files

---

## Project Integration

### Adding to a New Project

To integrate `prompt-protocols` into a project:

```bash
# Navigate to your project's .github directory
cd ~/path/to/your-project/.github

# Create symlink to prompts
ln -s ~/Developer/phd/tools/prompt-protocols/prompts ./prompts

# Create symlink to assessment tools
ln -s ~/Developer/phd/tools/prompt-protocols/assessment ./assessment

# Optional: symlink the reference document
ln -s ~/Developer/phd/tools/prompt-protocols/ten-simple-rules-reference.md ./ten-simple-rules-reference.md
```

**Alternative Location**: If your project doesn't have a `.github/` directory, you can create the symlinks in:
- Project root directory
- A `docs/` directory
- Any location that makes sense for your project structure

### Verification

Confirm symlinks are working:

```bash
# Check symlink creation
ls -la .github/

# Should show something like:
# prompts -> /Users/you/Developer/phd/tools/prompt-protocols/prompts
# assessment -> /Users/you/Developer/phd/tools/prompt-protocols/assessment

# Verify contents are accessible
ls .github/prompts/
```

---

## Usage in Projects

### Accessing Templates

Once symlinked, access templates directly from your project:

```bash
# View available templates
cat .github/prompts/TEMPLATES-INDEX.md

# Open specific template
cat .github/prompts/01-domain-research.md
```

### With AI Coding Assistants

When working with AI assistants (GitHub Copilot, Claude, etc.):

1. **Use templates to write your prompts**:
   - "Fill in the blanks."
   - Use a template for inspiration if your scenario doesn't quite match up.

2. **Use assessment tools**:
   - Reference the checklist at the end of `prompts/implementation.md` for a self-check.
   - Ask the AI assistant to assess your prompt.
   ```
   "Please assess my prompt against .github/assessment/prompt-assessment.md:
   [INSERT PROMPT]
   "
   ```

---

## Updating Templates

### Pulling Updates

When templates are updated in the central repository:

```bash
# Navigate to central repository
cd ~/Developer/phd/tools/prompt-protocols

# Pull latest changes
git pull origin main

# That's it! All symlinked projects now see updated templates
```

### Verifying Updates

Check that projects see the updates:

```bash
# In any project with symlinks
cd ~/path/to/your-project
cat .github/prompts/implementation.md  # Should show latest version
```

---

## Multiple Projects Setup

### Batch Setup Script

For setting up multiple projects at once, create a setup script:

```bash
#!/bin/bash
# setup-prompt-protocols.sh

PROTOCOLS_PATH="$HOME/Developer/phd/tools/prompt-protocols"
PROJECTS=(
    "$HOME/path/to/first/project"
    "$HOME/path/to/second/project"
    # Add more projects here
)

for project in "${PROJECTS[@]}"; do
    if [ -d "$project" ]; then
        mkdir -p "$project/.github"
        cd "$project/.github"
        
        # Remove old symlinks if they exist
        rm -f prompts assessment ten-simple-rules-reference.md
        
        # Create fresh symlinks
        ln -s "$PROTOCOLS_PATH/prompts" ./prompts
        ln -s "$PROTOCOLS_PATH/assessment" ./assessment
        ln -s "$PROTOCOLS_PATH/ten-simple-rules-reference.md" ./ten-simple-rules-reference.md
        
        echo "✓ Set up prompt-protocols in $project"
    else
        echo "✗ Project not found: $project"
    fi
done
```

Make executable and run:

```bash
chmod +x setup-prompt-protocols.sh
./setup-prompt-protocols.sh
```

---

## Troubleshooting

### Symlinks Not Working

**Symptom**: `ls -la` shows broken symlinks (red text or different color)

**Solution**: Verify the source path exists and is correct
```bash
# Check if source exists
ls ~/Developer/phd/tools/prompt-protocols/prompts

# Recreate symlink with correct path
rm .github/prompts
ln -s ~/Developer/phd/tools/prompt-protocols/prompts .github/prompts
```

### Permission Issues

**Symptom**: Cannot access files through symlinks

**Solution**: Check permissions on source directory
```bash
chmod -R u+r ~/Developer/phd/tools/prompt-protocols
```

### Git Tracking Symlinks

**Issue**: Git tries to track symlink contents instead of the symlink itself

**Solution**: Ensure `.gitignore` excludes symlink targets but not the symlinks themselves. Symlinks should appear in git as symlinks, not as directories.

If you want to track the symlinks themselves:
```bash
# Symlinks should be staged as symlinks
git add .github/prompts  # This stages the symlink, not the contents
```

---

## Advanced Configuration

### Project-Specific Customization

If you need project-specific templates:

1. Keep shared templates symlinked
2. Add custom templates directly in project
3. Reference both in your workflows

```
.github/
├── prompts/           # Symlink to shared templates
└── custom-prompts/    # Project-specific templates
```

### Version Pinning

To pin a specific version of templates:

```bash
cd ~/Developer/phd/tools/prompt-protocols
git checkout <specific-commit-or-tag>
```

All symlinked projects will use that version until you update.

---

## Getting Help

- **Template usage questions**: See [prompts/TEMPLATES-INDEX.md](prompts/TEMPLATES-INDEX.md)
- **Assessment criteria**: See [assessment/prompt-assessment.md](assessment/prompt-assessment.md)
- **Core principles**: See [ten-simple-rules-reference.md](ten-simple-rules-reference.md)
- **Issues**: Open an issue on GitHub

---

## Summary

**One-time setup**:
```bash
git clone git@github.com:sscivier/prompt-protocols.git ~/Developer/phd/tools/prompt-protocols
```

**Per-project setup**:
```bash
cd ~/path/to/project/.github
ln -s ~/Developer/phd/tools/prompt-protocols/prompts ./prompts
ln -s ~/Developer/phd/tools/prompt-protocols/assessment ./assessment
```

**Updates**:
```bash
cd ~/Developer/phd/tools/prompt-protocols && git pull
```

That's it! Templates are now available across all your projects and stay synchronized automatically.