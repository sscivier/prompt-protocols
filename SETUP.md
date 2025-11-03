# Setup Instructions

This guide explains how to set up `prompt-protocols` for use across multiple projects through symlinks.

## Overview

The `prompt-protocols` repository is designed to be cloned once to a central location and symlinked into individual projects' `ai-dev/` directory. This approach allows you to:

- Maintain one authoritative source of prompt templates and assessment tools
- Update templates across all projects with a single `git pull`
- Keep project repositories clean (symlinks in a local-only directory)
- Share templates across projects without version control overhead
- Optionally include prompt development artifacts in version control when desired

---

## Initial Setup

### 1. Clone the Repository

Clone `prompt-protocols` to a central location on your system:

```bash
# Choose a location for tools/resources (adjust path as needed)
cd ~/path/to/tools

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
# Navigate to your project root
cd ~/path/to/your-project

# Create ai-dev directory for prompt development resources
mkdir -p ai-dev

# Navigate into it
cd ai-dev

# Create symlinks to shared resources
ln -s ~/path/to/tools/prompt-protocols/prompts ./prompts
ln -s ~/path/to/tools/prompt-protocols/assessment ./assessment

# Optional: symlink the reference document
ln -s ~/path/to/tools/prompt-protocols/ten-simple-rules-reference.md ./ten-simple-rules-reference.md
```

### For Projects Using Git

Add `ai-dev/` to your `.gitignore` to keep these local development resources out of version control:

```bash
# From project root
echo "ai-dev/" >> .gitignore
```

**When to track prompt artifacts:** If you want to version control specific prompts or prompt development artifacts, you can:
- Keep `ai-dev/` ignored but copy finalized prompts to a tracked location (e.g., `docs/prompts/`)
- Create a separate tracked directory for shared prompt artifacts
- Track specific files within `ai-dev/` using git negation patterns in `.gitignore`

### Verification

Confirm symlinks are working:

```bash
# Check symlink creation (from project root)
ls -la ai-dev/

# Should show something like:
# prompts -> /Users/you/path/to/tools/prompt-protocols/prompts
# assessment -> /Users/you/path/to/tools/prompt-protocols/assessment

# Verify contents are accessible
ls ai-dev/prompts/
```

### For Projects Not Using Git

If your project doesn't use git version control, you can still use the `ai-dev/` directory:

```bash
# Same setup as above
cd ~/path/to/your-project
mkdir -p ai-dev
cd ai-dev
ln -s ~/path/to/tools/prompt-protocols/prompts ./prompts
ln -s ~/path/to/tools/prompt-protocols/assessment ./assessment
```

The `ai-dev/` directory is simply a convention for organizing prompt development resources - no git required.

---

## Usage in Projects

### Accessing Templates

Once symlinked, access templates directly from your project:

```bash
# View available templates
cat ai-dev/prompts/TEMPLATES-INDEX.md

# Open specific template
cat ai-dev/prompts/01-domain-research.md
```

### With AI Coding Assistants

When working with AI assistants (GitHub Copilot, Claude, etc.):

1. **Use templates to write your prompts**:
   - "Fill in the blanks."
   - Use a template for inspiration if your scenario doesn't quite match up.

2. **Use assessment tools**:
   - Reference the checklist at the end of `prompts/implementation.md` for a self-check.
   - Ask the AI assistant to assess your prompt.
   ```markdown
   "Please assess my prompt against ai-dev/assessment/prompt-assessment.md:
   [INSERT PROMPT]
   "
   ```

---

## Updating Templates

### Pulling Updates

When templates are updated in the central repository:

```bash
# Navigate to central repository
cd ~/path/to/tools/prompt-protocols

# Pull latest changes
git pull origin main

# That's it! All symlinked projects now see updated templates
```

### Verifying Updates

Check that projects see the updates:

```bash
# In any project with symlinks
cd ~/path/to/your-project
cat ai-dev/prompts/implementation.md  # Should show latest version
```

---

## Multiple Projects Setup

### Batch Setup Script

For setting up multiple projects at once, create a setup script:

```bash
#!/bin/bash
# setup-prompt-protocols.sh

PROTOCOLS_PATH="$HOME/path/to/tools/prompt-protocols"
PROJECTS=(
    "$HOME/path/to/first/project"
    "$HOME/path/to/second/project"
    # Add more projects here
)

for project in "${PROJECTS[@]}"; do
    if [ -d "$project" ]; then
        cd "$project"
        mkdir -p ai-dev
        cd ai-dev
        
        # Remove old symlinks if they exist
        rm -f prompts assessment ten-simple-rules-reference.md
        
        # Create fresh symlinks
        ln -s "$PROTOCOLS_PATH/prompts" ./prompts
        ln -s "$PROTOCOLS_PATH/assessment" ./assessment
        ln -s "$PROTOCOLS_PATH/ten-simple-rules-reference.md" ./ten-simple-rules-reference.md
        
        # Add to .gitignore if git repo exists
        if [ -d "$project/.git" ]; then
            if ! grep -q "^ai-dev/$" "$project/.gitignore" 2>/dev/null; then
                echo "ai-dev/" >> "$project/.gitignore"
                echo "  ✓ Added ai-dev/ to .gitignore"
            fi
        fi
        
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
ls ~/path/to/tools/prompt-protocols/prompts

# Recreate symlink with correct path
rm ai-dev/prompts
ln -s ~/path/to/tools/prompt-protocols/prompts ai-dev/prompts
```

### Permission Issues

**Symptom**: Cannot access files through symlinks

**Solution**: Check permissions on source directory
```bash
chmod -R u+r ~/path/to/tools/prompt-protocols
```

### Git Tracking

**Recommended approach**: Add `ai-dev/` to `.gitignore` to keep prompt development resources local.

```bash
echo "ai-dev/" >> .gitignore
```

 **If you want to track the symlinks**: Remove `ai-dev/` from `.gitignore` or use negation patterns. Git will track symlinks themselves (not their contents).

```bash
# To track symlinks
git add ai-dev/prompts  # This stages the symlink, not the contents
```

**Note**: Tracking symlinks means other collaborators need the same `prompt-protocols` setup for the symlinks to work.

---

## Advanced Configuration

### Project-Specific Customization

If you need project-specific templates:

1. Keep shared templates symlinked in `ai-dev/`
2. Add custom templates directly in `ai-dev/`
3. Reference both in your workflows

```
ai-dev/
├── prompts/           # Symlink to shared templates
├── assessment/        # Symlink to shared assessment
├── custom-prompts/    # Project-specific templates
└── work-in-progress/  # Your prompt drafts
```

Everything in `ai-dev/` can remain untracked if you've added it to `.gitignore`.

### Version Pinning

To pin a specific version of templates:

```bash
cd ~/path/to/tools/prompt-protocols
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
git clone git@github.com:sscivier/prompt-protocols.git ~/path/to/tools/prompt-protocols
```

**Per-project setup**:
```bash
cd ~/path/to/project
mkdir -p ai-dev
cd ai-dev
ln -s ~/path/to/tools/prompt-protocols/prompts ./prompts
ln -s ~/path/to/tools/prompt-protocols/assessment ./assessment
echo "ai-dev/" >> ../.gitignore  # If using git
```

**Updates**:
```bash
cd ~/path/to/tools/prompt-protocols && git pull
```

That's it! Templates are now available across all your projects and stay synchronized automatically.