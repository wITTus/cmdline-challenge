# Multi camelCase to PascalCase

## Description

Consider many words of which some may be camel case or not. Concatenate them all and transform _camelCase_ to _PascalCase_

## Test case 1

```bash
echo 'Word myWordBlub myBlah' | solution
```

Shall print the following output:

```
WordMyWordBlubMyBlah
```

## Solution 1

Split words up into several lines and transform first characters to upper case, then join lines.

```bash
echo 'Word myWordBlub myBlah' | for i in `</dev/stdin`; do echo `echo $i | cut -c1 | tr 'a-z' 'A-Z'``echo $i | cut -c2-`; done | tr -d '\n'; echo
```

## Solution 2

Using perl:

```bash
echo 'Word myWordBlub myBlah' | perl -pe 's# [a-z]#uc $&#ge' | tr -d \ 
```
