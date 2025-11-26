# Repository Guidelines

## Pre-Action Checklist

Before suggesting ANY infrastructure, CI/CD, or tooling changes:

1. Run `ls .github/workflows/` to see existing workflows
2. Run `cat package.json | grep scripts -A 50` to see available commands
3. Check for `.qualityrc.json`, `CLAUDE.md`, or similar config files

## Build, Test, and Development Commands

- `npm run dev` — Start Next.js dev server
- `npm run build` — Production build
- `npm run lint` / `npm run lint:fix` — ESLint + Stylelint
- `npm run format` / `npm run format:check` — Prettier formatting
- `npm test` — Run Vitest tests
- `npm run test:unit` — Unit tests only
- `npm run test:integration` — Integration tests
- `npm run test:e2e` — Playwright E2E tests
- `npm run test:ci` — Full CI test suite
- `npm run test:all` — All test suites
- `npm run validate:all` — Comprehensive validation

## Quality Automation (create-quality-automation)

**IMPORTANT**: This project uses `create-quality-automation` for CI/CD quality gates. Before suggesting or creating ANY new GitHub Actions workflows for lint/test/security/formatting, you MUST first check:

1. `.github/workflows/quality.yml` — already exists and handles all quality checks
2. `.qualityrc.json` — CQA configuration file

**DO NOT** create duplicate workflows. The existing workflow already handles:

- ESLint with security rules
- Prettier formatting checks
- Stylelint for CSS
- Test execution
- Security audit (`npm audit`)
- Secret detection

**Available Commands** (use these instead of suggesting new workflows):

- `npm run validate:all` — Comprehensive validation
- `npm run validate:comprehensive` — Extended validation
- `npm run lint` / `npm run lint:fix` — Linting
- `npm run format:check` / `npm run format` — Formatting
- `npm run security:audit` — Dependency security check
- `npm run test:ci` — CI-optimized test suite

**Before proposing CI/CD changes**: Run `ls .github/workflows/` and `cat .github/workflows/quality.yml` to understand what already exists.
