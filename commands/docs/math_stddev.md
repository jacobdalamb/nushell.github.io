---
title: math stddev
categories: |
  math
version: 0.90.0
math: |
  Returns the standard deviation of a list of numbers, or of each column in a table.
usage: |
  Returns the standard deviation of a list of numbers, or of each column in a table.
feature: default
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for math

<div class='command-title'>{{ $frontmatter.math }}</div>

## Signature

```> math stddev {flags} ```

## Flags

 -  `--sample, -s`: calculate sample standard deviation (i.e. using N-1 as the denominator)


## Input/output types:

| input        | output |
| ------------ | ------ |
| list\<number\> | number |
| record       | record |
| table        | record |
## Examples

Compute the standard deviation of a list of numbers
```nu
> [1 2 3 4 5] | math stddev
1.4142135623730951
```

Compute the sample standard deviation of a list of numbers
```nu
> [1 2 3 4 5] | math stddev --sample
1.5811388300841898
```

Compute the standard deviation of each column in a table
```nu
> [[a b]; [1 2] [3 4]] | math stddev
╭───┬───╮
│ a │ 1 │
│ b │ 1 │
╰───┴───╯
```
