# Flex Text Table

Fast and flexible Pyhon library for text tables.

[![Unit tests](https://github.com/MarcinOrlowski/python-flex-text-table/actions/workflows/unittests.yml/badge.svg?branch=master)](https://github.com/MarcinOrlowski/python-flex-text-table/actions/workflows/unittests.yml)
[![MD Lint](https://github.com/MarcinOrlowski/python-flex-text-table/actions/workflows/markdown.yml/badge.svg?branch=master)](https://github.com/MarcinOrlowski/python-flex-text-table/actions/workflows/markdown.yml)
[![GitHub issues](https://img.shields.io/github/issues/MarcinOrlowski/python-flex-text-table.svg)](https://github.com/MarcinOrlowski/python-flex-text-table/issues)

[![PyPI version](https://badge.fury.io/py/flex-text-table.svg)](https://badge.fury.io/py/flex-text-table)
[![Downloads](https://img.shields.io/pypi/dm/flex-text-table)](https://pypi.org/project/flex-text-table/)
[![Python Version](https://img.shields.io/pypi/pyversions/flex-text-table.svg)](https://pypi.org/project/flex-text-table/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Library is also available as [PHP package](https://github.com/MarcinOrlowski/php-text-table).

---

Table of contents

1. [Features](#features)
1. [Installation & requirements](docs/setup.md)
1. [Examples](docs/examples.md)
1. [License](#license)

---

## Features

1. Simple API, easy to use,
2. Lightweight (no additional dependencies),
3. Production ready.

---

## Usage examples

Simples possible usage:

```python
table = FlexTable(['ID', 'NAME', 'SCORE'])
table.add_rows({
    [1, 'John', 12],
    [2, 'Tommy', 15],
})
print(table.render())
```

would produce nice text table:

```ascii
┌────┬───────┬───────┐
│ ID │ NAME  │ SCORE │
├────┼───────┼───────┤
│ 1  │ John  │ 12    │
│ 2  │ Tommy │ 15    │
└────┴───────┴───────┘
```

See more [usage examples](docs/examples.md).

---

## License

* Written and copyrighted &copy;2023 by Marcin Orlowski <mail (#) marcinorlowski (.) com>
* Text Table is open-sourced software licensed under
  the [MIT license](http://opensource.org/licenses/MIT)
