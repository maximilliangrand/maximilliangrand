# Maxim Gagiev

**I build the production LLM, voice, and security systems businesses run on.**
Co-founder of [MYG Media](https://myg-media.com) in Vienna: voice agents answering real
clinic and club phone lines, post-quantum tooling, and the automation behind them.

[![Portfolio](https://img.shields.io/badge/Portfolio-0a0a0a?style=flat-square&logo=cloudflare&logoColor=F38020)](https://maxim-gagiev.pages.dev)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/maxim-gagiev/)
[![Email](https://img.shields.io/badge/max@myg--media.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:max@myg-media.com)
&nbsp;·&nbsp; Anthropic **Claude Certified Architect**

Most client work is private, so what is public here is the systems work: security,
cryptography, tools I wanted to exist, and fixes upstreamed into libraries you already ship.

## Merged upstream

Bugs I found and fixed in libraries a large part of the ecosystem depends on. Each was
reproduced against the published release and shipped with a test that fails before the fix and
passes after, and merged by the maintainers themselves.

- **[PostCSS](https://github.com/postcss/postcss/pull/2135)** and its **[parser tests](https://github.com/postcss/postcss-parser-tests/pull/32)** · a rule end-offset that shifted when whitespace preceded the semicolon · merged by Andrey Sitnik, the author of PostCSS
- **[immer](https://github.com/immerjs/immer/pull/1289)** · structural sharing silently lost on no-op array mutations, defeating memoization · merged by Mark Erikson
- **[jose](https://github.com/panva/jose/pull/895)** · a JWE the library produced but could not decrypt back, against RFC 7516 · merged by Filip Skokan
- **[Cloudflare workers-sdk](https://github.com/cloudflare/workers-sdk/pull/15151)** · wrangler misparsing trailing commas in config · merged
- **[commitlint](https://github.com/conventional-changelog/commitlint/pull/4968)** · scoped `conventional-changelog` presets whose parser options were silently dropped · merged
- **[PapaParse](https://github.com/mholt/PapaParse/pull/1140)** · Date values mangled on unparse · merged
- **[js-base64](https://github.com/dankogai/js-base64/pull/192)** · a one-character surrogate-range typo that corrupted Unicode round-trips · merged

More reproduced fixes are in review at **highlight.js**, **multiformats**, **firecrawl/pdf-inspector**,
**n8n-mcp**, **hyperresearch**, and **d3-array**. Most were found by testing a library against the
thing it claims to obey (an RFC, a reference implementation, exact arithmetic) rather than against
its own test suite.

## Featured

**[Urfael](https://github.com/maximilliangrand/urfael)** · `JavaScript · Electron · MCP` · MIT
A self-hosted, voice-capable AI assistant built blast-radius-first. The brain listens on a unix
socket with **zero TCP ports**, untrusted turns run a no-egress read-only profile, and plugins
load as data inside a `--network none` container, sha-pinned at consent.

It ships a security claim you can run instead of read:

```bash
npm run security   # boots the real daemon, attacks it, prints a pass/fail table
# → 11/11 real-world attack classes resisted · 128/128 checks passed
```

28,000 lines of source across 130 modules, **zero runtime dependencies**, ~1,400 passing tests.

**[consilium](https://github.com/maximilliangrand/consilium)** · `TypeScript` · MIT
Deterministic orchestration for LLM agent councils. Fan out independent hypotheses, adversarially
refute each, converge on the survivors: reliability from structure, not a bigger model. Zero runtime
dependencies, model-agnostic behind one runner seam, and every pattern is unit-testable with a mock,
no API key required.

**[Rustchain](https://github.com/maximilliangrand/rustchain)** · `Rust`
A blockchain from scratch with no framework: ed25519 signatures, proof-of-work with difficulty
retargeting, heaviest-work fork choice with median-time-past, Merkle trees, a wallet, and real
length-prefixed TCP peer-to-peer. Hardened to be verified rather than trusted: canonical hashing,
a panic-free library under a clippy deny gate, property and fuzz tests, a multi-node reconvergence
test over real sockets, a threat model, and CI. 115 tests, clippy clean at `-D warnings`.

**[Forge](https://github.com/maximilliangrand/forge)** · `TypeScript · Electron`
Bulk media tooling: AI image and video upscaling, batch compression, audio conversion.
GPU-accelerated, entirely local, no uploads or accounts. Shipped for macOS, Windows and Linux.

## Also built

**[BrainVault](https://github.com/maximilliangrand/brainvault)** · local-first notes with wiki links and a graph view; nothing leaves your machine · `Tauri`
**[OpenBuild](https://github.com/maximilliangrand/openbuild)** · open-source drag-and-drop website builder with one-click deploy · `Vue`
**[Code Translator](https://github.com/maximilliangrand/code-translator)** · translates code between languages across AI providers, with a VS Code extension · `Python`
**[StartupCouncilAI](https://github.com/maximilliangrand/StartupCouncilAI)** · a panel of AI advisors that debate a business question and return a synthesis · `Next.js`
**[GREMLIN](https://github.com/maximilliangrand/gremlin)** · a voice AI that interrupts your coding session with absurd feature demands · `Python`

## Stack

`TypeScript` `Python` `Rust` · `Node` `Next.js` `Electron` `Tauri` · `PostgreSQL` `Docker` `Cloudflare`

**AI:** LLM orchestration (Claude, GPT, Gemini), MCP servers and clients, agentic systems, RAG,
ElevenLabs conversational voice
**Security:** post-quantum readiness (NIST FIPS 203/204/205, CNSA 2.0), adversarial red-teaming
of agent systems, prompt-injection containment, sandbox and capability design

---

<sub>Vienna, Austria · German / English / Russian · Overwatch Top 500, former pro-league competitor</sub>
