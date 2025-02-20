---
title: dfr last
categories: |
  dataframe
version: 0.90.0
dataframe: |
  Creates new dataframe with tail rows or creates a last expression.
usage: |
  Creates new dataframe with tail rows or creates a last expression.
feature: dataframe
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for dataframe

<div class='command-title'>{{ $frontmatter.dataframe }}</div>


::: warning
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::
## Signature

```> dfr last {flags} (rows)```

## Parameters

 -  `rows`: Number of rows for tail


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Create new dataframe with last rows
```nu
> [[a b]; [1 2] [3 4]] | dfr into-df | dfr last 1
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 3 │ 4 │
╰───┴───┴───╯

```

Creates a last expression from a column
```nu
> dfr col a | dfr last

```
