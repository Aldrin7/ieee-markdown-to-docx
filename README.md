# IEEE MD → DOCX Converter

**One-click GUI application** that converts Markdown files into IEEE conference-format `.docx` documents.

**Created by Aldrin Manon**

![Status](https://img.shields.io/badge/status-ready-brightgreen)
![Python](https://img.shields.io/badge/python-3.7+-blue)

## Features

| Feature | Supported |
|---------|-----------|
| IEEE two-column layout | ✅ |
| Auto-numbered sections (I, II, III…) | ✅ |
| Auto-numbered subsections (A, B, C…) | ✅ |
| Image embedding from folders | ✅ |
| Figure auto-numbering (Fig. 1, Fig. 2…) | ✅ |
| Markdown tables → Word tables | ✅ |
| LaTeX formulas (`\alpha`, `\sum`, `\frac`) | ✅ |
| Inline math `$...$` | ✅ |
| Display equations `$$...$$` (centered, numbered) | ✅ |
| Subscripts/superscripts (`X_i`, `X^{n+1}`) | ✅ |
| Greek letters, operators, arrows | ✅ |
| Multi-author column layout | ✅ |
| References with hanging indent | ✅ |
| Bold labels, bullet lists, blockquotes | ✅ |
| Batch conversion (all .md in folder) | ✅ |
| Built-in test run | ✅ |

## How to Use
## Preferred option: Option 3

### Option 1: Pre-built EXE (Windows)

1. Download `IEEE_MD2DOCX.exe` from the `dist/` folder
2. **Double-click** to launch the GUI
3. Click **🧪 Test Run** to verify it works
4. Select a folder containing your `.md` files and images
5. Click **▶ Convert All**

### Option 2: Build from Source

```bash
# Install dependencies
pip install python-docx

# Run GUI
python app.py

# Or CLI mode
python app.py paper.md
python app.py /path/to/folder/

# Build EXE (requires pyinstaller)
pip install pyinstaller
python build.py
# → produces dist/IEEE_MD2DOCX.exe
```

### Option 3: Windows One-Click Build

Double-click `build.bat` — it installs dependencies and builds the EXE automatically.

## Folder Structure

Place your `.md` files and images in the same folder:

```
my_paper/
├── paper.md              ← Your markdown source
├── figures/
│   ├── architecture.png  ← Referenced in paper.md
│   └── results.png
└── data.csv
```

Reference images in your `.md`:

```markdown
![Architecture diagram](figures/architecture.png)
![Results chart](figures/results.png){width=3in}
```

## Markdown Format

```markdown
# Paper Title

**Author Name**
*Department, University*
*City, Country*
*email@example.com*

## Abstract
Your abstract text here with $inline math$.

## Keywords
keyword1, keyword2, keyword3

## Introduction
Body text with citations [1].

### Subsection
More text. Display equation:

$$E = mc^2$$

| Column1 | Column2 |
|---------|---------|
| data1   | data2   |

## References
[1] A. Author, "Title," Journal, 2024.
```

## Supported LaTeX

- **Greek:** `\alpha` `\beta` `\gamma` `\theta` `\lambda` `\pi` `\sigma` `\omega` …
- **Operators:** `\sum` `\int` `\prod` `\partial` `\nabla` `\infty` …
- **Relations:** `\leq` `\geq` `\neq` `\approx` `\in` `\subset` …
- **Arrows:** `\rightarrow` `\leftarrow` `\Rightarrow` …
- **Functions:** `\sin` `\cos` `\log` `\lim` `\max` `\exp` …
- **Fractions:** `\frac{a}{b}` → (a)/(b)
- **Blackboard:** `\mathbb{R}` `\mathbb{N}` …

## Output

Each `.md` file produces a `<filename>_IEEE.docx` in the same folder.

## Files

```
ieee-md2docx/
├── app.py          # GUI application + CLI entry point
├── converter.py    # Core conversion engine
├── build.py        # Cross-platform build script
├── build.bat       # Windows one-click build
├── test_paper.md   # Sample paper for testing
└── dist/
    └── IEEE_MD2DOCX(.exe)  # Pre-built binary
```

## License

MIT
