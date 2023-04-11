# Flex Table

Fast and flexible Python library for text tables.

---

## Usage examples

1. Simplest use case
2. Custom align & and cells' width limit

### Simplest use case

This is probably the most common and yet the simplest possible usage:

```python
from flextable.table import FlexTable

# Create the tablie with 3 columns, of which IDs will be their values.
table = FlexTable(['ID', 'NAME', 'SCORE']);

# Add 2 rows to the table, assignig cells in order of appearance.
table->add_rows([
    [1, 'John', 12],
    [2, 'Tommy', 15],
]);

# Print the whole table.
print(table.render())
```

which in turn should produce this table:

```python
┌────┬───────┬───────┐
│ ID │ NAME  │ SCORE │
├────┼───────┼───────┤
│ 1  │ John  │ 12    │
│ 2  │ Tommy │ 15    │
└────┴───────┴───────┘
```

---

### Use different table renderer

The common usage of `FlexTable` library is to eventually present used the
content of the table in the nice tabular form. As the table itself is just
a data structure, "visualisation" of the table is done via the dedicated
renderer which will return the table as a string. It therefore can influence
the final look of the table, incl. the way it is formatted.

To override the renderer, simply pass instance of the renderer of your
choice to the `FlexTable`'s rendering shortcuts:

```python
renderer = PlusMinusRenderer()
print(table.render(renderer))
```

or

```python
...
renderer = PlusMinusRenderer()
print(renderer.render(table))
```

would produce table rendered using `+`, `-` and `|` characters
instead of table shaped characters:

```python
+----+-------+-------+
| ID | NAME  | SCORE |
+----+-------+-------+
| 1  | John  | 12    |
| 2  | Tommy | 15    |
+----+-------+-------+
```

**NOTE:** You can provide your own renderer (i.e. producing `HTML` or whatever you wish,
by implementing `RendererContract` in your class.

For available built-in renderers, see [flextable/renderers/](../flextable/renderers/) sources.

**HINT:** If you want to just introduce new frame characters, just extend built-in
[AsciiTableRenderer](../flextable/renderers/ascii_table_renderer.py) and provide characters of your choices
only. See i.e. [flextable/renderers/ms_dos_renderer.py](../flextable/renderers/ms_dos_renderer.py) code for
reference.

---

### Custom align and cells' width limit

```python
from flextable.table import FlexTable

# Create the list with 3 columns, of which IDs will be their values.
# The definition of 2nd column is created explicitly, using instance 
# of Column class that is automatically created for other columns.
table = FlexTable(['ID', new Column('NAME', maxWidth: 20), 'SCORE'])

table.set_column_align('SCORE', Align::RIGHT)

# Add 2 rows to the table, assignig cells in order of appearance.
# Similarly to the column above, the 2nd cell in second row is also
# created directly using instance of Cell, to gain more control. 
table.add_rows([
    [1, 'John', 12],
    [2, Cell('Tommy', Align.CENTER), 15],
])

# print the whole table using MS-DOS style frames.
renderer = MsDosRenderer()
print(renderer.render(table))
```

would produce this nicely formatted text table:

```python
╔════╦══════════════════════╦═══════╗
║ ID ║ NAME                 ║ SCORE ║
╠════╬══════════════════════╬═══════╣
║ 1  ║ John                 ║    12 ║
║ 2  ║        Tommy         ║    15 ║
╚════╩══════════════════════╩═══════╝
```

---

## License

* Written and copyrighted &copy;2023 by Marcin Orlowski <mail (#) marcinorlowski (.) com>
* Text Table is open-sourced software licensed under
  the [MIT license](http://opensource.org/licenses/MIT)
