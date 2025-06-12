# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a SCORM (Sharable Content Object Reference Model) package containing an interactive e-learning content created with Genially. The package follows SCORM 1.2 specification for Learning Management System (LMS) integration.

## Key Components

- **imsmanifest.xml**: SCORM manifest file defining the content structure and metadata
- **genially.html**: Main interactive content presentation (308KB HTML file with embedded JavaScript)
- **app/scorm.js**: Comprehensive SCORM API wrapper handling LMS communication
- **app/scorm-config.js**: Configuration setting passing percentage to 100%
- **static/js/**: React-based application chunks and media player components
- **css/**: Multiple CSS files for styling
- **images/**: Content images and assets
- **fonts/**: Web font files
- **audios/**: Audio content files

## Architecture

The SCORM package uses a layered architecture:

1. **SCORM Layer**: `app/scorm.js` provides the SCORM API wrapper with:
   - Connection management (initialize/terminate)
   - Data persistence (get/set/save)
   - Progress tracking and completion status
   - Session time reporting
   - Interaction tracking

2. **Content Layer**: `genially.html` contains the interactive presentation built with:
   - React components for dynamic content
   - Media players for various formats (YouTube, Vimeo, etc.)
   - Chart and visualization components
   - Progressive web app capabilities

3. **Configuration Layer**: `app/scorm-config.js` sets learning parameters:
   - Passing percentage: 100% (all slides must be visited)

## SCORM Integration

The package implements SCORM 1.2 with automatic:
- Progress tracking based on slide visits
- Score calculation (percentage of slides visited)
- Completion status when passing percentage is reached
- Suspend/resume functionality
- Session time tracking

The SCORM wrapper handles both SCORM 1.2 and 2004 versions automatically and manages LMS communication through standard SCORM API calls.