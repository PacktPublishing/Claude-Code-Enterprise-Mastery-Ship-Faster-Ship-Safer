---
name: deploy
description: Runs the deployment checklist before deploying
disable-model-invocation: true
---

# Deploy Skill

Execute the full deployment checklist before deploying to staging or production.

## Pre-Deploy Checklist

1. **Check for uncommitted changes**
   - Run `git status`
   - If there are uncommitted changes, STOP and report them
   - All changes must be committed before deployment

2. **Run tests**
   - Execute `npm test`
   - If ANY test fails, STOP and report the failures
   - All tests must pass before deployment

3. **Run build**
   - Execute `npm run build`
   - If build fails, STOP and report the errors

4. **Check branch**
   - Verify we are on the correct branch for deployment
   - Staging: `main` branch
   - Production: tagged release

5. **Log deployment**
   - Create or append to `deploy-log.txt` with:
     - Timestamp (ISO 8601)
     - Git commit hash (`git rev-parse HEAD`)
     - Branch name
     - Deploying user (from git config)
     - Status: SUCCESS or FAILED

## Output

Report the deployment status:
- All checks passed → "Ready to deploy. Deployment logged."
- Any check failed → "Deployment blocked. See issues above."
