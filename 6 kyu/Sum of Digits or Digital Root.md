#### Question
Digital root is the recursive sum of all the digits in a number.

Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. This is only applicable to the natural numbers.


#### Example
```
16 -->  1 + 6 = 7
942 -->  9 + 4 + 2 = 15  -->  1 + 5 = 6
132189 -->  1 + 3 + 2 + 1 + 8 + 9 = 24  -->  2 + 4 = 6
493193 -->  4 + 9 + 3 + 1 + 9 + 3 = 29  -->  2 + 9 = 11  -->  1 + 1 = 2
```

##### 想法


#### Solution
```
function digital_root(n) {

    let arr = n.toString().split("");

    let sum = 0;
    for (let i = 0; i < arr.length; i++) {
        sum += Number(arr[i]);
    }

    if (sum >= 10) {
        sum = digital_root(sum);
    }

    return sum;
}
```