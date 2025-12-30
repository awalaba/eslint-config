# eslint-config

ESLint configuration for projects using the flat config format (ESLint 9+).

## Installation

### Option 1: Install from npm (if published)

```bash
npm install --save-dev eslint-config
```

### Option 2: Install from Git repository

```bash
npm install --save-dev git+https://github.com/awalaba/eslint-config.git
```

### Option 3: Install from local file path

```bash
npm install --save-dev file:../path/to/eslint-config
```

## Usage

After installation, create or update your `eslint.config.js` file in your project:

```javascript
import eslintConfig from 'eslint-config';

export default [
  ...eslintConfig,
  // Add your project-specific overrides here if needed
];
```

Or using CommonJS:

```javascript
const eslintConfig = require('eslint-config');

module.exports = [
  ...eslintConfig,
  // Add your project-specific overrides here if needed
];
```

## Project-Specific Configuration

You can extend or override the configuration for your specific project:

```javascript
import eslintConfig from 'eslint-config';

export default [
  ...eslintConfig,
  {
    // Override language options for browser environment
    languageOptions: {
      globals: {
        ...require('globals').browser,
      },
    },
  },
  {
    // Add project-specific rules
    rules: {
      'no-console': 'warn',
    },
  },
];
```

## Requirements

- Node.js
- ESLint 9.32.0 or higher
- The following peer dependencies (installed automatically):
  - `eslint`
  - `eslint-config-prettier`
  - `eslint-plugin-prettier`
  - `globals`
  - `prettier`

## What's Included

This config includes:
- ESLint recommended rules
- Prettier integration (via `eslint-config-prettier` and `eslint-plugin-prettier`)
- Strict mode enabled globally
- Node.js globals by default

## Development

```bash
# Run linter
npm run lint

# Fix linting issues
npm run lint:fix

# Format code
npm run format
```
