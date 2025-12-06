# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Repository Overview

This repository is a collection of source logo files in SVG format, organized by spending/merchant categories. There is no application code, build system, or automated tests here—only static assets managed via Git.

Key characteristics:
- Each top-level directory (e.g. `Business`, `Digital`, `Finance`, `Groceries`, `Techs`, `Travel`, `Charity`, `Dining-out`, `Fines-and-taxes`, `Health`, `Realty`, `Telecom`, `Clothes`, `Education`, `Goods`, `Lifestyle`, `Repairs`, `Transportation`) represents a logical category of merchants or services.
- Within each category directory, individual SVG files correspond to specific brands or services (e.g. `uber.svg`, `yandex-go.svg`, `adidas.svg`, `MIR.svg`).
- `README.md` describes the repository as a set of logo source files in SVG format.

## Directory and Naming Conventions

- Top-level directories are human-readable category names in English, usually matching expense or business domains.
- SVG filenames typically match the brand name, lowercased, with words separated by hyphens where needed (e.g. `yandex-eda.svg`, `rendez-vous.svg`). Some files preserve capitalization where that matches the brand (e.g. `BSPB.svg`, `VK.svg`).
- There is no deeper nested structure beyond category → individual SVGs; all logic for how these logos are used is expected to live in downstream applications or design tooling, not in this repository.

When adding new assets:
- Choose the most appropriate existing category directory; if none fits, discuss with the maintainer before creating a new category.
- Follow the existing naming style for new files: brand name as the base, with hyphens between words and `.svg` extension.

## Working with Assets

Common tasks for this repo involve viewing, editing, and organizing SVG files rather than running code:
- Use an external vector graphics editor (e.g. Illustrator, Figma, Inkscape) to modify individual SVGs.
- Keep SVGs clean and minimal (e.g. avoid embedded raster images or unnecessary metadata) to make them easy to consume in downstream projects.
- If a logo is updated or replaced, prefer editing the existing file in place rather than creating duplicates, so downstream references remain valid.

## Commands and Workflows

There are no language-specific build, lint, or test commands in this repository. Typical command-line operations focus on navigating and managing the SVG assets:

- List top-level categories:
  - `ls`
- List all SVGs in a given category (example: Transportation):
  - `ls Transportation/*.svg`
- Search for a logo by name across all categories:
  - `find . -name '*uber*.svg'`
- Count total number of SVG logos:
  - `find . -name '*.svg' | wc -l`

Version control workflows use standard Git commands (e.g. `git status`, `git diff`, `git add <path>`, `git commit`), with diffs consisting primarily of SVG changes or additions.
