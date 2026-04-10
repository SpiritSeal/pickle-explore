# 🥒 Pickle Explorer

A browser-based IDE that lets you write a Python class and instantly explore the binary pickle encoding of that class, byte by byte.

**Live app → [spiritseal.github.io/pickle-explore](https://spiritseal.github.io/pickle-explore)**

## Features

- **In-browser Python** powered by [Pyodide](https://pyodide.org/) — no server needed
- **Monaco Editor** (the VS Code engine) with Python syntax highlighting
- **Color-coded hex dump** — each opcode group gets a distinct colour
- **Per-opcode documentation** drawn directly from Python's `pickletools` module
- **Hover interactions** — hover a byte to highlight its opcode row, and vice versa
- **Protocol selector** — try protocols 0 through 5 and see how the encoding changes
- **`Ctrl+Enter`** shortcut to re-pickle instantly

## Usage

1. Write (or edit) a Python class in the left-hand editor.
2. Select a pickle protocol (default: 2).
3. Click **🥒 Pickle It!** (or press `Ctrl+Enter`).
4. The right panel shows:
   - A colour-coded byte stream of the raw pickle data
   - A legend explaining the opcode colour categories
   - A per-opcode breakdown with its offset, name, argument, and documentation

You can also assign any serialisable object to a variable named `obj` and it will be pickled directly instead of instantiating the class.

## Local development

Open `index.html` in a browser — it loads all dependencies (Monaco Editor, Pyodide) from CDN, so an internet connection is required.

```bash
# Optionally serve with any static file server, e.g.:
python -m http.server
# then open http://localhost:8000
```

## Deploying to GitHub Pages

Enable GitHub Pages for this repository (Settings → Pages → Source: `main` branch, `/` root).  
The `.nojekyll` file prevents GitHub Pages from treating the project as a Jekyll site.