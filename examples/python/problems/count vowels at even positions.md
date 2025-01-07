---
title: Count vowels at even positions
---

# Problem Statement

Given a string `s`, return the count of each vowel present at even positions in the given string
(case insensitive). If the string has no vowels at even positions, return an empty dictionary.

**Example**
```
count_vowels(["hello"]) # Output: {'e': 1}
count_vowels(["rhythm"]) # Output: {}
count_vowels(["PYTHON"]) # Output: {'o': 1}

```

# Solution

```py3 test.py -r 'python test.py'
<template>
def count_vowels(s: str) -> dict:
    '''
    Given a string, count the occurence of each vowel (a, e, i, o, u) in the string.

    Arguments:
    s: str - input string.

    Return: dict - dictionary with vowel count.
    '''
    <los>...</los>
    <sol>
    vowels = 'aeiou'
    word=s.lower()
    size=len(s)
    vowel_count = {v: 0 for v in vowels}
    for x in range(size):
        if word[x] in vowels:
            if x % 2 == 0:
                vowel_count[word[x]] += 1
    return {k: v for k, v in vowel_count.items() if v > 0}</sol>
</template>

<suffix_invisible>
{% include '../function_type_and_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```
s = "hello"
modify_check(
    lambda x: count_vowels(x),
    s, {'e': 1},
    should_modify=True
)
```

## Output 1

```
{'e': 1}
```

## Input 2

```
s = "aeiou"
modify_check(
    lambda x: count_vowels(x),
    s, {'a': 1, 'i': 1, 'u': 1},
    should_modify=True
)
```

## Output 2

```
{'a': 1, 'i': 1, 'u': 1}
```

## Input 3

```
s = "xyz"
modify_check(
    lambda x: count_vowels(x),
    s, {},
    should_modify=True
)
```

## Output 3

```
{}
```

# Private Test Cases

## Input 1

```
s = "aeiouAEIOU"
modify_check(
    lambda x: count_vowels(x),
    s, {'a': 2, 'e': 2, 'i': 2, 'o': 2, 'u': 2},
    should_modify=True
)
s = "The quick brown fox"
modify_check(
    lambda x: count_vowels(x),
    l, {"e": 1, "u": 1, "o": 1},
    should_modify=True
)
s = ""
modify_check(
    lambda x: count_vowels(x),
    l, {},
    should_modify=True
)
```

## Output 1

```
{'a': 2, 'e': 2, 'i': 2, 'o': 2, 'u': 2}
{"e": 1, "u": 1, "o": 1}
{}
```
