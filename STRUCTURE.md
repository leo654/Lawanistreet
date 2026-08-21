# Codebase Structure

## Overview

The repository is organized so page routes remain at root, while all static assets are centralized in `assets/`.

## Directory Structure

```
html/
├── assets/
│   ├── css/                  # Stylesheets and vendor CSS
│   ├── js/                   # Application scripts, modules, third-party libraries
│   ├── img/                  # Images and project-specific visual assets
│   ├── fonts/                # Font files
│   ├── video/                # Video assets
│   ├── favicons/             # Favicon and web manifest files
│   └── slide/                # Slide-specific assets
├── docs/
│   └── FILE_MANAGEMENT.md    # Operational file management rules
├── legacy/
│   └── unused-root/          # Archived root files retained for reference
├── php/                      # Mail endpoint
├── scss/                     # SCSS source files
├── scripts/
│   └── file-manager.sh       # Size/reference auditing utility
└── *.html                    # Page entry points (kept at root for stable URLs)
```

## File Management Workflow

1. Keep new static assets under `assets/`.
2. Keep route files (`*.html`) at root unless routing is intentionally changed.
3. Archive superseded loose files in `legacy/unused-root/`.
4. Run link integrity checks after moves:

```bash
./scripts/file-manager.sh check-links
```

5. Use size report to manage bloat:

```bash
./scripts/file-manager.sh largest
```
