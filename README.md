# Spreadsheets

You're given a CSV file, titled `transactions.csv`. If you have a keen eye and inspect the contents of the file
you'll realize that this isn't a traditional comma-separated values file.

- The delimiter is the pipe operator `|`
- Named columns have an exclamation mark prefix `!`
- Named columns appear anywhere in the file as long as they maintain the same column count
- Cells can have equations prefixed with `=`

The goal is to take `transactions.csv` and compute what needs to be computed producing a file
that contains all the static values + all the equations resolved.

We ask you to do this in a language you are not familiar with.

### Operations & Equations

Any computable expression in the CSV must be prefixed with `=`. The expression
language is very similar to excel formulas, it supports basic arithmetic expressions
as well as function calls that provide additional features like comparisons,
string concatenations and other useful utility functions.

#### Operations

- `^^` Copies the formula from the cell above in the same column, with some special evaluation rules
- `(A..Z)n` references a cell by a combination of a column-letter+row-number. Ex: A2 B3
- `A^` copies the evaluated result of the cell above in the same column
- `!label` Columns can have labels, which allows this ability to have different column groups in the same file as long as the number of columns stays consistent
- `A^v` copies the evaluated result of the last cell in the specified column from the most recently available column group that has data in that specified column
- `@label<n>` References a specific labeled column and a specific row `n` under that column relative to where the column was labeled. This is a reference operator with relative row traversal