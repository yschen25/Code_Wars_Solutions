#### Question
Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.

#### Example
```
uniqueInOrder('AAAABBBCCDAABBB') == ['A', 'B', 'C', 'D', 'A', 'B']
uniqueInOrder('ABBCcAD')         == ['A', 'B', 'C', 'c', 'A', 'D']
uniqueInOrder([1,2,2,3,3])       == [1,2,3]

```

##### 想法
利用 filter 去篩值即可

#### Solution
```
// Method 1
function(iterable) {

    let output = [];
    for (let i = 0; i < iterable.length; i++) {
        let curr = iterable[i];
        let next = iterable[i + 1];

        if (curr !== next) {
            output.push(curr);
        }
    }

    return output;
}
```

```
// Method 2
function(iterable) {
    return [...iterable].filter((item, index) => item !== iterable[index + 1])
}
```