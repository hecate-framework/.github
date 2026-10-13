<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/hecate-framework/.github/main/brand/assets/Social/readme-banner-on-dark.png">
  <img alt="hecate — contract-first web APIs for Lua 5.5" src="https://raw.githubusercontent.com/hecate-framework/.github/main/brand/assets/Social/readme-banner.png">
</picture>

hecate is a modular, contract-first framework for building HTTP APIs in
[Lua 5.5](https://www.lua.org/). It is one framework rather than an assembly of
libraries: one version number, one set of conventions, one vocabulary and one
command-line tool, from the Lua toolchain to the database driver.

> **Status: specification stage.** The design is written and the foundation package
> (`hecate-core`) is being implemented. No release is usable in production yet.
> Design feedback is as welcome as code.

## What it is

You declare a route and its schemas once, as plain Lua data. Validation, the OpenAPI
contract, the API reference and contract tests are derived from that single
declaration.

```lua
local hecate = require "hecate"
local schema = require "hecate.schema"

local health = hecate.routes "health"

health:get "/health" {
  summary   = "Liveness probe",
  responses = { [200] = schema.object { status = schema.literal "ok" } },
  action    = function(request) return { status = "ok" } end,
}

return health
```

Handlers read like sequential code. I/O suspends the current coroutine on a libuv
reactor, and explicit primitives (`fork`, `join`, `select`, `deadline`) are there when
you want concurrency on purpose. *The example is illustrative: names are settled by the
specifications.*

The principles, in short:

1. **One framework.** Every package shares one object model, error model and release cycle.
2. **Contract-first.** Routes and schemas are runtime data; contracts and docs derive from them.
3. **Object-oriented, by choice.** Classes, traits and interfaces for large code; light route modules for small services.
4. **Transparent concurrency.** Coroutines on a reactor, structured concurrency.
5. **Academic vocabulary.** *Future*, *reactor*, *refinement type*, *unit of work*: names from the literature.
6. **Measured performance.** Benchmarks run in CI; regressions block releases.
7. **Documentation is part of the product.** No feature ships without its reference.
8. **Cross-platform.** Linux, macOS and Windows are first-class.

## Where to find things

All development happens in one monorepo:
**[hecate-framework/hecate](https://github.com/hecate-framework/hecate)**.

| You want to… | Go to |
|---|---|
| Understand the goals and non-goals | [`docs/vision.md`](https://github.com/hecate-framework/hecate/blob/main/docs/vision.md) |
| See what using hecate will feel like | [`docs/developer-experience.md`](https://github.com/hecate-framework/hecate/blob/main/docs/developer-experience.md) |
| Learn the vocabulary | [`docs/glossary.md`](https://github.com/hecate-framework/hecate/blob/main/docs/glossary.md) |
| Read the architecture, area by area | [`docs/architecture/`](https://github.com/hecate-framework/hecate/tree/main/docs/architecture) |
| Know why a decision was made | [`docs/adr/`](https://github.com/hecate-framework/hecate/tree/main/docs/adr) (Architecture Decision Records) |
| Know what comes next | [`docs/roadmap.md`](https://github.com/hecate-framework/hecate/blob/main/docs/roadmap.md) and [`docs/open-questions.md`](https://github.com/hecate-framework/hecate/blob/main/docs/open-questions.md) |
| Browse the packages and their status | [`packages/README.md`](https://github.com/hecate-framework/hecate/blob/main/packages/README.md) |
| Follow the changes | [`CHANGELOG.md`](https://github.com/hecate-framework/hecate/blob/main/CHANGELOG.md) |
| Contribute | [`CONTRIBUTING.md`](https://github.com/hecate-framework/hecate/blob/main/CONTRIBUTING.md) |
| Report a bug or ask a design question | [Issues](https://github.com/hecate-framework/hecate/issues/new/choose) on the monorepo |
| Report a vulnerability | [Private security advisory](https://github.com/hecate-framework/hecate/security/advisories/new), never a public issue |
| Point an AI assistant at the project | [`llms.txt`](https://github.com/hecate-framework/hecate/blob/main/llms.txt) |
| Use the logo or the colours | [`brand/`](https://github.com/hecate-framework/.github/tree/main/brand) in this organisation's `.github` repository |

## The packages

Each package is a LuaRocks rock. All share one version and require Lua 5.5. The
`hecate` rock pulls in the standard edition in one dependency.

| Layer | Packages |
|---|---|
| Foundation | `core` |
| Runtime | `reactor` · `net` · `json` · `log` |
| Protocol | `http` · `router` · `schema` |
| Framework | `config` · `container` · `kernel` · `openapi` |
| Data | `sql` · `query` · `postgresql` · `mysql` · `sqlite` · `redis` · `migration` · `orm` |
| Tooling | `cli` · `test` · `doc` |
| Planned | `websocket` · `security` · `template` · `mongodb` · `sqlserver` |

Repositories named `hecate-<package>` are **read-only mirrors** of the monorepo,
published so that each rock can be built and browsed on its own. Pull requests
opened on a mirror are closed automatically: open issues and pull requests in
[hecate-framework/hecate](https://github.com/hecate-framework/hecate).

## Repositories in this organisation

| Repository | Purpose |
|---|---|
| [`hecate`](https://github.com/hecate-framework/hecate) | The monorepo: specification, packages, tooling, website sources |
| `hecate-<package>` | Read-only mirrors, one per package |
| [`.github`](https://github.com/hecate-framework/.github) | This page, default community files and the visual identity |

<sub>MIT licensed. The name is always written in lowercase: hecate.</sub>
