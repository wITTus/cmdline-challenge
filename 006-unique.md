# Unique

## Description

Removing duplicated lines is commonly done by piping input through sort with a following uniq. One disadvantage of this approach is the blocking nature of sort.
The challenge is: Write a non-blocking shell command which eliminates duplicates and behaves like a combination of sort and uniq.

## Test case 1

```bash
echo -e "1\n2\n3\n2" | solution
```

Shall print the following output:

```
1
2
3
```

## Test case 2

```bash
cat /dev/urandom | hexdump -C | solution
```

Shall print the same output as without solution since every line is unique.


## Solution 1

Beware, this is effectively a fork bomb as it spawns a shell per line.

```bash
cat /dev/urandom | hexdump -C | (:(){ read i && (echo "$1" | grep -q ':$i:' || echo $i; : "$1$i:";) }; : ":" done)
```

## Solution 2

Insert the line $0 into the associative array a or increment a counter.

```bash
echo -e "1\n2\n3\n2" | awk '!a[$0]++'
```
