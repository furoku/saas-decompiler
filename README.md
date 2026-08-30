# SaaS Decompiler

**Reverse-engineer SaaS from pixels to business logic.**

A multilingual prompt library for reconstructing the observable structure of SaaS products from screenshots, public pages, accessible product behavior, and public documentation.

> “Decompile” here means product analysis: infer how a SaaS is designed from evidence users can lawfully observe. This project is **not** intended to bypass authentication, extract private source code, discover secrets, evade access controls, or copy proprietary implementation details.

## Languages

- [English](README.en.md)
- [日本語](README.ja.md)
- [한국어](README.ko.md)
- [繁體中文](README.zh-TW.md)
- [简体中文](README.zh-CN.md)

## Prompt library

- [English](prompts/en.md)
- [日本語](prompts/ja.md)
- [한국어](prompts/ko.md)
- [繁體中文](prompts/zh-TW.md)
- [简体中文](prompts/zh-CN.md)

## What it covers

40 reusable prompt patterns covering product strategy, UI/UX, design systems, frontend architecture, data models, user flows, state machines, business rules, authentication and permissions, billing, onboarding, AI SaaS, APIs, integrations, notifications, admin consoles, security, growth, MVP planning, and implementation specifications.

The core method is:

**Pixel → Component → Screen → Flow → Feature → Data → Rule → System → Business**

## How to use

1. Pick the closest prompt category.
2. Give the model a URL, screenshots, product video, public documentation, or other observable evidence.
3. Ask it to separate **Observation**, **Inference**, and **Speculation**.
4. Use the result as input for product discovery, competitive analysis, prototyping, PRDs, or an independent implementation.

## Principles

- Reconstruct user-visible behavior, not hidden proprietary implementation.
- Prefer evidence-backed claims and confidence levels.
- Treat unknown internals as hypotheses, never facts.
- Build equivalent user value independently rather than cloning source code.
- Respect applicable law, terms of service, privacy, copyright, trademarks, and access controls.

## Project status

Prompt/reference repository. No runtime dependencies or executable application code.

Last verified: 2026-08-30.

## Security & privacy

Do not place credentials, API keys, private customer data, private source code, or other secrets into examples or issues. See [SECURITY.md](SECURITY.md).

## License

MIT License. See [LICENSE](LICENSE).