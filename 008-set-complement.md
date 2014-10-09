# Set Complement

## Description

Sometimes you need to find out which entries (existing in the first file) are missing in a second file.
The challenge is: Write a command which reads two files and prints lines which are unique to the first file only.

## Test case 1

File A:
```
one
two
three
four
```

File B:

```
three
four
five
six
```

The solution applied on both files shall print the following output:

```
one
two
```

## Solution 1

The best approach available is done by using the lesser known command `comm`.

```bash
comm -23 <(sort A) <(sort B)
```

Alternatively, grep may be used. But beware, this approach is using a pattern file. That means, `o.e` would falsely match as well.

```bash
grep -vf B A
```

