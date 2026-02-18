# Txtar VSCode Extension

VSCode language support for the [txtar](https://pkg.go.dev/golang.org/x/tools/txtar) archive format.

## Features

- Syntax highlighting for txtar files
- Comment highlighting for lines before/after file markers
- Filename highlighting in file marker lines (`-- filename --`)
- Embedded language support: automatically delegates syntax highlighting to the appropriate language based on file extension
  - Go (`.go`)
  - Python (`.py`)
  - JavaScript (`.js`)
  - TypeScript (`.ts`)
  - JSON (`.json`)
  - YAML (`.yaml`, `.yml`)
  - Markdown (`.md`, `.markdown`)
  - HTML (`.html`)
  - CSS (`.css`)
  - Shell (`.sh`, `.bash`)
  - Java (`.java`)
  - C (`.c`)
  - C++ (`.cpp`, `.cc`, `.cxx`, `.h`, `.hpp`)
  - Rust (`.rs`)
  - XML (`.xml`)

## Installation

### From Source

1. Clone this repository
2. Copy the extension folder to your VSCode extensions directory:
   - **Linux/macOS**: `~/.vscode/extensions/`
   - **Windows**: `%USERPROFILE%\.vscode\extensions\`
3. Restart VSCode

### Manual Installation

1. Open VSCode
2. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS)
3. Type "Extensions: Install from VSIX"
4. Select the `.vsix` file

## Usage

The extension automatically activates for files with the `.txtar` extension. 

### Txtar Format

A txtar archive consists of:
- Comment lines (any text before the first file marker)
- File entries starting with `-- filename --` markers
- File content following each marker

Example:

```
This is a comment.

-- hello.go --
package main

func main() {
    println("Hello, World!")
}
-- data.json --
{
  "message": "Hello"
}
```

## License

See LICENSE file for details.
