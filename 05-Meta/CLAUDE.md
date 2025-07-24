# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is an Obsidian vault containing a comprehensive personal knowledge base with academic notes, IT/computer science documentation, and creative writing. The repository uses a PARA-based organizational system (Projects, Areas, Resources, Archives) for optimal knowledge management while preserving German directory names for academic content.

## Architecture and Structure

### PARA-Based Organization

- **00-Inbox/** - Temporary holding area for new notes and captures
- **01-Active/** - Current projects and active work
  - Bachelor-Thesis/ - Ongoing thesis research and writing
  - MCI-Outgoing/ - Active university processes and documentation  
  - Luna-Story/ - Active creative writing project
  - Learning-Current/ - Current courses and learning materials
- **02-Areas/** - Ongoing responsibilities and interests
  - Computer-Science/ - Core CS topics with German directory names preserved
    - Betriebssysteme/ (Operating Systems)
    - Algorithmen-Datenstrukturen/ (Algorithms & Data Structures)
    - Datenbanken/ (Databases)
    - Datennetze/ (Networks)
    - IT Security/ (IT Security)
    - Machine Learning/ (Machine Learning)
    - Systeme/ (Systems Architecture)
  - Programming/ - Programming languages, concepts, and tools
    - Programmierung/ (German programming concepts)
  - Languages/ - German studies and linguistics
    - Germanistik/ (German Studies)
    - Geschichte/ (History)
  - Personal-Development/ - Productivity systems and self-improvement
  - Academia/ - Research methods and academic skills
- **03-Resources/** - Reference materials and knowledge base
  - IT-Reference/ - Technical documentation and cheat sheets
  - Academic-Papers/ - Research papers and citations
  - Templates/ - Note and project templates
  - Glossaries/ - Term definitions and reference materials
- **04-Archive/** - Completed projects and historical materials
  - Bachelor DiBSE/ - Completed degree coursework
  - Projects-Completed/ - Finished projects and old work
  - Creative-Writing-Archive/ - Completed stories and writing
- **05-Meta/** - Vault management and configuration
  - Templates/ - Note templates and automation
  - Scripts/ - Utility scripts and tools
  - Maintenance/ - Vault organization and cleanup
- **Assets/** - Centralized media storage
  - Images/ - All images, diagrams, and screenshots (including former _Drawings/ content)
  - Excalidraw/ - Interactive diagrams and drawings
  - Documents/ - PDFs and other document files
  - Other/ - Miscellaneous files

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

### PARA Workflow
- **Capture**: New ideas go to 00-Inbox/ for processing
- **Process**: Move items from Inbox to appropriate PARA category
- **Active Work**: Keep 01-Active/ focused on current priorities
- **Maintenance**: Regularly review and archive completed projects

### File Management
- **Search**: Use Obsidian's built-in search or grep for content discovery
- **Navigation**: PARA structure provides clear organizational hierarchy
- **Linking**: Internal links use `[[filename]]` syntax
- **Assets**: All media centralized in Assets/ folder with descriptive subfolders
- **Excalidraw References**: All Excalidraw images now located in Assets/Excalidraw/ and Assets/Images/

### Content Organization
- **Naming**: German names preserved for academic content, English for organizational structure
- **Folders**: German academic directories maintained (e.g., Betriebssysteme/, Datenbanken/)
- **Index Files**: Create _index.md files for major sections
- **Cross-References**: Maintain links between related concepts across areas
- **Asset References**: Update any image links to point to Assets/Images/ or Assets/Excalidraw/

## Important Notes

### Repository-Specific Conventions
- This is a personal knowledge base, not a software project
- No build processes, testing, or deployment workflows
- Content is primarily in German for academic subjects
- PARA system separates active work from reference materials
- German directory names preserved for academic authenticity
- All assets centralized in Assets/ folder
- Git conflicts may occur due to obsidian-git automation

### Working with Content
- Respect PARA organizational principles
- Maintain German language and directory names for academic content
- Use Obsidian markdown extensions appropriately (backlinks, tags, etc.)
- Be cautious with automated changes to preserve academic integrity
- Keep Assets/ folder organized with descriptive filenames
- Update image references to use centralized Assets/ paths

### File Types and Patterns
- `.md` files: Standard markdown notes
- `.excalidraw.md`: Excalidraw diagrams (stored in Assets/Excalidraw/)
- Image files: All centralized in Assets/Images/ (formerly scattered in _Drawings/ folders)
- Documents: PDFs and other files in Assets/Documents/

### PARA Maintenance
- **Regular Reviews**: Process Inbox weekly, review Active projects monthly
- **Archive Management**: Move completed projects from Active to Archive
- **Link Maintenance**: Update internal links when reorganizing content
- **Asset Organization**: Keep media files properly categorized in Assets/
- **German Name Preservation**: Maintain German directory names for academic content

### Asset Reference Updates
When working with content that references images or Excalidraw diagrams:
- All former `_Drawings/` content is now in `Assets/Images/`
- All Excalidraw files are now in `Assets/Excalidraw/`
- Update any broken image links to point to the new centralized locations
- Use relative paths like `[[Assets/Images/filename.png]]` for consistency

The vault serves as both a learning repository and reference system for academic and professional development, optimized for long-term knowledge management while preserving German academic structure and terminology.