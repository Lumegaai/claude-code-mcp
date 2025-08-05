# Complete Source Manifest - Claude Code MCP Server

## Project Overview
This repository contains the source code for Claude Code MCP Server, a Model Context Protocol server that enables running Claude Code in one-shot mode with permissions bypassed automatically. It provides a unified `claude_code` tool for LLMs to interact with Claude Code directly.

**Version:** 1.10.12  
**License:** MIT  
**Author:** Peter Steinberger  
**Package:** @steipete/claude-code-mcp

## Repository Structure

### Root Configuration Files
- **.gitignore** - Git ignore patterns (node_modules, dist, coverage, IDE files)
- **.npmignore** - NPM package ignore patterns (excludes assets/ from npm package)
- **LICENSE** - MIT License file
- **package.json** - Node.js package configuration with dependencies and scripts
- **package-lock.json** - Locked dependency versions for reproducible installs
- **tsconfig.json** - TypeScript compiler configuration

### Core Implementation
- **src/server.ts** - Main MCP server implementation
  - Implements the `claude_code` tool with MCP protocol
  - Handles Claude CLI subprocess spawning and management
  - Includes error handling, timeouts, and debug logging
  - Version printing on first tool use
  - Environment variable support (CLAUDE_CLI_PATH, MCP_CLAUDE_DEBUG)

### Launch Scripts
- **start.sh** - Unix/Linux/macOS startup script
- **start.bat** - Windows batch startup script

### GitHub Configuration
- **.github/workflows/ci.yml** - Continuous Integration workflow
  - Runs on push and pull requests
  - Tests on multiple Node.js versions
  - Builds and runs test suite
  
- **.github/workflows/test.yml** - Test automation workflow
  - Comprehensive test execution
  - Coverage reporting
  
- **.github/workflows/claude.yml** - Claude Code GitHub Action
  - Responds to issue comments
  - Requires ANTHROPIC_API_KEY secret

### Documentation Files
- **README.md** - Main project documentation with installation and usage
- **CHANGELOG.md** - Detailed version history and release notes
- **RELEASE.md** - Release process documentation
- **AGENT.md** / **CLAUDE.md** - Instructions for Claude Code when working on this repo
- **docs/local_install.md** - Local installation guide
- **docs/e2e-testing.md** - End-to-end testing documentation  
- **docs/RELEASE_CHECKLIST.md** - Maintainer's release checklist

### Test Suite

#### Test Files
- **src/__tests__/setup.ts** - Test environment setup
- **src/__tests__/mocks.ts** - Mock implementations
- **src/__tests__/server.test.ts** - Server unit tests
- **src/__tests__/e2e.test.ts** - End-to-end integration tests
- **src/__tests__/edge-cases.test.ts** - Edge case scenarios
- **src/__tests__/error-cases.test.ts** - Error handling tests
- **src/__tests__/validation.test.ts** - Input validation tests
- **src/__tests__/version-print.test.ts** - Version printing tests

#### Test Utilities
- **src/__tests__/utils/claude-mock.ts** - Mock Claude CLI for testing
- **src/__tests__/utils/mcp-client.ts** - MCP client test utilities
- **src/__tests__/utils/persistent-mock.ts** - Persistent mock server
- **src/__tests__/utils/test-helpers.ts** - Shared test helper functions

#### Test Configuration
- **vitest.config.ts** - Main Vitest configuration
- **vitest.config.unit.ts** - Unit test specific configuration
- **vitest.config.e2e.ts** - E2E test specific configuration
- **test-standalone.js** - Standalone test runner

### Release Scripts
- **scripts/publish-release.sh** - Automated npm publishing
- **scripts/test-release.sh** - Pre-release testing
- **scripts/check-version-log.sh** - Version/changelog validation
- **scripts/restore-config.sh** - Configuration restoration

### Assets Directory
- **assets/claude_code_mcp_logo.png** - Project logo
- **assets/screenshot.png** - Main screenshot
- **assets/additional_claude_screenshot.png** - Additional UI screenshot
- **assets/agents_in_agents_meme.jpg** - Humorous project meme
- **assets/claude_code_example_20250515.png** - Usage example
- **assets/claude_code_multistep_example.png** - Multi-step operation example
- **assets/claude_tool_git_example.png** - Git integration example
- **assets/cursor-screenshot.png** - Cursor IDE integration
- **assets/eslint_example.png** - ESLint integration example
- **assets/file_list_example.png** - File listing example
- **assets/github_actions_fix_example.png** - GitHub Actions fix example
- **assets/multistep_example.png** - Another multi-step example

### IDE Configuration
- **.vscode/settings.json** - VS Code workspace settings

### Utility Files
- **print-eslint-config.js** - ESLint configuration printer utility

## Key Features
- Single-tool MCP server architecture
- Automatic permission bypassing (--dangerously-skip-permissions)
- Configurable working directory
- Tool enablement configuration
- Comprehensive error handling
- Debug logging support
- Timeout management (default: 5 minutes)
- Version printing on first use

## Dependencies

### Runtime Dependencies
- @modelcontextprotocol/sdk (^1.11.2) - MCP protocol implementation
- zod (^3.24.4) - Runtime type validation

### Development Dependencies
- @eslint/js (^9.26.0) - JavaScript linting
- @types/node (^22.15.17) - Node.js TypeScript types
- @vitest/coverage-v8 (^2.1.8) - Code coverage
- tsx (^4.19.4) - TypeScript execution
- typescript (^5.8.3) - TypeScript compiler
- vitest (^2.1.8) - Testing framework

## NPM Scripts
- `npm run build` - Compile TypeScript to JavaScript
- `npm start` - Run the compiled server
- `npm run dev` - Development mode with hot reload
- `npm test` - Run all tests
- `npm run test:unit` - Run unit tests only
- `npm run test:e2e` - Run end-to-end tests
- `npm run test:coverage` - Generate coverage report
- `npm run test:watch` - Watch mode for tests

## Environment Variables
- `CLAUDE_CLI_PATH` - Override default Claude CLI path
- `MCP_CLAUDE_DEBUG` - Enable debug logging (set to 'true')

## File Count Summary
- Configuration files: 11
- Source files: 1
- Test files: 13
- Documentation files: 9
- Script files: 7
- Asset files: 11
- Total files: 52 (excluding node_modules and generated files)