+++
title = "Natural sort is unnatural"
date = 2022-03-05
+++

If you were to create files with the following names in macOS:
```
-0.27
a-103
a3
```


Ever notice that macOS can sort folders somewhat strangely?

Why natural sort? When you sort lexicographically, you can end up with

```
1
10
2
```

In response to these complaints, natural sort was devised

- Sort by length, then lexicographically

## Python Implementation

A key function for pythons sort function

<details>


```python
def mykey(string: str) -> tuple:
    """create sort key"""
    return tuple(
        (False, int(part), len(string)) if part.isdigit() else (True, part)
        for part in re.findall(r"\D+|\d+", string.lower())
    )
```

</details>

## Test cases

```
012
01b
10a
12a
1a0
1ab
1b0
2a
a12
abc

-4.5
-5
0
1
```

# Further reading

- [Sorting for Humans : Natural Sort Order](https://blog.codinghorror.com/sorting-for-humans-natural-sort-order/)
- [Natural sort order - Wikipedia](https://en.wikipedia.org/wiki/Natural_sort_order)
- [macos - How does finder sort folders when they contain digits and characters? - Ask Different](https://apple.stackexchange.com/questions/362696/how-does-finder-sort-folders-when-they-contain-digits-and-characters)