[facebook/jscodeshift](https://github.com/facebook/jscodeshift)

[jscodeshift.com](https://jscodeshift.com)

jscodeshift is a toolkit created by Facebook for running automated code-rewriting scripts (codemods) across multiple JavaScript or TypeScript files.

How It Works

• Abstract Syntax Tree (AST): It parses source code into a structured AST using recast, allowing you to query and manipulate code as objects rather than fragile strings or regex.
• Style Preservation: recast attempts to keep original code styling, indentation, and formatting intact when generating the output source.
• Runner CLI: It includes a command-line runner that handles file discovery, parallel processing across directories, and summary reporting of changed files.

Common Use Cases

• API Migrations: Automatically updating component props, method names, or imports across large codebases.
• Framework Upgrades: Transitioning code to newer versions of libraries (such as React or TypeScript) without manual find-and-replace.
• Enforcing Standards: Standardizing code patterns and lint rules across multiple repositories.


---


Basic Usage

1. Installation

```
npm install -g jscodeshift
# Or run on-demand via npx
npx jscodeshift -t transform.js src/

```

2. Basic Transform File (transform.js)

```
module.exports = function transformer(file, api) {
  const j = api.jscodeshift;
  return j(file.source)
    .find(j.Identifier, { name: 'oldName' })
    .replaceWith(j.identifier('newName'))
    .toSource();
};

```

Would you like to see **an example codemod for a specific refactoring task** (like renaming a component or changing an import), or do you need help **debugging a custom transform**?
