<picture>
  <source media="(max-width: 640px) and (prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ancongui/ancongui/f82f45890bb7bad0189e2a7cc81d5afe6ca3d69c/assets/hero-narrow-dark.svg">
  <source media="(max-width: 640px)" srcset="https://raw.githubusercontent.com/ancongui/ancongui/f82f45890bb7bad0189e2a7cc81d5afe6ca3d69c/assets/hero-narrow-light.svg">
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ancongui/ancongui/f82f45890bb7bad0189e2a7cc81d5afe6ca3d69c/assets/hero-dark.svg">
  <img src="https://raw.githubusercontent.com/ancongui/ancongui/f82f45890bb7bad0189e2a7cc81d5afe6ca3d69c/assets/hero-light.svg" alt="Andrés Contreras Guillén. Founder and Technology Lead of Firefly Software and the Firefly Software Foundation. CTO at Signature, working on Lean Transformation. I build application frameworks and AI for banking and insurance." width="100%">
</picture>

## I design the architecture and write the software

I started programming at eight with BASIC, Visual Basic, Batch, Bash, Perl, and PHP. I was a regular on security forums and at events in Spain, and a member of ka0labs. Understanding how systems worked and where they failed taught me a lot, but building software became the work I wanted to pursue.

In 2009, at fourteen, I began working on professional projects and with startups. As the projects grew, I moved into enterprise development and software architecture. I've worked in AI and Big Data since 2012. From 2015 to 2018, I was responsible for global AI innovation at everis (now NTT DATA), working as Head of AI & Robotics and Innovation Manager at everis NextGen. I developed AI virtual workers using machine learning and NLP to automate business processes. That experience informs the frameworks and financial software I build today.

I'm the founder and technology lead of **Firefly Software** and the **Firefly Software Foundation**. My public engineering work lives across [fireflyframework](https://github.com/fireflyframework) and [firefly-oss](https://github.com/firefly-oss): application frameworks, tools for AI and software delivery, and technology for banking and insurance operations.

I work on the internals as well as the applications: dependency injection, domain contracts, event-driven services, persistence, security, and orchestration. The repositories below show the implementations, tests, and tradeoffs behind that work.

[Firefly Framework](https://fireflyframework.org/) · [Firefly Software](https://fireflysoftware.io/) · [LinkedIn](https://www.linkedin.com/in/andrescontrerasguillen/)

## The engineering problems I work on

**Distributed transactions.** I work on Java's reactive Saga and TCC engines: ordering dependent steps, coordinating reservations, and compensating when part of an operation fails. The failure paths matter as much as the successful execution. [Saga implementation](https://github.com/fireflyframework/fireflyframework-orchestration/blob/main/src/main/java/org/fireflyframework/orchestration/saga/engine/SagaEngine.java) · [TCC tests](https://github.com/fireflyframework/fireflyframework-orchestration/blob/main/src/test/java/org/fireflyframework/orchestration/unit/tcc/TccEngineTest.java).

**Processes that survive interruption.** In [Firefly Weave](https://github.com/fireflyframework/firefly-weave), I work across the workflow compiler and durable execution model, including worker coordination and recovery. Its recovery matrix covers process restarts, lost external responses, and acknowledgement boundaries. Weave is currently an alpha. [Compiler](https://github.com/fireflyframework/firefly-weave/tree/main/src/firefly_weave/compiler) · [Recovery tests](https://github.com/fireflyframework/firefly-weave/blob/main/tests/e2e/test_recovery_matrix.py).

**Infrastructure for AI applications.** I built [Firefly Agentic](https://github.com/fireflyframework/fireflyframework-agentic) on Pydantic AI and work on the layers around model calls: memory, tools, validation, and pipeline execution. The pipeline engine handles dependency scheduling, parallel work, and checkpoint resume. [Pipeline engine](https://github.com/fireflyframework/fireflyframework-agentic/blob/main/fireflyframework_agentic/pipeline/engine.py) · [Memory implementation](https://github.com/fireflyframework/fireflyframework-agentic/tree/main/fireflyframework_agentic/memory).

**AI-assisted software delivery.** I’m building [Firefly Forge](https://github.com/fireflyframework/firefly-forge) around retained source, executable verification, and explicit publication decisions. A difficult part is deciding whether evidence is still valid when code, policy, or access changes. [Architecture](https://github.com/fireflyframework/firefly-forge/blob/main/docs/architecture.md) · [Evidence and authority tests](https://github.com/fireflyframework/firefly-forge/blob/main/tests/test_learning_cached_authority.py).

**Financial behavior under failure.** I use the Lumen wallet and ledger applications to exercise the frameworks against concrete financial rules. Tests cover a failed credit step restoring balances, and an outbox event committing or rolling back with its transfer. [Python saga tests](https://github.com/fireflyframework/fireflyframework-pyfly/blob/main/samples/lumen/tests/test_money_transfer_saga.py) · [PHP transaction and outbox tests](https://github.com/fireflyframework/fireflyframework-php/blob/main/samples/lumen/tests/Outbox/OutboxSameTransactionTest.php).

I also build [FlyCanon](https://github.com/fireflyframework/flycanon), for knowledge with source provenance and cited answers, and [FlyQuery](https://github.com/fireflyframework/flyquery), for structured-file analytics with inspectable SQL. [Firefly Agent Bridge](https://github.com/fireflyframework/firefly-agent-bridge) connects applications to coding CLIs through scoped jobs and resumable workflows.

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

## Banking and insurance technology

Through Firefly Software, I work on **OpenPlatform** business modules and their integration with existing financial systems. Public repositories cover customer management, accounts, payments, lending, and shared services.

Firefly's services also cover insurance operations, including underwriting support, policy and claims work. Those implementations connect to insurers' existing systems; native insurance capabilities are being developed.

A few places to inspect the engineering:

- [Customer management](https://github.com/firefly-oss/core-common-customer-mgmt): customer data and lifecycle capabilities.
- [Accounts](https://github.com/firefly-oss/core-banking-accounts) and [ledger](https://github.com/firefly-oss/core-banking-ledger): banking services with separate core, model, interface, SDK, and web modules.
- [Loan origination](https://github.com/firefly-oss/core-lending-loan-origination) and [servicing](https://github.com/firefly-oss/core-lending-loan-servicing): the work around lending products.

[Explore Firefly OpenPlatform](https://github.com/firefly-oss) · [My account-service contributions](https://github.com/firefly-oss/core-banking-accounts/commits/main/?author=ancongui)

## How I make the work usable

The [book collection](https://fireflyframework.org/#books) covers jafly, pyfly, larafly, and rsfly in English and Spanish. I work on the examples and documentation alongside the implementation. Readers can follow the ideas into companion services and the tests that exercise them, including [larafly's documentation checks](https://github.com/fireflyframework/fireflyframework-php/blob/main/tests/DocsCodeIsRealTest.php).

## Strategy, transformation, and delivery

<a href="https://www.signature.com.es/">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ancongui/ancongui/f82f45890bb7bad0189e2a7cc81d5afe6ca3d69c/assets/signature-wordmark-dark.svg">
    <img src="https://raw.githubusercontent.com/ancongui/ancongui/f82f45890bb7bad0189e2a7cc81d5afe6ca3d69c/assets/signature-wordmark-light.svg" alt="Signature Management Consultants" width="200">
  </picture>
</a>

Alongside Firefly, I'm **Chief Technology Officer at [Signature Management Consultants](https://www.signature.com.es/)**, where I lead the firm's technology capability and Forward Deployment practice.

My work in Lean Transformation brings business leaders and engineering teams together to turn strategic priorities into changes the organization can put into practice. That includes diagnosing what limits performance, redesigning processes, and deciding how AI, data, and existing systems can support the transformation.

I stay involved through architecture and implementation, helping teams bring the system into production and take ownership of it. The work connects business judgment with hands-on engineering: the operating model and the code have to work together. [Transformation practice](https://www.signature.com.es/capacidades/transformacion) · [Technology capabilities](https://www.signature.com.es/capacidades/digital).

**Contact:** [andres.contreras@fireflysoftware.io](mailto:andres.contreras@fireflysoftware.io) · Orange, Orange County, US
