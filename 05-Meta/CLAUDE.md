# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is an Obsidian vault containing a comprehensive personal knowledge base with academic notes, IT/computer science documentation, and creative writing. The repository is structured as a markdown-based note system using Obsidian as the primary editor.

## Architecture and Structure

### Main Content Areas

- **IT/** - Computer science and IT security notes covering:
  - Bachelor DiBSE coursework (Operating Systems, Databases, Networks, Machine Learning, etc.)
  - IT Security (OSINT, cryptography, practical security)
  - Programming languages (C++, JavaScript, Python) and concepts
- **Germanistik/** - German literature and linguistics studies
- **Geschichte/** - Historical notes
- **MCI/** - University-related documentation and processes
- **Diverses/** - Miscellaneous content including creative writing projects

### Technology Stack

- **Platform**: Obsidian vault (markdown-based knowledge management)
- **Version Control**: Git with automated backups via obsidian-git plugin
- **File Format**: Markdown (.md) with Obsidian extensions
- **Plugins**: 
  - obsidian-git (automated version control)
  - obsidian-excalidraw-plugin (diagrams)
  - obsidian-advanced-slides (presentations)
  - Various UI and functionality enhancements

## Common Operations

### Git Workflow
The repository uses automated git commits through the obsidian-git plugin with commit messages in format "vault backup: YYYY-MM-DD HH:MM:SS".

**Manual Git Operations:**
```bash
git status                    # Check repository status
git add .                     # Stage all changes
git commit -m "message"       # Manual commit
git push origin main          # Push to remote
```

### File Management
- **Search**: Use Obsidian's built-in search or grep for content discovery
- **Navigation**: Files are organized hierarchically by subject area
- **Linking**: Internal links use `[[filename]]` syntax
- **Images**: Stored in subdirectories, often named `_Drawings/` or similar

### Content Organization
- Academic notes follow hierarchical structure (Subject > Topic > Subtopic)
- Files use descriptive names, often with prefixes like `_` for index files
- Excalidraw drawings prefixed with `zz` or similar for organization
- German academic structure reflects university coursework organization

## Important Notes

### Repository-Specific Conventions
- This is a personal knowledge base, not a software project
- No build processes, testing, or deployment workflows
- Content is primarily in German for academic subjects
- Creative writing projects in `/Diverses/Luna/` and similar directories
- Git conflicts may occur due to obsidian-git automation (see conflict-files-obsidian-git.md)

### Working with Content
- Respect existing academic note structure and hierarchies
- Maintain German language for academic content where established
- Use Obsidian markdown extensions appropriately (backlinks, tags, etc.)
- Be cautious with automated changes to preserve academic integrity

### File Types and Patterns
- `.md` files: Standard markdown notes
- `.excalidraw.md`: Excalidraw diagrams embedded in markdown
- `.png/.jpg`: Images and diagrams in `_Drawings/` subdirectories
- `.txt`: Text files (e.g., spell check results)

The vault serves as both a learning repository and reference system for academic and professional development in computer science and related fields.