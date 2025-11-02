# Optimize Deploy Workflow

## Problem
The current GitHub Actions deployment workflow triggers on every push to master and rebuilds from scratch each time, leading to:
- Unnecessary workflow runs for non-site changes (e.g., OpenSpec updates)
- Slower build times due to repeated installation of Hugo, Dart Sass, and dependencies
- Inefficient resource usage and longer feedback cycles

## Proposed Solution
Enhance the deployment workflow with intelligent caching and conditional triggers to improve build performance and reduce unnecessary runs.

**Key improvements:**
1. **Smart Path Triggers**: Only trigger deployment when actual site content changes (content/, themes/, config files, etc.), excluding openspec/ and other non-site directories
2. **Dependency Caching**: Cache Hugo CLI, Dart Sass, and npm dependencies to avoid repeated installations
3. **Build Caching**: Leverage Hugo's built-in caching for faster incremental builds

## Affected Capabilities
- **deployment**: Modified to include caching strategies and conditional workflow triggers

## Success Criteria
- Workflow only triggers on relevant file changes (not on openspec/ updates)
- Build times reduced by 30-50% through effective caching
- No impact on deployment reliability or site quality
- Clear cache invalidation when dependencies are updated

## Non-Goals
- Changing the hosting platform or deployment target
- Adding new deployment environments (staging, etc.)
- Modifying the Hugo build configuration or output

## Actual Results

### Performance Improvement
**Measured build times:**
- **Before optimization**: 43.4 seconds (average)
- **After optimization**: 30.2 seconds (average)
- **Improvement**: 13.2 seconds reduction (30.4% faster)

This meets the success criteria of 30-50% build time reduction and validates the effectiveness of the multi-layer caching strategy.
