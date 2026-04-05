# Rust Templates for cargo-generate

A collection of project templates for [cargo-generate](https://github.com/cargo-generate/cargo-generate).

## Available Templates

### hexagonal_arch

A full hexagonal architecture (ports and adapters) template for Rust library projects.

```
src/
├── adapters/
│   ├── driven/      # Outgoing adapters (repositories, external services)
│   └── driving/     # Incoming adapters (controllers, handlers)
├── application/
│   ├── services/    # Application services
│   └── use_cases/   # Use case implementations
└── domain/
    ├── aggregates/  # Domain aggregates
    ├── models/      # Domain models
    ├── ports/       # Port interfaces (traits)
    └── value_objects/ # Value objects
```

### hexagonal_arch_simple_lib

A simplified hexagonal architecture template for Rust library projects.

```
src/
├── adapters/
│   ├── drive/       # Driven adapters (outgoing)
│   └── driving/     # Driving adapters (incoming)
├── application/     # Application layer
└── domain/          # Domain layer
```

### hexagonal_arch_simple_bin

A simplified hexagonal architecture template for Rust binary projects.

```
src/
├── adpters/
│   ├── driven/      # Outgoing adapters
│   └── driving/     # Incoming adapters
├── application/     # Application layer
└── domain/          # Domain layer
```

### clean_arch

A clean architecture template for Rust library projects, following dependency rule with clear layer separation.

```
src/
├── domain/                    # Enterprise business rules
│   ├── entities/              # Core business objects
│   ├── value_objects/         # Immutable domain value types
│   ├── events/                # Domain events
│   └── repositories/          # Repository interfaces (traits)
├── application/               # Application business rules
│   ├── use_cases/             # Use case interactors
│   ├── services/              # Application services
│   └── dtos/                  # Data transfer objects
├── infrastructure/            # External concerns
│   ├── persistence/           # Database implementations
│   ├── external_services/     # Third-party service integrations
│   └── messaging/             # Message queue/event bus
└── presentation/              # Interface adapters
    ├── api/                   # REST/GraphQL API handlers
    ├── cli/                   # Command-line interface
    └── web/                   # Web UI templates/SSR
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
