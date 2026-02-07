# GEMINI.md

## Project Overview

**Fabric** is an open-source framework written in Go for augmenting humans using AI. It acts as a versatile command-line interface (CLI) and REST API to interact with a wide array of AI providers. The core concept of Fabric is "Patterns", which are pre-defined, reusable prompts designed to solve specific real-world tasks.

The project consists of:
- A powerful **Go-based CLI** (`fabric`) as the main interface.
- A **REST API server** that exposes all core functionality over HTTP, including an interactive Swagger UI.
- A **SvelteKit and TailwindCSS-based web interface** for a GUI alternative to the CLI.
- Several **helper applications** also written in Go (`to_pdf`, `code2context`, `generate_changelog`).

### Key Features
- **Pattern System:** A large, crowdsourced collection of prompts for tasks like analysis, summarization, code generation, and more.
- **Multi-Provider Support:** Natively supports a wide range of AI vendors including OpenAI, Anthropic, Google Gemini, Ollama, Azure OpenAI, and many others.
- **Extensibility:** The system is designed to be extensible with custom patterns.
- **Rich I/O:** Can process text from stdin, files, URLs, and even YouTube video transcripts.
- **REST API:** A full-featured REST API allows for integration into other applications.
- **Reproducible Environments:** Uses Nix flakes for setting up a consistent development environment.

## Building and Running

### Initial Setup
First-time setup is required to configure API keys and directories.
```bash
fabric --setup
```

### From Source (Go)
A Go toolchain (1.25.1 or newer) is required.

```bash
# Install the main fabric CLI tool
go install github.com/danielmiessler/fabric/cmd/fabric@latest

# Install helper tools
go install github.com/danielmiessler/fabric/cmd/to_pdf@latest
go install github.com/danielmiessler/fabric/cmd/code2context@latest
go install github.com/danielmiessler/fabric/cmd/generate_changelog@latest

# Run the installed binary
fabric --help
```

### Web Interface (SvelteKit)
The web interface is located in the `/web` directory. Node.js and pnpm are required.

```bash
cd web
pnpm install
pnpm run dev
```
The web application will be available at `http://localhost:5173`.

### REST API Server
```bash
# Start the server on the default port 8080
fabric --serve

# Start on a custom port with an API key
fabric --serve --address :9090 --api-key your-secret-key
```
Interactive API documentation is available at `/swagger/index.html` when the server is running.

### Using Nix
For developers contributing to Fabric, a Nix development shell is provided.

```bash
# Enter the development environment
nix develop

# Inside the shell, you can build and run the project
go build ./cmd/fabric
./fabric --version
```

### Using Docker
Pre-built Docker images are available.

```bash
# Run setup (first time)
mkdir -p $HOME/.fabric-config
docker run --rm -it -v $HOME/.fabric-config:/root/.config/fabric kayvan/fabric:latest --setup

# Run the CLI
docker run --rm -it -v $HOME/.fabric-config:/root/.config/fabric kayvan/fabric:latest -p summarize

# Run the REST API server
docker run --rm -it -p 8080:8080 -v $HOME/.fabric-config:/root/.config/fabric kayvan/fabric:latest --serve
```

## Testing

Run the full suite of Go tests:
```bash
go test ./...
```

Run tests for the web interface:
```bash
cd web
pnpm test
```

## Development Conventions

### Code Style
- Follow standard Go conventions (`gofmt`, `golint`).
- The project uses `treefmt-nix` for code formatting, which can be run with `nix fmt`.

### Commit Messages
Commit messages should be descriptive and follow a conventional format:
- `feat: add new pattern for code analysis`
- `fix: resolve OAuth token refresh issue`
- `docs: update installation instructions`

### Pull Requests
- PRs should be focused and minimal. Large, multi-file changes should be broken down or discussed in an issue first.
- Contributors must generate a changelog entry for their PR by running:
  ```bash
  go run ./cmd/generate_changelog --ai-summarize --incoming-pr YOUR_PR_NUMBER
  ```

### API Documentation
- When adding or modifying REST API endpoints, the Swagger documentation must be updated.
- Add `swaggo` annotations to the handler in the Go code.
- Regenerate the documentation using the `swag` CLI:
  ```bash
h
swag init -g internal/server/serve.go -o docs
  ```
- Commit the updated `docs/swagger.json`, `docs/swagger.yaml`, and `docs/docs.go` files.

## Project Structure

- `cmd/`: Main application entry points for the executables (`fabric`, `to_pdf`, etc.).
- `internal/`: Core application logic, separated by concern (cli, server, core, tools). This code is not meant to be imported by other projects.
- `data/`: Contains the AI "Patterns" and "Strategies". This is the heart of the application's functionality.
- `docs/`: Project documentation, including contributing guidelines, API docs, and feature explanations.
- `web/`: The SvelteKit source code for the web interface.
- `nix/`: Nix expressions for setting up the development environment.
- `.goreleaser.yaml`: Configuration for GoReleaser, which automates the build and release process for multiple platforms.
- `flake.nix`: Defines the Nix flake for providing a reproducible development environment.
