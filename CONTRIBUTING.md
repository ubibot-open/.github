# Contributing to UbiBot Open

Thanks for considering a contribution! This file is the default contributing guide for every
repository under the `ubibot-open` org — an individual repo's own `CONTRIBUTING.md` (if it adds
one later) takes precedence over this one.

## The repositories

| Repo | What it is | Language/stack |
|---|---|---|
| [ubibot-open-server](https://github.com/ubibot-open/ubibot-open-server) | Device-facing backend + admin console | Go, React/TypeScript |
| [ubibot-open-ws1b](https://github.com/ubibot-open/ubibot-open-ws1b) | WS1B reference firmware | C, ESP-IDF |
| [ubibot-serial-sync](https://github.com/ubibot-open/ubibot-serial-sync) | Desktop serial debugging/provisioning tool | C++, Qt 6/QML |
| [ubibot-open-doc](https://github.com/ubibot-open/ubibot-open-doc) | Protocol spec and deployment/bring-up guide | Markdown |

Each repo's own `README.md` (and `BUILD.md`, where present) has the build/run instructions —
start there before opening a PR so your change actually builds locally first.

## Before you start

- **Bug fix or small change**: feel free to open a PR directly.
- **New feature or anything that changes behavior across repos** (e.g. a protocol change, a new
  API endpoint, a new admin-console page): please open an issue first to discuss the approach.
  This project intentionally stays minimal (see each repo's README for what's explicitly out of
  scope) — confirming direction first saves you a rewritten PR later.
- **Documentation-only changes**: go straight to a PR against
  [ubibot-open-doc](https://github.com/ubibot-open/ubibot-open-doc).

## Reporting bugs / requesting features

Open an issue on the specific repo the bug or request belongs to (not this `.github` repo, unless
it's about the org profile page itself). Use the issue templates where offered — at minimum,
include:

- What you did, what you expected, what actually happened.
- Repo version/commit, OS, and (for firmware/hardware issues) the device model and ESP-IDF
  version.
- Logs or error output where relevant (`idf.py monitor` output, server logs, browser console,
  etc.).

## Making a pull request

1. Fork the repo and create a branch off `main` (`git checkout -b fix/short-description`).
2. Make your change, following the existing code's style and comment density rather than
   introducing a new convention — match what's already there in the file you're editing.
3. Run the repo's own build and, where they exist, its tests, before opening the PR:
   - `ubibot-open-server`: `cd server && go build ./... && go test ./...`; if you touched the
     admin console, `cd admin && npm run lint`.
   - `ubibot-open-ws1b`: `idf.py build` (with ESP-IDF v6.0.2, target `esp32c5` — see the repo's
     README for setup).
   - `ubibot-serial-sync`: see the repo's `BUILD.md`.
4. Keep the PR focused — one logical change per PR is much easier to review than a bundle of
   unrelated fixes.
5. Write a clear PR description: what changed and why, and how you tested it. Link the issue it
   addresses, if any.
6. Push and open the PR against `main`. A maintainer will review it — expect some back-and-forth
   for anything non-trivial.

## Code style

There's no separate style guide beyond "match the surrounding code": comment density, naming, and
idiom should stay consistent within the file you're touching. A few stack-specific notes:

- **Go** (`ubibot-open-server/server`): standard `gofmt`/`go vet` cleanliness; table-driven tests
  where practical (see the existing `*_test.go` files for the pattern used).
- **React/TypeScript** (`ubibot-open-server/admin`): functional components + hooks, matching the
  existing `pages/`/`components/` structure; run `npm run lint` before submitting.
- **C/ESP-IDF** (`ubibot-open-ws1b`): match the existing file header/comment format and the
  `osi_*`/`mem_*` helper wrappers already used throughout `main/` rather than calling FreeRTOS/
  libc primitives directly where a wrapper already exists.
- **C++/Qt** (`ubibot-serial-sync`): see that repo's `BUILD.md` for its design notes and module
  layout before adding a new panel/feature.

## Licensing of your contribution

By submitting a contribution, you agree it's licensed under the same license as the repository
you're contributing to (see that repo's `LICENSE` file — currently Apache 2.0 for
`ubibot-open-server` and `ubibot-open-doc`, MIT for `ubibot-open-ws1b`, and LGPLv3 for
`ubibot-serial-sync`). No separate CLA is required.

## Getting help

Not sure where something belongs, or want to discuss an idea before writing code? Open an issue,
or ask in the community Discord linked from the [org profile](https://github.com/ubibot-open).

## Code of Conduct

This project follows the [Code of Conduct](CODE_OF_CONDUCT.md) — please read it before
participating.
