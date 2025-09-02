# Color-coded Zotero to Obsidian Template

This repository provides a template for importing color-coded Zotero annotations into Obsidian, maintaining the original highlight colors from Zotero.

## Overview

Obsidian templates are markdown files that can be used to structure and design Obsidian notes. This template is specifically designed to work with the [Zotero Integration Plugin](https://github.com/mgmeyers/obsidian-zotero-integration) for Obsidian by mgmeyers and enables you to use the different annotation colors provided by Zotero for functional color coding.

## Features

- Maintains Zotero highlight colors in Obsidian
- Organizes annotations by color
- Groups annotations into sections:
  - Main Claims and Questions (pink highlights)
  - Core Quotes (green highlights)
  - Excerpts and Comments (other colors, includidng pink and green highlights and segmented by orange highlights)
- Includes metadata and citation information

## Installation

1. Install the [Zotero Integration Plugin](https://github.com/mgmeyers/obsidian-zotero-integration) into your Obsidian vault.
2. Copy `Zotero Entry Note.md` to your Obsidian templates folder.
3. Follow the plugin's instructions on how to install an import format
3. Install the CSS snippet:
   - Open Obsidian Settings
   - Go to "Appearance" → "CSS snippets"
   - Click the folder icon to open the snippets folder
   - Copy `callouts.css` into this folder
   - Refresh the CSS snippets in Obsidian
   - Enable the snippet

## Usage

This template presumes that you use the following color code when annotating in Zotero:

- Pink (#e56eee) - Main Claims and Questions
- Green (#5fb236) - Core Quotes
- Orange (#f19837) - Headers for excerpts

That means that pink annotations in Zotero will be copied in the Obsidian note twice: Once in the leading section called "Main Claims and Questions" and once in the general annotation block under "Excerpts and Comments".

The same goes for green annotations, which will be copied once in "Core Quotes" and once in "Excerpts and Comments".

The "Excerpts and Comments" section generally collects all annotations from the Zotero entry in the order they appear in the annotations section of Zotero. The only exception are orange annotations, which will be imported as third-level headings, enabling you to structure your Obsidian note while annotating your PDF file within Zotero. If you mark part of the text in orange, it will thus appear as a heading in Obsidian.

To use this template, use the Zotero Integration import command while having Zotero open. You can read about how this works in the plugin's documentation: [Zotero Integration Plugin](https://github.com/mgmeyers/obsidian-zotero-integration)

## Supported Colors

The template supports all standard Zotero highlight colors:
- Yellow (#ffd400)
- Red (#ff6666)
- Orange (#f19837)
- Green (#5fb236)
- Blue (#2ea8e5)
- Pink (#e56eee)
- Purple (#a28ae5)
- Grey (#aaaaaa)