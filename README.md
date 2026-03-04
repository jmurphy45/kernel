# **Kernel**

*Laravel semantics with Rust type safety*

Minimal, async-first Rust web framework inspired by Laravel, providing routing, controllers, middleware, configuration, and a CLI—all built with Rust’s performance and safety in mind.

---

## Table of Contents

* [Goals](#goals)
* [Features](#features)
* [Architecture](#architecture)
* [MVP Scope](#mvp-scope)
* [Getting Started](#getting-started)
* [Project Structure](#project-structure)
* [Milestones](#milestones)
* [Contribution](#contribution)
* [License](#license)

---

## Goals

Kernel aims to provide:

* A developer-friendly, structured Rust web framework
* Laravel-inspired conventions and philosophy
* Modular components that can be extended over time
* CLI tooling for server management and project scaffolding

---

## Features (MVP)

* Async HTTP server (GET & POST)
* Simple routing system with path parameters
* Controller abstractions
* Middleware pipeline
* Basic dependency injection container
* Configuration loading from `.env`
* CLI tool for running the server and generating controllers
* Basic test harness for integration testing

---

## Architecture

Kernel follows an MVC-inspired modular design:

* **App** – central orchestrator holding router, container, and middleware
* **Router** – handles route registration and matching
* **Middleware** – global request/response pipeline
* **Container** – dependency injection for services
* **Config** – environment-based configuration

---

## MVP Scope

**Included in MVP:**

* HTTP server
* Routing & controllers
* Middleware
* DI container
* Config system
* CLI scaffold
* Test harness

**Out of Scope:**

* ORM / database integration
* Auth / sessions / CSRF
* View templating
* WebSockets / background jobs
* Macro-based routing

---

## Getting Started

### Prerequisites

* Rust 1.70+
* Cargo

### Run the Server

```bash
cargo run -- serve
```

### Create a Controller

```bash
cargo run -- make:controller UserController
```

### Run Tests

```bash
cargo test
```

---

## Project Structure

```text
kernel/
 ├── src/
 │   ├── main.rs           # Entry point / CLI
 │   ├── app.rs            # App kernel
 │   ├── router.rs         # Routing system
 │   ├── middleware.rs     # Middleware pipeline
 │   ├── container.rs      # Dependency injection
 │   ├── request.rs        # Request abstraction
 │   ├── response.rs       # Response abstraction
 │   ├── config.rs         # Configuration loader
 │   └── cli.rs            # CLI commands
 └── Cargo.toml
```

---

## Milestones

1. **Server** – Hardcoded route responding to requests
2. **Router** – Dynamic route table with path parameters
3. **Middleware** – Logging pipeline example
4. **DI Container** – Singleton service registration and resolution
5. **Config** – `.env` loading into typed structs
6. **CLI** – `serve` & `make:controller`
7. **Tests** – Async integration test harness

---

## Contribution

Kernel is open for contributions. Developers are welcome to improve features, add components, or enhance the CLI.

### Guidelines

* Keep code idiomatic and safe
* Use async/await for all I/O operations
* Document your code
* Follow Rustfmt and Clippy recommendations
* Discuss major changes via issues before submitting pull requests

### How to Contribute

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -am 'Add feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

---

## License

MIT License. See [LICENSE](LICENSE) for details.
