# AGENTS.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

Fabric is an open-source Go framework for augmenting humans using AI. It provides a CLI and REST API to interact with multiple AI providers through reusable prompts called "Patterns."

## Build and Run Commands

### Go CLI (Main Application)
```bash
# Build from source
go build ./cmd/fabric

# Install globally
go install github.com/danielmiessler/fabric/cmd/fabric@latest

# Run tests
go test ./...

# Run a specific test
go test -run TestFunctionName ./internal/cli/

# Run with verbose output
go test -v ./...

# First-time setup (configures API keys and directories)
fabric --setup
```

### Web Interface (SvelteKit)
```bash
cd web
pnpm install
pnpm run dev        # Development server at localhost:5173
pnpm test           # Run tests
pnpm run build      # Production build
pnpm run lint       # Lint check
```

### REST API Server
```bash
fabric --serve                              # Start on default port 8080
fabric --serve --address :9090              # Custom port
fabric --serve --serveOllama                # With Ollama-compatible endpoints
```

Swagger documentation is available at `/swagger/index.html` when the server is running.

### Helper Tools
```bash
go install github.com/danielmiessler/fabric/cmd/to_pdf@latest
go install github.com/danielmiessler/fabric/cmd/code2context@latest
go install github.com/danielmiessler/fabric/cmd/generate_changelog@latest
```

## Code Architecture

### Directory Structure
- `cmd/` - Main entry points for executables (`fabric`, `to_pdf`, `code2context`, `generate_changelog`)
- `internal/` - Core application logic (not meant for external import)
- `data/patterns/` - AI prompt patterns (the heart of Fabric's functionality)
- `data/strategies/` - Prompt strategies (CoT, ToT, etc.)
- `web/` - SvelteKit web interface
- `docs/` - Documentation including REST API docs

### Internal Package Organization
- `internal/cli/` - CLI command handling, flags parsing (`flags.go`), chat execution
- `internal/core/` - Plugin registry (`plugin_registry.go`), chatter for AI interactions
- `internal/domain/` - Domain models (attachments, file management, streaming)
- `internal/plugins/` - Plugin system base (`plugin.go`)
- `internal/plugins/ai/` - AI vendor implementations (OpenAI, Anthropic, Gemini, Ollama, etc.)
- `internal/plugins/ai/openai_compatible/` - Generic OpenAI-compatible provider support
- `internal/server/` - REST API handlers (Gin framework)
- `internal/tools/` - Utilities (YouTube transcripts, Jina scraping, patterns loader)
- `internal/i18n/` - Internationalization support

### Plugin Architecture
AI vendors implement the `ai.Vendor` interface and are registered in `internal/core/plugin_registry.go`. Each vendor plugin lives in `internal/plugins/ai/<vendor_name>/` and handles:
- Model listing
- Chat completion with streaming
- Configuration via environment variables

To add a new OpenAI-compatible provider, add it to `internal/plugins/ai/openai_compatible/providers.go`.

### Pattern Format
Patterns are markdown files in `data/patterns/<pattern_name>/system.md`. They use structured sections:
- `# IDENTITY and PURPOSE` - Role definition
- `# OUTPUT SECTIONS` - Expected output format
- `# OUTPUT INSTRUCTIONS` - Formatting rules
- `# INPUT:` - Marks where user input is placed

Custom patterns can be stored separately from built-in patterns (configured via `fabric --setup`).

## API Documentation
When modifying REST API endpoints, update Swagger annotations and regenerate docs:
```bash
swag init -g internal/server/serve.go -o docs
```
Commit the updated `docs/swagger.json`, `docs/swagger.yaml`, and `docs/docs.go`.

## Commit Convention
Include co-author line for AI-assisted changes:
```
Co-Authored-By: Warp <agent@warp.dev>
```

For changelog entries on PRs:
```bash
go run ./cmd/generate_changelog --ai-summarize --incoming-pr YOUR_PR_NUMBER
```
