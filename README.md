# Mermaid.js Syntax Highlighter for TextMate

This repository provides a rudimentary Mermaid.js syntax highlighter for TextMate, including support for nodes, shapes, links, and directives within Mermaid.js diagrams.

## Features

- **Comments**: Highlights comments starting with `%%`.
- **Directives**: Captures and highlights special Mermaid.js directives such as `%%{init: {...}}%%`.
- **Node Shapes**: Handles various Mermaid.js node shapes, including square brackets `[]`, round brackets `()`, and curly braces `{}`.
- **Operators**: Highlights Mermaid.js flowchart operators like `-->`, `---`, `==>`, etc.
- **Labels**: Highlights labels used between operators.
- **Strings**: Supports both single-quoted and double-quoted strings, including multi-line strings.
- **Keywords**: Recognizes key Mermaid.js keywords like `graph`, `flowchart`, `subgraph`, `end`, `class`, and more.
- **Subgraph Names**: Highlights subgraph names using specific regex.

## Installation

1. **Clone the Repository:**

   Open your terminal and clone this repository to your local machine:

   ```bash
   git clone https://github.com/mettamatt/mermaid-bundle.git
   ```

2. **Rename the Folder:**

   Rename the folder to ensure TextMate recognizes it as a bundle:

   ```bash
   mv mermaid-bundle mermaid.tmbundle
   ```

3. **Move the Bundle to TextMate's Bundles Directory:**

   Move the renamed `mermaid.tmbundle` directory to TextMate's `Bundles` directory:

   ```bash
   mv mermaid.tmbundle ~/Library/Application\ Support/TextMate/Bundles/
   ```

4. **Reload TextMate Bundles:**

   To make sure TextMate recognizes the new bundle, reload bundles by running:

   ```bash
   osascript -e 'tell app "TextMate" to reload bundles'
   ```

5. **Using the Syntax Highlighter:**

   After reloading, open any Mermaid.js file (`*.mmd` or `*.mermaid`), and TextMate should automatically apply the syntax highlighting. If it doesn't, manually select the Mermaid syntax from the language menu.

## Syntax Highlighting Details

The syntax highlighter uses a structured approach based on TextMate grammar definitions. Here’s what’s highlighted:

### 1. **Comments**

- Syntax: `%%`
- Highlighting Rule: Matches lines starting with `%%`.
- Scope: `comment.mermaid`

### 2. **Directives**

- Syntax: `%%{init: {...}}%%`
- Handles keys, structures, and boundaries in Mermaid.js directives.
- Scope: `meta.preprocessor.mermaid` and `entity.name.directive.key.mermaid`

### 3. **Node Shapes**

- Syntax: `[text]`, `{text}`, `(text)`
- Recognizes and highlights different node shapes and their contents.
- Scope: `entity.name.node.shape.mermaid` and `entity.name.type.mermaid`

### 4. **Operators**

- Syntax: `-->`, `---`, `==>`, etc.
- Highlighting for Mermaid.js flowchart operators.
- Scope: `keyword.operator.js.mermaid`

### 5. **Keywords**

- Recognized Keywords: `graph`, `flowchart`, `subgraph`, `end`, `class`, `classDef`, `state`, `section`, `title`
- Scope: `keyword.control.mermaid`

### 6. **Quoted Strings**

- Supports both single-quoted and double-quoted strings.
- Scope: `string.quoted.single.mermaid`, `string.quoted.double.mermaid`

### 7. **Subgraph Names**

- Syntax: `subgraph NAME`
- Captures and highlights subgraph names.
- Scope: `entity.name.subgraph.mermaid`

### 8. **Link Labels**

- Syntax: `|label|`
- Recognizes and highlights labels for Mermaid.js links.
- Scope: `string.link.label.mermaid`
