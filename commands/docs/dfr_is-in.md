---
title: dfr is-in
categories: |
  expression
version: 0.90.0
expression: |
  Creates an is-in expression.
usage: |
  Creates an is-in expression.
feature: dataframe
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for expression

<div class='command-title'>{{ $frontmatter.expression }}</div>


::: warning
Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag
:::
## Signature

```> dfr is-in {flags} (list)```

## Parameters

 -  `list`: List to check if values are in


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Creates a is-in expression
```nu
> let df = ([[a b]; [one 1] [two 2] [three 3]] | dfr into-df);
    $df | dfr with-column (dfr col a | dfr is-in [one two] | dfr as a_in)
╭───┬───────┬───┬───────╮
│ # │   a   │ b │ a_in  │
├───┼───────┼───┼───────┤
│ 0 │ one   │ 1 │ true  │
│ 1 │ two   │ 2 │ true  │
│ 2 │ three │ 3 │ false │
╰───┴───────┴───┴───────╯

```
