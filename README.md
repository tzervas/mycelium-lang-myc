# mycelium-lang-myc

Self-hosted **presentation / re-export umbrella** for Mycelium **native `.myc`** component repos
(PROGRAM-SELFHOST-DECOMPOSE-2026-07-17 Phase R / dual-umbrella split).

<!-- FLEET-BADGES:BEGIN -->
[![CI](https://github.com/tzervas/mycelium-lang-myc/actions/workflows/fleet-ci.yml/badge.svg?branch=main)](https://github.com/tzervas/mycelium-lang-myc/actions/workflows/fleet-ci.yml?query=branch%3Amain)
[![Security](https://github.com/tzervas/mycelium-lang-myc/actions/workflows/fleet-security.yml/badge.svg?branch=main)](https://github.com/tzervas/mycelium-lang-myc/actions/workflows/fleet-security.yml?query=branch%3Amain)
[![Runner](https://img.shields.io/badge/runs--on-self--hosted%20podman-informational)](https://github.com/tzervas/gha-runner-ctl)
<!-- FLEET-BADGES:END -->

## What this is

A clean entry point that **pins** `*-myc` sibling SHAs (see [`components.lock`](./components.lock))
and documents the native language surface without browsing the historical monorepo.

| Field | Value |
|---|---|
| **Monorepo archive** | `tzervas/mycelium` tag `archive/main-pre-component-transpile-2026-07-17` @ `aad96b7a425710db5e91094d4fc2ca21a129e41a` |
| **Rust train umbrella** | [`tzervas/mycelium-lang`](https://github.com/tzervas/mycelium-lang) (transitional until native ports are stable) |
| **Component map** | monorepo `docs/planning/gap-analysis-2026-07-16/COMPONENT-REPO-MAP-DRAFT.md` |
| **Honesty** | Umbrella is operational wiring; not DN-88 production-ready dogfood; not a SemVer 1.0 claim |
| **Pins** | 46 `*-myc` pins in `components.lock` — **Declared** seed/delivery pins (see each repo `DELIVERY.md`) |

## Component groups (native)

- **Kernel:** mycelium-core-myc, mycelium-value-myc, mycelium-runtime-myc, mycelium-l1-myc, mycelium-codegen-myc
- **Std:** mycelium-std-*-myc
- **Tooling:** mycelium-check-myc, mycelium-transpile-myc, mycelium-cli-myc, …
- **Compiler surface:** mycelium-compiler-myc (`lib/compiler`)

## Pin policy

`components.lock` records each component tip SHA. Update pins only via PR here;
CI should verify pins resolve (future).

## CI

Workflows run on **self-hosted** runners managed by [`gha-runner-ctl`](https://github.com/tzervas/gha-runner-ctl)
(`runs-on: [self-hosted, linux, x64, podman]`). Badges above report status for **this branch**.

## Relation to monorepo / Rust train

The monorepo `tzervas/mycelium` remains the **archive + active development** trunk until cutover.
Rust components stay under `mycelium-lang` until native ports are stable enough to archive the Rust train.
