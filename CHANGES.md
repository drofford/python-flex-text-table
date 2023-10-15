```ascii
#####.##....#####.##...##...######.#####.##...##.######...######...#....#####..##....#####
##....##....##.....##.##......##...##.....##.##....##.......##....###...##..##.##....##...
##....##....##......###.......##...##......###.....##.......##...##.##..##..##.##....##...
####..##....####.....#........##...####.....#......##.......##..##...##.#####..##....####.
##....##....##......###.......##...##......###.....##.......##..#######.##..##.##....##...
##....##....##.....##.##......##...##.....##.##....##.......##..##...##.##..##.##....##...
##....#####.#####.##...##.....##...#####.##...##...##.......##..##...##.#####..#####.#####
```

Fast and flexible Python library for text tables.

---

# Changes

* dev
  * Added option to control column's title visibility.
  * Added `set_no_data_label()` to override default `NO DATA` shown when rendering empty table.
  * Fixed rendering of middle row separator when 'NO DATA' label is used


* 2.6.0 (2023-05-05)
  * Fixed column container not updating width of columns correctly.
  * Simplified header rendering code.
  * Corrected typehints.
  * Added more tests.
  * Updated docs.
  * `FlexTable` c'tor now also accepts rows for instant initialization.


* 2.5.0 (2023-04-11)
  * Initial public release.
