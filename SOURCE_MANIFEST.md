# Source Manifest - Claude Code MCP Server

## Project Overview
This repository contains the source code for Claude Code MCP Server, a Model Context Protocol server that enables running Claude Code in one-shot mode with permissions bypassed automatically. It provides a unified `claude_code` tool for LLMs to interact with Claude Code directly.

## Core Files

### Server Implementation
- **src/server.ts** - Main server implementation containing the MCP server setup, tool handlers, and Claude Code execution logic
  - Implements the `claude_code` tool
  - Handles subprocess spawning for Claude CLI
  - Manages error handling and timeouts
  - Version: 1.10.12

### Configuration Files
- **package.json** - Node.js package configuration
  - Defines dependencies (@modelcontextprotocol/sdk, zod)
  - Scripts for build, test, and development
  - Published as @steipete/claude-code-mcp

- **tsconfig.json** - TypeScript compiler configuration
- **vitest.config.ts** - Main Vitest test configuration
- **vitest.config.unit.ts** - Unit test specific configuration
- **vitest.config.e2e.ts** - End-to-end test configuration

### Launch Scripts
- **start.sh** - Unix/Linux startup script
- **start.bat** - Windows batch startup script

### GitHub Actions Workflows
- **.github/workflows/ci.yml** - Continuous integration pipeline
- **.github/workflows/test.yml** - Test automation workflow
- **.github/workflows/claude.yml** - Claude Code GitHub Action configuration

### Documentation
- **README.md** - Project overview, installation instructions, and usage guide
- **CHANGELOG.md** - Version history and release notes
- **RELEASE.md** - Release process documentation
- **CLAUDE.md** / **AGENT.md** - Guidance for Claude Code when working with this repository
- **CURSOR.md** - Cursor IDE specific instructions
- **docs/local_install.md** - Local installation guide
- **docs/e2e-testing.md** - End-to-end testing documentation
- **docs/RELEASE_CHECKLIST.md** - Release checklist for maintainers

### Test Suite
- **src/__tests__/server.test.ts** - Server unit tests
- **src/__tests__/e2e.test.ts** - End-to-end integration tests
- **src/__tests__/edge-cases.test.ts** - Edge case testing
- **src/__tests__/error-cases.test.ts** - Error handling tests
- **src/__tests__/validation.test.ts** - Input validation tests
- **src/__tests__/version-print.test.ts** - Version printing functionality tests
- **src/__tests__/setup.ts** - Test setup and configuration
- **src/__tests__/mocks.ts** - Mock implementations for testing

### Test Utilities
- **src/__tests__/utils/claude-mock.ts** - Mock Claude CLI for testing
- **src/__tests__/utils/mcp-client.ts** - MCP client utilities for testing
- **src/__tests__/utils/persistent-mock.ts** - Persistent mock server for testing
- **src/__tests__/utils/test-helpers.ts** - Shared test helper functions

### Scripts
- **scripts/publish-release.sh** - Automated release publishing
- **scripts/test-release.sh** - Release testing script
- **scripts/check-version-log.sh** - Version and changelog validation
- **scripts/restore-config.sh** - Configuration restoration utility

### Miscellaneous
- **test-standalone.js** - Standalone test runner
- **print-eslint-config.js** - ESLint configuration printer
- **.vscode/settings.json** - VS Code workspace settings
- **.github/copilot-instructions.md** - GitHub Copilot configuration
- **rules.devin.md** - Devin AI specific rules

## Key Dependencies
- @modelcontextprotocol/sdk - MCP protocol implementation
- zod - Runtime type validation
- TypeScript - Type-safe development
- Vitest - Testing framework

## Architecture Notes
- Single-tool MCP server architecture
- Subprocess execution via Node.js spawn
- Automatic permission bypassing with --dangerously-skip-permissions
- Configurable working directory and tool enablement
- Comprehensive error handling and timeout management

## Environment Variables
- `CLAUDE_CLI_PATH` - Custom path to Claude CLI executable
- `MCP_CLAUDE_DEBUG` - Enable debug logging (set to 'true')

## Development Workflow
1. `npm install` - Install dependencies
2. `npm run dev` - Run in development mode with hot reload
3. `npm run build` - Build TypeScript to JavaScript
4. `npm test` - Run all tests
5. `npm run test:unit` - Run unit tests only
6. `npm run test:e2e` - Run end-to-end tests