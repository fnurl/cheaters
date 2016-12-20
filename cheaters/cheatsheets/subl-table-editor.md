### Table Editor (for Sublime Text 2/3)

All commands must be performed while the cursor is inside a table. Package
(unmaintained) is available at
<https://github.com/vkocubinsky/SublimeTableEditor>

| shortcut          | description                                                                                                                                   |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| xCTRL+xSHIFT+a    | Re-align the table without change the current table field. Move cursor to begin of the current table field.                                   |
| tab               | Re-align the table, move to the next field. Creates a new row if necessary.                                                                   |
| xSHIFT+tab        | Re-align, move to previous field.                                                                                                             |
| enter             | Re-align the table and move down to next row. Creates a new row if necessary. At the beginning or end of a line, enter still does new line.   |
| xOPT+left         | Move the current column left.                                                                                                                 |
| xOPT+right        | Move the current column right.                                                                                                                |
| xOPT+enter        | Split rest of cell down from current cursor position, insert new line bellow if current row is last row in the table or if next line is hline |
| xOPT+xSHIFT+left  | Kill the current column.                                                                                                                      |
| xOPT+xSHIFT+right | Insert a new column to the left of the cursor position.                                                                                       |
| xOPT+xSHIFT+down  | Add row above current row                                                                                                                     |
| xOPT+up           | Move current row up                                                                                                                           |
| xOPT+down         | Move current row down                                                                                                                         |
| xCTRL+k, -        | Add hline below current row and align table. Cursor stays in current cell.                                                                    |
| xCTRL+k, enter    | Insert a horizontal line below current row, and move the cursor into the row below that line.                                                 |
| xCTRL+k, "pipe"   | Convert selected CSV region into table                                                                                                        |
| xOPT+enter        | Split rest of cell down from current cursor position, insert new line bellow if current row is last row in the table or if next line is hline |
| xCTRL+j           | Join current row and next row into one if next row is not hline                                                                               |


### Stuff that you can autocomplete while in a table

| Description                               | Howto                             |
| ----------------------------------------- | --------------------------------- |
| Get double hline ('=') under table header | Write "pipe equals" and press tab |


### Settings

```
{
    // By default Table Editor is disabled. Must set to true to enable.
    "enable_table_editor": true,

    // Set table syntax for Table Editor.
    // Valid options are: "Simple", "EmacsOrgMode", "Pandoc", "MultiMarkdown",
    //                    "reStructuredText", "Textile"
    "table_editor_syntax": "Simple",

    // Border styles
    //
    // simple: |---|---|
    // emacs: org mode |---+---|
    // grid: +---+---+
    //
    // Override border style for Table Editor
    // Valid options are: "simple", "grid", "emacs"
    "table_editor_border_style": "simple",

    // Override custom column alignment for Simple Syntax
    // This settings by default is enabled, but you can disable it.
    //
    // With this feature you can explicit set justification with format characters
    //
    // - '<' - left
    // - '>' - right
    // - '#' - center
    //
    // Example:
    //
    // | column 1 | column 2 | column 3 |
    // | <<<<<<<< | >>>>>>>> | ######## |
    // +----------+----------+----------+
    // | 1        | row 1    | c1       |
    // | 2        | row 2    | c2       |
    // | 3        | row 3    | c3       |

    // Auto align number column to right
    // By default a number column aligns to right, if you do not like this you can disable it
    "table_editor_align_number_right": false,

    // Detect header column to center
    // By default a header column aligns to center, if you do not like this you can disable it
     "table_editor_detect_header": false,

    // Keep space left
    // Some time you do not like remove leading space from a data in a column, as in next example
    //
    // | Unordered  List |   Order List  |
    // |-----------------|---------------|
    // | - item 1        | # item 1      |
    // |   - subitem 1   |   # subitem 1 |
    // |   - subitem 2   | # item 2      |
    // | - item 2        |   # subitem 2 |
    // |                 |               |
    "table_editor_keep_space_left": true

    // If table_editor_custom_column_alignment is true, supports '<', '>', '#' column alignment
    "table_editor_custom_column_alignment": false,

    // Auto align number column to right
    // By default a number column aligns to right, if you do not like this you can disable it
     "table_editor_align_number_right": false,
}
```

Simple (`'Simple'`)

```
|    Name   | Age |
|-----------|-----|
| Anna      |  20 |
| Alexander |  27 |
```

EmacsOrgMode ('`EmacsOrgMode`')

```
|    Name   | Age |
|-----------+-----|
| Anna      |  20 |
| Alexander |  27 |
```

Pandoc Grid Tables (`'Pandoc'`)

```
+-----------+-----+
|    Name   | Age |
+===========+=====+
| Anna      |  20 |
+-----------+-----+
| Alexander |  27 |
+-----------+-----+
```
