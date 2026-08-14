# Maxim Gagiev

**I build the production LLM, voice, and security systems businesses run on.**
Co-founder of [MYG Media](https://myg-media.com) in Vienna: voice agents answering real
clinic and club phone lines, post-quantum tooling, and the automation behind them.

[![Portfolio](https://img.shields.io/badge/Portfolio-0a0a0a?style=flat-square&logo=cloudflare&logoColor=F38020)](https://maxim-gagiev.pages.dev)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/maxim-gagiev/)
[![Email](https://img.shields.io/badge/max@myg--media.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:max@myg-media.com)
&nbsp;·&nbsp; Anthropic **Claude Certified Architect**

Most client work is private, so what is public here is the systems work: security,
cryptography, and tools I wanted to exist.

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

**[Rustchain](https://github.com/maximilliangrand/rustchain)** · `Rust`
A blockchain from scratch with no framework: ed25519 signatures, proof-of-work consensus,
Merkle trees, a wallet, and peer-to-peer networking. Signature verification binds the signing
key to the sender's address, so a valid signature from an unrelated key is refused.

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
