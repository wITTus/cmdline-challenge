# Randomize string

## Description

Generate a string with the characters [a-z] of arbitrary length.

## Solution

To create a random string with 50 characters in the range [a-z] ...

```bash
cat /dev/urandom | base64 -w50 | tr A-Z0-9/\+ a-z
```
