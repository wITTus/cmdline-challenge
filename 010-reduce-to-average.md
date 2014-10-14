# Reduce to average

## Description

At times you need to perform numerical tasks on simple tables. In this case, calculate the average of values found by a common key. Do this for every key and the outcome should be a map of "KEY" to "AVG VALUE" entries.

## Test case 1

```bash
$ echo -e '10 85\n10 25\n10 7\n20 80\n20 90\n99 5\n99 30\n99 55\n99 10'
10 85
10 25
10 7
20 80
20 90
155 5
155 30
155 55
155 10
```

The solution applied to the input above shall print the following output:

```
10 39
20 85
155 25
```

## Solution 1

