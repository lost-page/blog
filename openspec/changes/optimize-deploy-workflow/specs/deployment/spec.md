# deployment Specification Deltas

## MODIFIED Requirements

### Requirement: GitHub Actions Workflow
The system SHALL use GitHub Actions to automatically build and deploy the site with optimized caching and conditional triggers.

#### Scenario: Workflow triggered only on site changes
- **WHEN** changes are pushed to the main branch affecting site content (content/, themes/, config files, static assets)
- **THEN** GitHub Actions automatically builds and deploys the site
- **AND** changes to non-site files (openspec/, documentation) do not trigger deployment

#### Scenario: Hugo CLI installation cached
- **WHEN** the workflow runs and Hugo is already cached
- **THEN** the cached Hugo CLI is restored instead of being downloaded again

#### Scenario: Dart Sass installation cached
- **WHEN** the workflow runs and Dart Sass is already cached
- **THEN** the cached Dart Sass is restored instead of being installed again

#### Scenario: npm dependencies cached
- **WHEN** the workflow runs and package-lock.json hasn't changed
- **THEN** cached node_modules are restored instead of running npm ci

### Requirement: Fast Deployment
The system SHALL complete builds and deployments efficiently using caching for improved performance.

#### Scenario: Cached build performance
- **WHEN** dependencies are cached and no breaking changes exist
- **THEN** build time is reduced by at least 30% compared to uncached builds

#### Scenario: Hugo build cache utilized
- **WHEN** Hugo builds the site
- **THEN** Hugo's internal cache is used across workflow runs for faster incremental builds
