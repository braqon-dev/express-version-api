# Changelog

All notable changes to this project are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/).

## [Unreleased]

## [2.0.8] - 2026-11-03

No changes to the runtime code: same API and behavior as 2.0.7.

### Added

- `SECURITY.md` with supported versions, private reporting and response times.
- README: contents line, JSR install for Node.js, typed quick start and a supply chain security section.
- "Report a vulnerability" link in the new-issue menu.

### Changed

- JSR package moved to `@braqon/express-version-api`. The old `@braian-quintian/express-version-api` is archived.
- npm releases are published with trusted publishing (OIDC) and provenance instead of a stored `NPM_TOKEN`.
- Bilingual (English/Spanish) code of conduct; reports go to hola@braqon.dev.
- Contributing guide matches the real workflow: pull requests target `develop`, signed commits, required checks and release process.
- Dev tooling: ESLint 10, tsup 9, lint-staged 17 and minor updates.
- CI runs the test suite once per pull request instead of up to three times.

### Fixed

- `LICENSE` is detected as MIT by GitHub; copyright is now 2024-present.

### Security

- Updated development dependencies to resolve the critical `proxy-addr` alert and most high alerts (dev-only; the published package has no runtime dependencies).

### Removed

- The workflow that auto-merged Dependabot pull requests. Dependency updates now need a human review.

## [2.0.7] - 2026-11-03

### Changed

- Moved the project to the [`braqon-dev`](https://github.com/braqon-dev) organization. Repository, homepage and issue links now point to `braqon-dev/express-version-api`.
- GitHub Packages builds are published as `@braqon-dev/express-version-api`.

### Fixed

- Issue templates now live where GitHub reads them (`.github/ISSUE_TEMPLATE/`).

### Removed

- Dependabot version updates. Dependabot security updates stay enabled.

## [2.0.4] - 2026-02-27

### Added

- Added `jsr.json` configuration and JSR package metadata.
- Added JSR publication support for `@braian-quintian/express-version-api`.

### Changed

- Updated repository documentation to match the current runtime behavior and exports.
- Hardened release automation to validate npm authentication before publish.

### Fixed

- Fixed `.npmrc` token interpolation to use `NODE_AUTH_TOKEN` in CI.
- Fixed GitHub Packages publication flow by using scoped package publish in workflow.

## [2.0.3] - 2026-02-27

### Changed

- Updated release workflow with explicit npm authentication verification.

## [2.0.0] - 2026-02-27

### Removed

- Removed deprecated `createVersionMiddleware` API.
- Removed CommonJS default export path; CJS now uses named exports only.

### Changed

- `test:types` now validates `test-types/**/*.test-d.ts` and runs in `validate`/CI.
- CI now targets `develop` and `main`, and PR checks use the actual base branch.
- `npm test` no longer writes coverage artifacts by default.
- Pre-commit hook now runs `lint-staged`.
- TypeScript incremental metadata moved outside publish output.
- Removed unused dev dependencies: `@types/semver`, `ts-node`.
- Updated README and package docs to match runtime behavior.

### Fixed

- `fallbackStrategy` is now validated at config resolution.
- Async `defaultHandler` errors are forwarded to Express `next(error)`.
- Caret matching for `0.x` follows semver-compatible constraints.
- `missingVersionMessage` from config is now applied in responses.
- Path extraction is stable with global/sticky regex (`lastIndex` handling).
- `req.versionInfo.source` now preserves the original extraction source in fallback paths.

## [1.0.6] - 2025-02-01

### Added

- Stable baseline release published to npm.
