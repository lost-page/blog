# Project Context

## Purpose
A simple, clean tech blog focused on technology, engineering skills, leadership, and team topics. The blog prioritizes content quality and ease of maintenance over complex features.

## Tech Stack
- **Static Site Generator**: Hugo
- **Content Format**: Markdown files
- **Hosting**: GitHub Pages
- **Version Control**: Git

## Project Conventions

### Code Style
- Keep it simple and maintainable
- Avoid unnecessary complexity or frameworks
- Prefer static configuration over dynamic code
- Follow Hugo best practices and conventions

### Architecture Patterns
- Static site generation (no server-side processing)
- File-based content management (Markdown in `/content/`)
- Theme-based styling (minimal, clean design)
- Git-based workflow for content updates

### Testing Strategy
- Manual testing of site generation and rendering
- Preview builds before deploying to production
- Test content rendering, navigation, and search functionality

### Git Workflow
- Master branch for production-ready content
- Feature branches for significant changes or new posts
- Deploy to GitHub Pages on push to main

## Domain Context
This is a personal tech blog covering:
- Software engineering practices and techniques
- Leadership and management in tech
- Team dynamics and collaboration
- Technical tutorials and guides

Target audience: Technical professionals, engineering leaders, and developers.

## Important Constraints
- Must be easy to update with new posts (just add Markdown files)
- No database or backend required
- Fast build and deploy times
- Mobile-responsive design
- Accessible and SEO-friendly

## External Dependencies
- GitHub Pages for hosting
- Hugo static site generator (installed locally for development)
- No external APIs or services required for core functionality
