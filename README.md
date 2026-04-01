# Rust Templates for cargo-generate

A collection of project templates for [cargo-generate](https://github.com/cargo-generate/cargo-generate).

## Available Templates

### hexagonal_arch

A hexagonal architecture (ports and adapters) template for Rust projects.

```
src/
├── adapters/
│   ├── driven/      # Outgoing adapters (repositories, external services)
│   └── driving/     # Incoming adapters (controllers, handlers)
├── application/     # Application services / use cases
└── domain/
    ├── model.rs     # Domain models
    └── ports.rs     # Port interfaces (traits)
```

## Usage

Install cargo-generate:

```bash
cargo install cargo-generate
```

Generate a new project from a template:

```bash
cargo generate https://github.com/mrl00/templates --name my-project
```

Or specify a template directly:

```bash
cargo generate https://github.com/mrl00/templates hexagonal_arch --name my-project
```

## License

This project is licensed under the MIT License.
