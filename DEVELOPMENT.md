# Development Guide

## Testing the Extension Locally

1. **Install VSCode Extension CLI** (if not already installed):
   ```bash
   npm install -g @vscode/vsce
   ```

2. **Package the extension**:
   ```bash
   vsce package
   ```
   This will create a `.vsix` file.

3. **Install the extension in VSCode**:
   - Open VSCode
   - Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS)
   - Type "Extensions: Install from VSIX"
   - Select the generated `.vsix` file

4. **Test with sample files**:
   - Open `example.txtar` or `test.txtar` in VSCode
   - Verify that:
     - Comments are highlighted
     - File markers (`-- filename --`) are highlighted
     - Filenames are highlighted
     - File contents use appropriate syntax highlighting based on extension

## Extension Structure

- `package.json` - Extension manifest
- `syntaxes/txtar.tmLanguage.json` - TextMate grammar for syntax highlighting
- `language-configuration.json` - Language configuration (brackets, comments, etc.)
- `example.txtar` - Simple example file
- `test.txtar` - Comprehensive test file covering all supported languages

## How It Works

The extension uses TextMate grammar to:

1. **Identify file markers**: Lines matching `^-- filename --$`
2. **Extract filename**: Captures the filename from the marker
3. **Delegate to embedded grammars**: Based on file extension, includes the appropriate language grammar
4. **Highlight comments**: Any lines not part of a file block are treated as comments

## Supported File Types

The extension automatically delegates to the following language grammars when available:

- Go, Python, JavaScript, TypeScript
- JSON, YAML, XML
- HTML, CSS, Markdown
- Shell scripts (Bash)
- Java, C, C++, Rust

Files with unknown extensions are displayed as plain text.
