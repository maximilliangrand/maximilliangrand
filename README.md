# Maxim Gagiev

**AI and backend engineer based in Vienna.** I build LLM and voice applications, agent tooling, and the services behind them. Co-founder of [MYG Media](https://myg-media.com). Open to AI engineering and backend roles.

[Portfolio](https://maxim-gagiev.pages.dev) · [LinkedIn](https://www.linkedin.com/in/maxim-gagiev/) · [Email](mailto:max@myg-media.com)

## Selected Work

- **[Nightshift](https://github.com/maximilliangrand/nightshift)**: a supervisor for unattended agent processes, with runtime limits, usage metering, process cleanup, and run reports. Its failure-case suite and documentation cover platform and metering limitations.
- **[Urfael](https://github.com/maximilliangrand/urfael)**: a local personal assistant with persistent memory, voice, and restricted tool access for untrusted messages. Includes a threat model, automated tests, and a separately run live security benchmark. A personal project, not an independently audited security product.
- **[Rustchain](https://github.com/maximilliangrand/rustchain)**: an educational Rust blockchain with heaviest-work fork choice, signed transactions, property tests, and multi-node tests over TCP.

For client work, see [a support assistant built around grounding and human handoff](case-studies/support-assistant.md). The anonymized account explains my implementation responsibilities, why I used prompt caching instead of a vector database, and what the recorded evaluation does and does not establish.

## Accepted Upstream Contributions

I investigate reproducible failures, add regression tests, and work through maintainer review. Selected examples:

| Project | Contribution |
| --- | --- |
| [Hermes Agent](https://github.com/NousResearch/hermes-agent/pull/104805) | Preserve completed background-process results across a headless parent's exit. Commits incorporated via [#104949](https://github.com/NousResearch/hermes-agent/pull/104949), with maintainer follow-up fixes. |
| [jose](https://github.com/panva/jose/pull/895) | Recheck JWE header disjointness after generated key-management parameters are added, including the multi-recipient path. |
| [n8n-mcp](https://github.com/czlonkowski/n8n-mcp/pull/1040) | Align synchronous and asynchronous loopback validation. Incorporated with maintainer revisions via [#1056](https://github.com/czlonkowski/n8n-mcp/pull/1056). |
| [PostCSS](https://github.com/postcss/postcss/pull/2135) | Correct rule source offsets when whitespace precedes a trailing semicolon. |
| [Immer](https://github.com/immerjs/immer/pull/1289) | Preserve structural sharing for no-op array operations; refined and merged by the maintainer. |
| [Cloudflare workers-sdk](https://github.com/cloudflare/workers-sdk/pull/15151) | Fix the generated Wrangler configuration schema's placement of `allowTrailingCommas`. |

Also merged: [commitlint](https://github.com/conventional-changelog/commitlint/pull/4968), [PapaParse](https://github.com/mholt/PapaParse/pull/1140), [electron-builder](https://github.com/electron-userland/electron-builder/pull/10081), and [js-base64](https://github.com/dankogai/js-base64/pull/192).

## Tools and Languages

TypeScript / JavaScript, Python, Rust · Node.js, PostgreSQL, Next.js · LLM tool calling, prompt caching, agent memory, evaluation harnesses, and API integrations.

English · conversational German (B1/B2) · Russian
