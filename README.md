# Maxim Gagiev

**I build the production LLM, voice, and security systems businesses run on.**
Co-founder of [MYG Media](https://myg-media.com), Vienna. Anthropic **Claude Certified Architect**.

[![Portfolio](https://img.shields.io/badge/Portfolio-0a0a0a?style=flat-square&logo=cloudflare&logoColor=F38020)](https://maxim-gagiev.pages.dev)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/maxim-gagiev/)
[![Email](https://img.shields.io/badge/max@myg--media.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:max@myg-media.com)

## Merged upstream

Bugs I found and fixed in libraries much of the ecosystem ships, each reproduced on the published
release with a failing-then-passing test and merged by the maintainers:

**[PostCSS](https://github.com/postcss/postcss/pull/2135)** and its [parser tests](https://github.com/postcss/postcss-parser-tests/pull/32) (merged by its author Andrey Sitnik) · **[immer](https://github.com/immerjs/immer/pull/1289)** (by Mark Erikson) · **[jose](https://github.com/panva/jose/pull/895)** (by Filip Skokan) · **[Cloudflare workers-sdk](https://github.com/cloudflare/workers-sdk/pull/15151)** · **[commitlint](https://github.com/conventional-changelog/commitlint/pull/4968)** · **[PapaParse](https://github.com/mholt/PapaParse/pull/1140)** · **[js-base64](https://github.com/dankogai/js-base64/pull/192)**

More in review at highlight.js, multiformats, firecrawl/pdf-inspector, and others. Most were found
by testing a library against the thing it claims to obey (an RFC, a reference implementation, exact
arithmetic) rather than against its own test suite.

## Featured

**[Urfael](https://github.com/maximilliangrand/urfael)** · a blast-radius-first AI assistant. Zero TCP ports, untrusted turns run no-egress and read-only, plugins load in a `--network none` container. `npm run security` attacks the live daemon and prints a table: 11/11 real-world attack classes resisted, ~1,400 tests, zero runtime deps.

**[consilium](https://github.com/maximilliangrand/consilium)** · deterministic orchestration for LLM agent councils: fan out independent hypotheses, adversarially refute each, converge on the survivors. Zero deps, model-agnostic, every pattern unit-testable with a mock.

**[Rustchain](https://github.com/maximilliangrand/rustchain)** · a blockchain from scratch in Rust: heaviest-work consensus with difficulty retargeting and median-time-past, real TCP peer-to-peer, canonical hashing, property + fuzz + multi-node tests, a threat model, 115 tests, clippy clean at `-D warnings`.

Also: **[Forge](https://github.com/maximilliangrand/forge)** (local GPU AI media tooling), **[BrainVault](https://github.com/maximilliangrand/brainvault)**, **[OpenBuild](https://github.com/maximilliangrand/openbuild)**, **[Code Translator](https://github.com/maximilliangrand/code-translator)**.

## Stack

`TypeScript` `Python` `Rust` · `Node` `Next.js` `Electron` `Tauri` · MCP servers and agentic systems, RAG, ElevenLabs voice · post-quantum readiness (FIPS 203/204/205), agent red-teaming, sandbox and capability design

<sub>Vienna, Austria · English / German / Russian · Overwatch Top 500, former pro-league competitor</sub>
