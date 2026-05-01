# AGENTS.md - Code Guidelines for Claude Desktop Transport Bridge

## Build/Test Commands
- `npm run build` - Build TypeScript to dist/ 
- `npm run watch` - Watch mode compilation
- No lint or test commands configured

## Code Style
- **Language**: TypeScript with strict mode enabled
- **Module system**: ES modules with `.js` imports (NodeNext)
- **Target**: ES2022, Node >= 20.0.0
- **Imports**: Use `.js` extension for local imports, destructured imports for external packages
- **Types**: Use TypeScript interfaces, strict typing with proper error interfaces
- **Classes**: PascalCase, private methods prefixed with underscore if internal
- **Variables**: camelCase, descriptive names
- **Error handling**: Structured error objects with name/message/stack/details
- **Logging**: Use Logger.getInstance() singleton, structured error logging with formatError()
- **Async**: Prefer async/await, proper error propagation in try/catch blocks
- **Files**: kebab-case filenames, single responsibility principle

## Architecture
- Bridge pattern connecting stdio server to SSE/WebSocket client
- Event-driven with proper cleanup in process handlers
- Singleton logger with file output to dist/src/logs/