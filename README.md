<picture>
  <source media="(max-width: 640px) and (prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ancongui/ancongui/main/assets/hero-narrow-dark.svg">
  <source media="(max-width: 640px)" srcset="https://raw.githubusercontent.com/ancongui/ancongui/main/assets/hero-narrow-light.svg">
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ancongui/ancongui/main/assets/hero-dark.svg">
  <img src="https://raw.githubusercontent.com/ancongui/ancongui/main/assets/hero-light.svg" alt="Andrés Contreras Guillén. Founder and Technology Lead of Firefly Software and the Firefly Software Foundation. Frameworks, AI, and banking technology." width="100%">
</picture>

## I design the architecture and write the software

I'm the founder and technology lead of **Firefly Software** and the **Firefly Software Foundation**. My public engineering work lives across [fireflyframework](https://github.com/fireflyframework) and [firefly-oss](https://github.com/firefly-oss): application frameworks, tools for AI and software delivery, and the business modules behind banking operations.

I work on the internals as well as the applications: dependency injection, domain contracts, event-driven services, persistence, security, and orchestration. The repositories below show the implementations, tests, and tradeoffs behind that work.

[Firefly Framework](https://fireflyframework.org/) · [Firefly Software](https://fireflysoftware.io/) · [LinkedIn](https://www.linkedin.com/in/andrescontrerasguillen/)

## Application architecture across five languages

The Firefly Framework family shares an approach to application structure while following each native stack. I work on its technical direction and implementation, including how business code stays separate from transport and infrastructure.

| Framework | Stack | Start with the code |
| --- | --- | --- |
| **jafly** | Java, Spring Boot, WebFlux | [Module catalog](https://github.com/fireflyframework/.github/blob/main/docs/MODULE_CATALOG.md) · [Parent project](https://github.com/fireflyframework/fireflyframework-parent) |
| **pyfly** | Python, Starlette or FastAPI | [Framework](https://github.com/fireflyframework/fireflyframework-pyfly) · [Wallet and ledger sample](https://github.com/fireflyframework/fireflyframework-pyfly/tree/main/samples/lumen) |
| **larafly** | PHP, Laravel | [Framework](https://github.com/fireflyframework/fireflyframework-php) · [Wallet and ledger sample](https://github.com/fireflyframework/fireflyframework-php/tree/main/samples/lumen) |
| **rsfly** | Rust, Tokio, Axum | [Framework](https://github.com/fireflyframework/fireflyframework-rust) |
| **netfly** | C#, ASP.NET Core | [Framework](https://github.com/fireflyframework/fireflyframework-dotnet) |

Capabilities and release maturity vary by implementation. Each repository documents its supported behavior.

## AI applications, delivery, and business processes

I built **[Firefly Agentic](https://github.com/fireflyframework/fireflyframework-agentic)** on Pydantic AI to give applications a foundation for agents, with tools, memory, retrieval, and validation. [Explore the implementation](https://github.com/fireflyframework/fireflyframework-agentic/tree/main/fireflyframework_agentic).

I’m building **[Firefly Forge](https://github.com/fireflyframework/firefly-forge)** as a software factory for pyfly and larafly, bringing product definition and coding-agent tasks together with verification and delivery. [Firefly Agent Bridge](https://github.com/fireflyframework/firefly-agent-bridge) connects applications to coding CLIs through scoped jobs and resumable workflows.

With **[Firefly Weave](https://github.com/fireflyframework/firefly-weave)**, I work on processes that cross services and involve people, including persisted execution history, waits, and human tasks. [Source](https://github.com/fireflyframework/firefly-weave/tree/main/src/firefly_weave) · [Examples](https://github.com/fireflyframework/firefly-weave/tree/main/examples).

I also build applications on these foundations: **[FlyCanon](https://github.com/fireflyframework/flycanon)** for knowledge with source provenance and cited answers, and **[FlyQuery](https://github.com/fireflyframework/flyquery)** for structured-file analytics with inspectable SQL.

## Banking technology in the open

Through Firefly Software, I work on **OpenPlatform** business modules and their integration with existing financial systems. Public repositories cover customer management, accounts, payments, lending, and shared services.

A few places to inspect the engineering:

- [Customer management](https://github.com/firefly-oss/core-common-customer-mgmt): customer data and lifecycle capabilities.
- [Accounts](https://github.com/firefly-oss/core-banking-accounts) and [ledger](https://github.com/firefly-oss/core-banking-ledger): banking services with separate core, model, interface, SDK, and web modules.
- [Loan origination](https://github.com/firefly-oss/core-lending-loan-origination) and [servicing](https://github.com/firefly-oss/core-lending-loan-servicing): the work around lending products.

[Explore Firefly OpenPlatform](https://github.com/firefly-oss) · [My account-service contributions](https://github.com/firefly-oss/core-banking-accounts/commits/main/?author=ancongui)

## A closer look at the implementation

These parts of the code show how I approach problems that come up across applications:

- **Composition and contracts:** pyfly's [container](https://github.com/fireflyframework/fireflyframework-pyfly/tree/main/src/pyfly/container) and [domain primitives](https://github.com/fireflyframework/fireflyframework-pyfly/tree/main/src/pyfly/domain).
- **Transactions and messaging:** larafly's [orchestration](https://github.com/fireflyframework/fireflyframework-php/tree/main/packages/orchestration) and [database event adapter](https://github.com/fireflyframework/fireflyframework-php/tree/main/packages/eda-database).
- **Executable learning material:** the [pyfly book and companion service](https://github.com/fireflyframework/fireflyframework-pyfly/tree/main/book) and [larafly's documentation checks](https://github.com/fireflyframework/fireflyframework-php/blob/main/tests/DocsCodeIsRealTest.php).

The [book collection](https://fireflyframework.org/#books) covers jafly, pyfly, larafly, and rsfly in English and Spanish. I treat examples and documentation as part of the engineering: readers should be able to follow an idea into working code.

I've worked in software since 2009 and AI and Big Data since 2012. Alongside Firefly, I'm Chief Technology Officer at [Signature Management Consultants](https://www.signature.com.es/).

**Contact:** [andres.contreras@fireflysoftware.io](mailto:andres.contreras@fireflysoftware.io) · Orange, Orange County, US
