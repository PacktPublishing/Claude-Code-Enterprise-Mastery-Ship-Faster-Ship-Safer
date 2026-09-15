# Project: [YOUR PROJECT NAME]

## Architecture
- [Monorepo / Single repo] with [package manager]
- Packages: [list your packages/modules]
- Tech stack: [TypeScript/Python/etc], [framework], [database]
- Entry point: [main file path]

## Coding Standards
- TypeScript strict mode — no `any` types
- No `console.log` in production code — use the logger middleware
- All functions must have explicit return types
- Import order: external packages → internal packages → relative imports
- Error handling: all async operations must have try-catch

## Testing Requirements
- All PRs require tests — minimum 80% coverage
- Test file naming: `*.test.ts` alongside source files
- Run tests: `npm test`
- Integration tests required for all API endpoints

## PR Format
- Title: `[TEAM-xxx] Short description`
- Description must include: what changed, why, how to test
- All CI checks must pass before merge
- Minimum 1 approving review required

## API Conventions (if applicable)
- RESTful endpoints with kebab-case URLs
- Response wrapper: `{ data, error, meta }`
- Input validation on all endpoints
- Authentication via middleware — never skip auth

## Common Mistakes
- [List mistakes specific to your codebase]
- Forgetting try-catch in route handlers
- Using string interpolation in SQL queries (use parameterized queries)
- Committing debug logging or hardcoded keys

## Deployment
- Staging: auto-deploys from `main` branch
- Production: requires manual approval + passing CI
- Never deploy on Fridays
- Rollback procedure: [document yours]
