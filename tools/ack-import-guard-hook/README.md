# ACK Import Guard

Enforces `.js` extensions on all relative imports in TypeScript files. The ACK extension uses ESM module resolution which requires explicit file extensions on relative imports even in `.ts` files.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "ACK Import Guard"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PreToolUse` for `Write` and `Edit` operations on `.ts` and `.tsx` files. It **blocks** writes that contain relative imports without `.js` extensions:

```typescript
// BLOCKED:
import { Foo } from './foo';
import { Bar } from '../bar';

// ALLOWED:
import { Foo } from './foo.js';
import { Bar } from '../bar.js';
import { Baz } from 'external-package';  // non-relative OK
```

Designed specifically for the ACK VS Code extension codebase.
