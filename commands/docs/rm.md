---
title: rm
categories: |
  filesystem
version: 0.90.0
filesystem: |
  Remove files and directories.
usage: |
  Remove files and directories.
feature: default
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for filesystem

<div class='command-title'>{{ $frontmatter.filesystem }}</div>

## Signature

```> rm {flags} (filename) ...rest```

## Flags

 -  `--trash, -t`: move to the platform's trash instead of permanently deleting. not used on android and ios
 -  `--permanent, -p`: delete permanently, ignoring the 'always_trash' config option. always enabled on android and ios
 -  `--recursive, -r`: delete subdirectories recursively
 -  `--force, -f`: suppress error when no file
 -  `--verbose, -v`: print names of deleted files
 -  `--interactive, -i`: ask user to confirm action
 -  `--interactive-once, -I`: ask user to confirm action only once

## Parameters

 -  `filename`: The file or files you want to remove.
 -  `...rest`: Additional file path(s) to remove.


## Input/output types:

| input   | output  |
| ------- | ------- |
| nothing | nothing |

## Examples

Delete, or move a file to the trash (based on the 'always_trash' config option)
```nu
> rm file.txt

```

Move a file to the trash
```nu
> rm --trash file.txt

```

Delete a file permanently, even if the 'always_trash' config option is true
```nu
> rm --permanent file.txt

```

Delete a file, ignoring 'file not found' errors
```nu
> rm --force file.txt

```

Delete all 0KB files in the current directory
```nu
> ls | where size == 0KB and type == file | each { rm $in.name } | null

```
