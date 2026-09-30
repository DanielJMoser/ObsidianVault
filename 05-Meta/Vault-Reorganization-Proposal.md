# Obsidian Vault Reorganization Proposal

## Current Issues with Structure

### Problems Identified
1. **Mixed organizational principles**: Subject-based (IT/, Germanistik/) vs. context-based (MCI/) vs. type-based (Diverses/)
2. **Deep nesting**: Some paths are 6+ levels deep (e.g., `IT/Bachelor DiBSE/Digital Business/Bachelorarbeit/Chapter 3/`)
3. **Inconsistent naming**: Mix of German/English, prefixes like `zz`, underscores vs. hyphens
4. **Scattered assets**: Images in various `_Drawings/` folders throughout hierarchy
5. **Temporal mixing**: Academic coursework mixed with ongoing projects
6. **Unclear boundaries**: "Diverses" becomes catch-all for unrelated content

## Proposed New Structure

### Root Level Organization
```
📁 00-Inbox/                    # Temporary holding for new notes
📁 01-Active/                   # Current projects and work
📁 02-Areas/                    # Ongoing responsibilities and interests  
📁 03-Resources/                # Reference materials and knowledge base
📁 04-Archive/                  # Completed projects and old materials
📁 05-Meta/                     # Vault management and templates
📁 Assets/                      # All media files centralized
```

### Detailed Structure

#### 00-Inbox/
- Daily captures and unprocessed notes
- Quick thoughts and ideas awaiting organization
- Meeting notes and temporary content

#### 01-Active/ (Current Projects)
```
📁 Bachelor-Thesis/             # Current thesis work
📁 MCI-Outgoing/               # Active university processes
📁 Luna-Story/                 # Active creative writing
📁 Learning-Current/           # Current courses/certifications
```

#### 02-Areas/ (Ongoing Interests)
```
📁 Computer-Science/
  📁 Algorithms-DataStructures/
  📁 Databases/
  📁 Networks/
  📁 Operating-Systems/
  📁 Security/
    📁 Cryptography/
    📁 OSINT/
    📁 Practical-Security/
📁 Programming/
  📁 Languages/
    📁 Cpp/
    📁 JavaScript/
    📁 Python/
  📁 Concepts/
📁 Academia/
  📁 Research-Methods/
  📁 Writing-Academic/
📁 Personal-Development/
  📁 Productivity-Systems/
  📁 Learning-Techniques/
```

#### 03-Resources/ (Reference Library)
```
📁 IT-Reference/
  📁 Cheat-Sheets/
  📁 Tutorials/
  📁 Documentation/
📁 Academic-Papers/
  📁 Computer-Science/
  📁 Digital-Business/
📁 Templates/
  📁 Note-Templates/
  📁 Project-Templates/
📁 Glossaries/
```

#### 04-Archive/ (Completed/Historical)
```
📁 Bachelor-DiBSE/             # Completed degree coursework
  📁 Semester-1/
  📁 Semester-2/
  📁 etc/
📁 Projects-Completed/
📁 Courses-Completed/
📁 Creative-Writing-Archive/
  📁 Luna-Legacy/
  📁 Other-Stories/
```

#### 05-Meta/ (Vault Management)
```
📁 Templates/
📁 Scripts/
📁 Maintenance/
📄 CLAUDE.md
📄 Vault-Setup.md
📄 Tagging-System.md
```

#### Assets/ (Centralized Media)
```
📁 Images/
  📁 Diagrams/
  📁 Screenshots/
  📁 Photos/
📁 Excalidraw/
📁 PDFs/
📁 Audio/
```

## Implementation Strategy

### Phase 1: Immediate Improvements (Low Risk)
1. Create new folder structure alongside existing
2. Move loose files in root to appropriate locations
3. Consolidate all images into `Assets/Images/`
4. Create index notes for major sections

### Phase 2: Content Migration (Medium Risk)
1. Move completed academic work to `04-Archive/Bachelor-DiBSE/`
2. Reorganize current IT notes by topic rather than course
3. Separate active projects from reference materials
4. Standardize naming conventions

### Phase 3: Optimization (Requires Planning)
1. Create MOCs (Maps of Content) for major areas
2. Implement consistent tagging system
3. Set up automated templates
4. Create cross-references and link maintenance

## Benefits of New Structure

### Improved Discoverability
- **PARA Method**: Projects, Areas, Resources, Archives - proven productivity system
- **Temporal Separation**: Active work separate from reference materials
- **Logical Grouping**: Related concepts together regardless of original context

### Better Maintenance
- **Centralized Assets**: All media in one location
- **Clear Boundaries**: Each folder has specific purpose
- **Consistent Naming**: Standardized conventions throughout

### Enhanced Workflow
- **Inbox Processing**: Clear path from capture to organization
- **Active Focus**: Current work easily accessible
- **Archive Clarity**: Completed work properly stored but searchable

## Naming Conventions

### Files
- Use kebab-case: `machine-learning-basics.md`
- Descriptive names: `database-normalization-forms.md` not `db-norm.md`
- No special prefixes unless part of system (e.g., `_index.md` for folder overviews)

### Folders
- Use Title-Case with hyphens: `Computer-Science/`
- Numbered prefixes only for sequential order: `01-Active/`
- Descriptive, not abbreviated: `Operating-Systems/` not `OS/`

## Migration Considerations

### Preserve History
- Keep git history intact during moves
- Document major reorganizations
- Maintain redirects for frequently accessed paths

### Link Management
- Use Obsidian's automatic link updating
- Manual verification of complex cross-references
- Consider link maintenance plugins

### Gradual Transition
- Implement structure incrementally
- Allow both old and new structures temporarily
- Move most-used content first for immediate benefits

## Tags and Metadata Strategy

### Hierarchical Tags
```
#status/active
#status/archived
#status/draft

#type/note
#type/project
#type/reference

#domain/cs
#domain/security
#domain/academic
```

### Properties (YAML Frontmatter)
```yaml
---
created: 2025-07-24
updated: 2025-07-24
status: active
type: note
domain: [cs, security]
course: IT-Security
semester: WS2024
---
```

This reorganization would transform your vault from a course-centric archive into a living, growing knowledge management system that scales with your career and interests.