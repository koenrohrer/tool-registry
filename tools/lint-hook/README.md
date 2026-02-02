# Auto Lint Hook

Automatically runs ESLint with `--fix` on staged JavaScript/TypeScript files before commits.

## How It Works

This hook triggers on the `PreCommit` event and runs ESLint on all staged `.js`, `.ts`, `.jsx`, and `.tsx` files.

## Requirements

- ESLint configured in your project
- Node.js installed
