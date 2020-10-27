#### Question
Welcome. In this kata, you are asked to square every digit of a number and concatenate them. Note: The function accepts an integer and returns an integer
#### Example
```
9119 => 811181 (9^2 = 81, 1^1 = 1, 1^1 = 1, 9^2 = 81)
```

##### 想法


#### Solution
```
// Method 1
let str = '';
num.toString().split("").forEach(function(item, index, array) {
    arr.push(parseInt(item) * parseInt(item))
    str += (parseInt(item) * parseInt(item))
})

return parseInt(str);
```

```
// Method 2
let arr = [];
for (let i = 0; i < num.toString().split("").length; i++) {
    arr.push(parseInt(strArr[i]) * parseInt(strArr[i]))
}

return parseInt(arr.join(''));

```

```
// Method 3
return  Number(num.toString().split("").map((item) => Number(item) * Number(item)).join(''));
```

```
// Method 4
return  Number(num.toString().split("").map((item) => item * item).join(''));
```