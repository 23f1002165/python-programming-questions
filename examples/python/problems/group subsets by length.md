---
title: Group subsets by length.
---

# Problem Statement

Write a function named subset that accepts a set of positive integers as arguments and returns a
dictionary where the keys are subset lengths, and the values are lists of subsets of that length.

**Note:** The function should include the empty subset.

**Input Format:** Comma seperated integers in a single line.  

**Output Format:** Dictionary where keys are subset sizes, and values are lists of subsets of that size.

**Sample Input**
```
1,2,3
```
**Sample Output**
```
{
  0: [[]],
  1: [[1], [2], [3]],
  2: [[1, 2], [1, 3], [2, 3]],
  3: [[1, 2, 3]]
}
```

# Solution
```py test.py -r 'python test.py' 
<prefix>
def subset(s:set) -> dict:
    '''
    Return all subsets of a given set
    and group them by size.
    '''
</prefix>
<template>
    <sol>
    result = [[]]
    for x in s:
        for y in range(len(result)):
            result.append(result[y] + [num])
    
    grouped = {}
    for subset in result:
        key = len(subset)
        if key not in grouped:
            grouped[key] = []
        grouped[key].append(subset)
    
    return grouped</sol><los>...</los>
</template>
<suffix>
# Driver code
l = set(map(int, input().split(',')))
print(subset(s))
</suffix>
```

# Public Test Cases

## Input 1

```
1,2,3
```

## Output 1 

```
{
  0: [[]],
  1: [[1], [2], [3]],
  2: [[1, 2], [1, 3], [2, 3]],
  3: [[1, 2, 3]]
}
```


## Input 2

```
4,5
```

## Output 2

```
{
  0: [[]],
  1: [[4], [5]],
  2: [[4, 5]]
}
```


# Private Test Cases

## Input 1

```
6
```

## Output 1

```
{
  0: [[]],
  1: [[6]]
}
```

## Input 2

```
7,8,9,10
```

## Output 2

```
{
  0: [[]],
  1: [[7], [8], [9], [10]],
  2: [[7, 8], [7, 9], [7, 10], [8, 9], [8, 10], [9, 10]],
  3: [[7, 8, 9], [7, 8, 10], [7, 9, 10], [8, 9, 10]],
  4: [[7, 8, 9, 10]]
}
```

## Input 3

```
10,20,30
```

## Output 3

```
{
  0: [[]],
  1: [[10], [20], [30]],
  2: [[10, 20], [10, 30], [20, 30]],
  3: [[10, 20, 30]]
}
```
