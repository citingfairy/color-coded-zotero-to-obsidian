# Color-coded Zotero to Obsidian Template

This repository provides templates for importing color-coded Zotero annotations into Obsidian, maintaining the original highlight colors from Zotero.

## Overview

Obsidian templates are markdown files that can be used to structure and design Obsidian notes. The template provided in this repository are specifically designed to work with the [Zotero Integration Plugin](https://github.com/mgmeyers/obsidian-zotero-integration) for Obsidian by mgmeyers. Both templates import the original Zotero annotation colors and make your vault pretty and colorful.

The Zotero Entry Note Advanced template additionally enables you to use functional color coding. Annotations not only show up in their original color, but can be used to pull certain annotations to the top of your Obsidian note and to create subheadings.

## Features

Both plugins:
- Maintain Zotero highlight colors in Obsidian
- Include metadata, citation information, and direct links to the source entry in Zotero.

This is how the metadata part of the Obsidian note will look like after import:

![Basic structure of the Zotero Entry Note template](example_img_1.png)

The Zotero Entry Note Advanced plugin:
- Organizes annotations by color
- Groups annotations into sections:
  - Main Claims and Questions (pink highlights)
  - Core Quotes (green highlights)
  - Excerpts and Comments (other colors, includidng pink and green highlights and segmented by orange highlights)

Example of minimal Main Claims and Questions and Core Quotes sections:

![Appearance of the Main Claims and Questions and Core Quotes sections](example_img_2.png)

Example of a subheading (orange highlighted text in Zotero PDF) and other excerpts:

![Subheading and excerpts in Zotero Entry Note](example_img_3.png)

## Installation

1. Install the [Zotero Integration Plugin](https://github.com/mgmeyers/obsidian-zotero-integration) into your Obsidian vault.
2. Copy `Zotero Entry Note.md` or `Zotero Entry Note Advanced.md` to your Obsidian templates folder.
3. Follow the plugin's instructions on how to install an import format
3. Install the CSS snippet:
   - Open Obsidian Settings
   - Go to "Appearance" → "CSS snippets"
   - Click the folder icon to open the snippets folder
   - Copy `callouts.css` into this folder
   - Refresh the CSS snippets in Obsidian
   - Enable the snippet

## Usage

To use the templates, use the Zotero Integration import command while having Zotero open. You can read about how this works in the plugin's documentation: [Zotero Integration Plugin](https://github.com/mgmeyers/obsidian-zotero-integration)

The basic template will turn your colored highlights in Zotero to identically colored callouts in Obsidian. Comments to the highlights and annotations will be imported as plain text. Highlights, comments and annotations will be provided with a citation (including the PDF page number). The citation also has a clickable link that brings you to the highlight or annotation within the Zotero interface.

The advanced template presumes that you use the following color code when annotating in Zotero:

- Pink (#e56eee) - Main Claims and Questions
- Green (#5fb236) - Core Quotes
- Orange (#f19837) - Headers for excerpts

That means that pink annotations in Zotero will be copied in the Obsidian note twice: Once in the leading section called "Main Claims and Questions" and once in the general annotation block under "Excerpts and Comments".

The same goes for green annotations, which will be copied once in "Core Quotes" and once in "Excerpts and Comments".

The "Excerpts and Comments" section generally collects all highlights and annotations from the Zotero entry in the order they appear in the annotations section of Zotero. The only exception are orange highlights, which will be imported as third-level headings, enabling you to structure your Obsidian note while annotating your PDF file within Zotero. If you mark part of the text in orange, it will thus appear as a heading in Obsidian.

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