# golangci-lint

A template `.golangci.yml` (config `version: "2"`) for [golangci-lint](https://golangci-lint.run/), used across Go projects. The repository holds only the config, a `.gitignore` and the license; there is no Go code.

## Usage

Copy `.golangci.yml` to the root of a Go module and run:

```bash
golangci-lint run ./...
golangci-lint fmt ./...
```

Adjust these placeholders first:

- `run.go` is `'1.25.1'`; match your project's Go version.
- `formatters.settings.goimports.local-prefixes` is the placeholder `github.com/username/repo`; replace it with your module path.

## Contents

- **Run settings** — 5 minute timeout, auto-detected concurrency, tests included, read-only module downloads, text output with linter names and colors.
- **Formatters** — `goimports` and `golines` (max line length 120).
- **Exclusions** — generated code (lax), `vendor/`, `third_party/`.
- **Linters** — `govet` (strict `shadow`), `staticcheck`, `unused`, `goconst`, `godoclint`, `sloglint`, `misspell`, `gosec`, `bidichk`, `bodyclose`, `sqlclosecheck`, `rowserrcheck`, `errorlint`, `errcheck`, `nilerr`, `nilnil`, `dupl`, `nestif`, `ineffassign`, `revive`, `gocritic`, `unconvert`, `wastedassign`, `usestdlibvars`, `contextcheck`, `noctx`.
- **Staticcheck** — all checks except `SA1019`, `ST1000`, `ST1003`, `ST1016`.

## License

GNU General Public License v3.0 (see [LICENSE](LICENSE)).
