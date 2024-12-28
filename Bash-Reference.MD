# Bash (Bourne Again SHell) Reference
## Basic Shell Features
### 3.5 Shell Expansions
#### 3.5.1 Brace Expansion
Brace expansion is a mechanism by which arbitrary strings may be generated

1. Brace expansions may be nested.
2. The results of each expanded string are not sorted; left to right order is preserved
3. The preamble is prefixed to each string contained within the braces, and the postscript is then appended to each resulting string, expanding left to right.
4. For Numbers, A sequence expression takes the form `{x..y[..incr]}`, where x and y are either integers or letters, and incr, an optional increment, is an integer. Note - works only in `bash`
5. When integers are supplied, the expression expands to each number between x and y, inclusive.
6. Supplied integers may be prefixed with '0' to force each term to have the same width. When either x or y begins with a zero,
7. ',' comma within brackets means **OR** 

```bash
$ echo a{d,c,b}e
ade ace abe

$ echo {A..C}-f-{1..2}
A-f-1 A-f-2 B-f-1 B-f-2 C-f-1 C-f-2

$ echo {A..Z..2}
A C E G I K M O Q S U W Y

$ echo /bash/{old,new,dist,bugs}
/bash/old /bash/new /bash/dist /bash/bugs

$ echo /usr/{ucb/{ex,edit},lib/{ex?.?*,how_ex}}
/usr/ucb/ex /usr/ucb/edit /usr/lib/ex?.?* /usr/lib/how_ex
```