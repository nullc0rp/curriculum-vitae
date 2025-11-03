# CV / Resume

Professional security engineer CV written in LaTeX using the `altacv` class.

## Project Structure

```
.
├── src/
│   ├── curriculum.tex    # Main LaTeX source file
│   ├── altacv.cls        # AltaCV class file
│   └── curriculum.pdf    # Compiled PDF (generated)
├── .github/
│   └── workflows/
│       ├── build.yml     # Build on push/PR
│       └── release.yml   # Build and attach PDF on release
└── README.md
```

## Local Compilation

### Prerequisites

On Arch Linux:
```bash
sudo pacman -S texlive-most texlive-lang
```

On Ubuntu/Debian:
```bash
sudo apt-get install texlive-full
```

On macOS:
```bash
brew install --cask mactex
```

### Compile

```bash
cd src
pdflatex curriculum.tex
pdflatex curriculum.tex  # Run twice for proper references
```

The compiled PDF will be generated as `src/curriculum.pdf`.

## GitHub Actions

This repository includes two GitHub Actions workflows:

### 1. Build on Push/PR (`build.yml`)
- Automatically builds the PDF when you push to `main`/`master` or open a PR
- PDF is available as a downloadable artifact for 7 days
- Useful for testing changes

### 2. Release Workflow (`release.yml`)
- Automatically builds and attaches the PDF when you create a new GitHub release
- The PDF is attached as a release asset
- To use: Create a new release on GitHub, and the workflow will automatically attach `curriculum.pdf`

## Troubleshooting

If you get an error about missing `altacv.cls`:
1. Download it from [GitHub](https://github.com/liantze/AltaCV)
2. Place `altacv.cls` in the `src/` directory

If you get font errors:
```bash
# Arch Linux
sudo pacman -S ttf-font-awesome

# Ubuntu/Debian
sudo apt-get install fonts-font-awesome
```

## Alternative: Use a LaTeX IDE

- **TeXstudio** - Cross-platform LaTeX editor
- **Overleaf** - Online LaTeX editor
- **VS Code** - With LaTeX Workshop extension
