# Simple Webpack Implementation

[Working proof (video)](result.mov)

A basic implementation of a JavaScript module bundler, similar to Webpack, created while following [Ronen Amiel's talk](https://www.youtube.com/watch?v=Gc9-7PBqOC8).

## Implementation Details

The bundler consists of three main parts:

1. **Asset Creation** (`createAsset` function)
    - Reads the content of a JavaScript file
    - Uses Babylon to parse the code into an AST
    - Extracts dependencies using babel-traverse
    - Transforms code using babel
    - Returns an object with file metadata and transformed code

2. **Dependency Graph** (`createGraph` function)
    - Creates initial asset from entry point
    - Recursively processes all dependencies
    - Builds a graph of module relationships
    - Maps relative paths to module IDs

3. **Bundle Generation** (`bundle` function)
    - Combines all modules into a single self-executing function
    - Creates a module system with `require` implementation
    - Generates final bundle in `dist/index.js`

## Key Features

- Handles ES6 module imports
- Resolves file dependencies recursively
- Creates a single bundled output file
- Implements a basic module system

## Project Structure

```
simple-webpack/
├── src/
│   └── entry.js
├── bundler.js
└── dist/
     └── index.js
```

## Dependencies

### Core Dependencies
- `babylon`: JavaScript parser
- `babel-traverse`: AST traversal
- `babel-core`: Code transformation

### Global Development Tools
- JS beautify: `npm i -g js-beautify`
- highlight: `npm i -g highlight`

## Usage

```bash
node bundler.js
```

The bundled output will be generated in `dist/index.js`.

## How It Works

The bundler follows these steps:

1. Reads the entry file
2. Analyzes its dependencies
3. Recursively processes all imported modules
4. Creates a dependency graph
5. Generates a single bundle with all required code

For more details, check the commented source code in `bundler.js`.
