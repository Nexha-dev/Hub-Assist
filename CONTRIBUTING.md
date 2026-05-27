# Contributing to HubAssist

## Setup

```bash
# Install root dev tools (husky, lint-staged, commitlint)
npm install

# Husky hooks are installed automatically via the `prepare` script.
# If hooks are missing, run:
npx husky
```

## Git Hooks

Two hooks are enforced automatically:

- **pre-commit** — runs `lint-staged`, which applies ESLint + Prettier to all staged `.ts` / `.tsx` files in `backend/` and `frontend/`.
- **commit-msg** — runs `commitlint` to validate the commit message format.

## Commit Message Format

Commits must follow the [Conventional Commits](https://www.conventionalcommits.org/) spec:

```
<type>(<scope>): <subject>

# Examples
feat(auth): add biometric login endpoint
fix(bookings): correct total amount calculation
chore(ci): add contract-test job
docs(readme): update Docker usage section
```

Valid types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `perf`, `ci`, `build`, `revert`.

## Code Style

- TypeScript strict mode is enabled in both `backend/` and `frontend/`.
- ESLint and Prettier configs live in each package directory.
- Run `npm run lint` and `npm run format` inside `backend/` or `frontend/` before opening a PR.

## Pull Requests

1. Fork the repo and create a feature branch: `git checkout -b feat/your-feature`
2. Write tests for new functionality.
3. Ensure `npm run test:cov` passes in `backend/` and `npm run test:coverage` passes in `frontend/`.
4. Open a PR against `main` with a clear description of the change.
