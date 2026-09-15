# Package: API

## Structure
- Routes: `src/routes/` — Express route handlers
- Services: `src/services/` — Business logic layer
- Middleware: `src/middleware/` — Auth, logging, error handling
- Database: `src/db/` — Schema and migrations

## Conventions
- Routes use kebab-case URLs: `/api/team-metrics`
- All route handlers must have try-catch error handling
- Database access ONLY through service layer — never in routes
- Response format: `{ data, error, meta }`
- Input validation before passing to service layer

## Testing
- Test files: `tests/routes/` and `tests/services/`
- Use supertest for route testing
- Mock database for unit tests
- Run: `npm test --workspace=packages/api`
