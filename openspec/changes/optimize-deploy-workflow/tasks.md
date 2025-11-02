# Implementation Tasks

## Task List

- [x] 1. **Add path-based trigger filters to workflow**
   - Updated `.github/workflows/deploy.yml` to add `paths` filter under `push:` trigger
   - Included: `content/**`, `themes/**`, `config.toml`, `config.yaml`, `hugo.toml`, `hugo.yaml`, `static/**`, `layouts/**`, `assets/**`, `data/**`, `archetypes/**`, `.github/workflows/deploy.yml`
   - Excluded: `openspec/**`, `*.md` (root level), `README.md`
   - Ready for testing after deployment

- [x] 2. **Add Hugo CLI caching**
   - Added `actions/cache@v4` step before "Install Hugo CLI"
   - Cache key based on HUGO_VERSION environment variable: `hugo-${{ env.HUGO_VERSION }}-linux-amd64`
   - Cache path: `${{ runner.temp }}/hugo.deb`
   - Conditionally skips download if cache hit, always installs from .deb
   - Ready for testing in workflow runs

- [x] 3. **Add Dart Sass caching**
   - Added `actions/cache@v4` step before "Install Dart Sass"
   - Switched from snap to direct download for better caching
   - Added DART_SASS_VERSION environment variable (1.93.3)
   - Cache key: `dart-sass-${{ env.DART_SASS_VERSION }}-${{ runner.os }}`
   - Cache path: `/home/runner/dart-sass`
   - Conditionally skips download if cache hit
   - Added PATH configuration step
   - Fixed: Corrected version from non-existent 1.77.6 to valid 1.93.3

- [x] 4. **Add npm dependencies caching**
   - Added `actions/cache@v4` step before "Install Node.js dependencies"
   - Cache key based on hash of `package-lock.json`: `npm-${{ runner.os }}-${{ hashFiles('**/package-lock.json') }}`
   - Cache path: `node_modules`
   - Restore keys for partial cache matches
   - Conditionally skips npm ci if cache hit
   - Ready for testing with dependency changes

- [x] 5. **Add Hugo build cache**
   - Added `actions/cache@v4` step to cache Hugo's internal cache directory
   - Cache path: `${{ runner.temp }}/hugo_cache` (matches HUGO_CACHEDIR)
   - Cache key based on content and theme hashes: `hugo-build-${{ runner.os }}-${{ hashFiles('content/**', 'themes/**') }}`
   - Restore keys for partial cache matches
   - Hugo automatically uses cached resources directory
   - Ready for testing incremental build performance

- [x] 6. **Document caching strategy**
   - Added workflow header comments explaining optimizations
   - Added inline comments for each caching layer
   - Documented cache keys and invalidation strategy
   - Documented when caches are cleared/refreshed

- [ ] 7. **Validate and test complete workflow**
   - Run full workflow with all caching enabled (requires git push)
   - Verify first run (cache miss) completes successfully
   - Verify second run (cache hit) completes faster
   - Measure and document build time improvements
   - Ensure deployment quality unchanged

## Dependencies
- Tasks 2-5 can be implemented in parallel after task 1
- Task 6 can be done alongside implementation
- Task 7 depends on all previous tasks

## Validation
- Workflow runs successfully with all caches
- Build time reduced by 30-50% on cache hits
- No workflow triggers on openspec/ changes
- Site deploys correctly with all optimizations active
