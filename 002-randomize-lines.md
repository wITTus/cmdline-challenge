# Randomize lines

## Description

Sometimes it is useful to shuffle the input, i.e. bring the input into random order. For example, you have a deck of cards and you want to shuffle the cards on the command line so that the output is a random permutation. For example, if you represent the cards as tuples like "Ah As Ac Ad Kh Ks Kc Kd ..." than the output should be a random permutation like "Qs, Kh, 8d, 9h, Qh, ...".

## Solution 1

One simple solution is to use `sort`. Typically, it is used to sort the input. How can this be useful to shuffle the input? With the option -R `sort` sorts by a random hash of keys.

```bash
echo "Ah As Ac Ad Kh Ks Kc Kd" | tr ' ' '\n' | sort -R
```

## Solution 2

```bash
echo "Ah As Ac Ad Kh Ks Kc Kd" | \
     for i in `cat`; \
         do echo $RANDOM $i; done | sort -n | cut -d\  -f2
```
