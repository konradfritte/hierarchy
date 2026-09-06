# Hierarchy

A vibe-coded (mostly done with DS V4 Flash 0731) hierarchic outliner. Everything runs locally in the browser in a single `index.html` file.

## Getting started

Open `index.html` directly in your browser.

## Usage

- Press `Enter` to create a new item below the current one.
- Use `Tab` / `Shift`+`Tab` to indent / outdent.
- Use `Alt`+`←`/`→` to zoom into an item and back out (the breadcrumb on top shows the path; click it to jump back).

### Selection (marking)

- `Shift`+`↑` / `Shift`+`↓` jumps between siblings on the **same hierarchy level** as the starting item.
- Child items cannot be selected independently; if a marked sibling has children, its whole subtree is marked along with it.
- Once all children of a parent are marked (including a single child), `Shift`+`↑` / `Shift`+`↓` includes the parent as well.
- Moving with `↑` / `↓` clears the selection again.

### Color marking

- `Ctrl`+`M`, then a digit `1`–`9`: colors the focused item **or** all marked items.
- Pressing the same digit again removes the color.
- Colors are preserved on export/import.

### Further actions

| Action | Shortcut |
| --- | --- |
| Create new item below | `Enter` |
| Indent / outdent | `Tab` / `Shift`+`Tab` |
| Previous / next item | `↑` / `↓` |
| Mark items | `Shift`+`↑` / `Shift`+`↓` |
| Move item (with children) | `Alt`+`↑` / `Alt`+`↓` |
| Zoom into / out of an item | `Alt`+`→` / `Alt`+`←` |
| Collapse / expand item | `Ctrl`+`.` |
| Delete item (incl. children) | `Ctrl`+`Del` |
| Color item (or marked ones) | `Ctrl`+`M` + `1`–`9` |
| Remove color | `Ctrl`+`M` + same digit |
| Import list | `Ctrl`+`I` |
| Export list | `Ctrl`+`E` |
| Show help | `Ctrl`+`H` |

All shortcuts are also listed in the built-in help dialog (`?` button top right or `Ctrl`+`H`).

## Export / Import

Export creates a JSON file (`hierarchy.json`) with the following format:

```json
{
  "items": [
    {
      "text": "Top-level item",
      "depth": 0,
      "collapsed": false,
      "color": ""
    },
    {
      "text": "Child item",
      "depth": 1,
      "collapsed": false,
      "color": "3"
    }
  ]
}
```

- `color` is a digit `1`–`9` or empty.
- Import via `Ctrl`+`I` or the file field in the toolbar.
