# Contributing to GokturkFK

Thank you for your interest in contributing to **GokturkFK** open-source repositories.

## Workflow

1. **Open or claim an issue** before starting large changes so we can align on scope and architecture.
2. **Branch from `main`** using a clear prefix:
   - `feat/...` — new features
   - `fix/...` — bug fixes
   - `docs/...` — documentation improvements
   - `chore/...` — tooling, CI, or maintenance
3. **Keep pull requests focused** — one logical change per PR, with tests covering new behavior or bug fixes.
4. **Verify locally** before opening a PR:
   - Go repositories: `go build ./... && go vet ./... && go test -race ./...` (and `golangci-lint` where configured)
   - Python repositories: `pytest` (and `ruff check .` where configured)
5. **Linear history:** Protected branches merge via **squash** after all required CI checks pass.

## Security & Privacy Rules

- **Never** commit secrets, API keys, tokens, credentials, private keys, or `.env` files.
- **Never** disclose security vulnerabilities in public issues or PRs — follow [`SECURITY.md`](SECURITY.md).
- Respect wire-contract stability in shared libraries (such as `gokturk-core`).

## Code of Conduct

All contributors and maintainers are expected to follow our [Code of Conduct](CODE_OF_CONDUCT.md).
