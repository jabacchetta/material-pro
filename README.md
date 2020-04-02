# Material Pro (VSCode)

[![Inline (VSCode extension) version badge](https://vsmarketplacebadge.apphb.com/version-short/jabacchetta.material-pro.svg?color=blue&style=?style=for-the-badge&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.material-pro)
[![Inline (VSCode extension) installs badge](https://vsmarketplacebadge.apphb.com/installs-short/jabacchetta.material-pro.svg?color=blue)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.material-pro)
[![Inline (VSCode extension) rating badge](https://vsmarketplacebadge.apphb.com/rating-short/jabacchetta.material-pro.svg?color=blue)](https://marketplace.visualstudio.com/items?itemName=jabacchetta.material-pro)

## VSCode Masterclass (Coming Soon)

Follow [on Twitter](https://twitter.com/devcastcode) and [subscribe at DevCast](https://www.devcast.app/) to get priority access.

## Introduction

[Material Pro](https://marketplace.visualstudio.com/items?itemName=jabacchetta.material-pro) is a
color theme for VSCode that delivers visual pop while keeping distractions to a minimum and drawing
attention to what's most important — the code itself.

The syntax colors are mostly based off of the highly popular [Material Theme](https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-material-theme), although
each syntax selection is gradually being looked at and updated.

## Features

- Subtle contrast that separates the editor from the rest of the user interface without creating a
  washed-out effect.
- Dimmed inactive headings/icons that keeps irrelevant components out of the way.
- Modern tab border with a cleaner version of the signature Material accent.
- Strategic color pops added to significant elements (e.g. badge counts for problems and git changes).
- Italic font style for reserved keywords.
- Comprehensive coverage of VSCode's color theme API.

## Preview

![Preview](./images/screenshot.jpg)

## Custom Command Prompt

To get a colorized command prompt as seen in the screenshots above, add the following to `.bash_profile`:

```bash
# Enable colors in terminal
export CLICOLOR=1

# Customize terminal command prompt
export PS1='`if [ $? = 0 ]; then echo "\[\033[0;32m\]✔"; else echo "\[\033[0;31m\]✘"; fi` \[\033[0;34m\] \w\[\033[35m\]$(__git_ps1 " %s") \[\033[0;36m\]>\[\033[00m\] '

# Allows git repository status to be shown in prompt
source ~/.git-prompt.sh
```

## Icons

Install [Material Theme Icons](https://marketplace.visualstudio.com/items?itemName=Equinusocio.vsc-material-theme-icons) and
set the accent color to cyan.

## Recommended Settings

Optionally, add the following to your [user settings](https://code.visualstudio.com/docs/getstarted/settings#_settings-file-locations) for
additional UI updates.

```jsonc
{
  // More spacing.
  "editor.padding.top": 12,
  "editor.padding.bottom": 12,
  "workbench.tree.indent": 12,

  // Remove distractions.
  "editor.cursorBlinking": "solid",

  // Use "Go to Line..." keyboard shortcut when needed.
  "editor.lineNumbers": "off",

  // Install one of the font families listed.
  "editor.fontFamily": "'Operator Mono SSm Lig', 'Fira Code', 'Cascadia Code', Consolas, monospace",
  "editor.fontLigatures": true,

  // Personal preferences for readability.
  "window.zoomLevel": 1.4,
  "editor.fontSize": 13,
  "editor.lineHeight": 21,
  "workbench.fontAliasing": "auto",
}
```

## Custom Styles

VSCode's official theme color API doesn't have settings for everything, but we can customize the
stylesheets by installing the [Customize
UI](https://marketplace.visualstudio.com/items?itemName=iocave.customize-ui) extension and adding
the following settings:

```jsonc
{
  "customizeUI.stylesheet": {
    // Adds a border below the sidebar title.
    ".sidebar .composite.title": "border-bottom: 1px solid #19252B",

    // Leaves only the bottom border on matching bracket border.
    ".monaco-editor .bracket-match": "border-top: none; border-right: none; border-left: none;",

    // Leaves only the bottom border on find/match/selection highlights.
    ".monaco-editor .wordHighlight": "border-top: none; border-right: none; border-left: none;",
    ".monaco-editor .wordHighlightStrong": "border-top: none; border-right: none; border-left: none;",
    ".monaco-editor .findMatch": "border-top: none; border-right: none; border-left: none;",
    ".monaco-editor .currentFindMatch": "border-top: none; border-right: none; border-left: none;",
    ".monaco-editor .selectionHighlight": "border-top: none; border-right: none; border-left: none;",

    // Changes the color of the dirty file tab circle.
    ".monaco-workbench .part.editor>.content .editor-group-container.active>.title .tabs-container>.tab.dirty>.tab-close .action-label:not(:hover):before, .monaco-workbench .part.editor>.content .editor-group-container>.title .tabs-container>.tab.dirty>.tab-close .action-label:not(:hover):before": "color: #00bcd480",

    // // Optional, if you're already familiar with the editor icons and their keyboard shortcuts.
    // ".editor-actions": "display: none !important",
  },
}
```
