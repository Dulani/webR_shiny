# Agent Instructions - webR Shiny Performance Tester

This file provides context and instructions for AI agents working on this repository.

## Project Structure

- `index.qmd`: The main Quarto document containing the Shiny application and technical documentation.
- `_quarto.yml`: Configuration for the Quarto project.
- `docs/`: The output directory for the rendered static site (configured in `_quarto.yml`).

## Technical Stack

- **Quarto**: The publishing system used to build the site.
- **webR**: R compiled to WebAssembly, enabling R to run in the browser.
- **shinylive**: A Quarto extension that enables Shiny apps to run using webR.

## Development Workflow

1. **Environment Setup**: Ensure Quarto is installed and the `shinylive` extension is added (`quarto add quarto-ext/shinylive`).
2. **Editing**: Most logic resides in `index.qmd` within the `shinylive` code blocks.
3. **Performance Metrics**: When adding new benchmarks, ensure they are captured in the reactive data frame that powers the CSV download.
4. **Rendering**: Always run `quarto render` after making changes to verify that the build succeeds and the static site is updated.

## Performance Testing Logic

The performance testing logic is split between:
- **Load Time**: Measured from the start of the page load until R is initialized and ready to receive commands.
- **Execution Lag**: Measured by timing a simple R command (e.g., `Sys.sleep(0)` or `1+1`) repeatedly to gauge responsiveness.
- **Capabilities**: Using JavaScript/R to detect available memory, CPU cores (via `navigator.hardwareConcurrency`), and browser info.

## Guidelines

- Keep the page "self-contained" as much as possible by using static assets and avoiding external API dependencies unless necessary.
- Ensure the description remains technical and useful for developers interested in webR performance.
- When updating the benchmarks, maintain the CSV export functionality so that historical comparisons can be made.
