# webR Shiny Performance Tester

This repository contains a self-contained (static site) Quarto-based Shiny application powered by webR.

## Purpose

The goal of this project is to provide a single-page application that:
1. Demonstrates the capabilities of webR for running R code in the browser.
2. Benchmarks the performance of webR on different machines and browsers.
3. Provides technical developers with insights into load times, execution lag, and machine-specific capabilities.
4. Allows users to download their performance results as a CSV for further analysis.

## How it Works

The application uses the [shinylive](https://github.com/quarto-ext/shinylive) Quarto extension to bundle a Shiny app into a static site. When a user visits the page, webR is loaded in a Service Worker, allowing R to run locally in the browser without a backend server.

## Running Locally

To render the site locally, you need [Quarto](https://quarto.org/) installed.

1. Install the `shinylive` extension:
   ```bash
   quarto add quarto-ext/shinylive
   ```
2. Render the project:
   ```bash
   quarto render index.qmd
   ```
3. View the results in the `docs/` or `_site/` directory.
