#### Question
Write a function that takes an array of numbers (integers for the tests) and a target number. It should find two different items in the array that, when added together, give the target value. 

The indices of these items should then be returned in a tuple like so: (index1, index2).
For the purposes of this kata, some tests may have multiple answers; any valid solutions will be accepted.

The input will always be valid (numbers will be an array of length 2 or greater, and all of the items will be numbers; target will always be the sum of two different items from that array).


#### Example
```
twoSum [1, 2, 3] 4 === (0, 2)
```

##### 想法

若是有 array = [1, 2, 3], 然後要兩個兩個加總去跟 target 比較的話<br/>
會是先從 index = 0 和 index = 1, 2 去加總比較 <br/>
再來是 index = 1 和 index = 2 去加總比較<br/>
最後 index = 2 則不用跟 index = 0, 1 去加總比較，因為前面都已經比較過了<br/>


所以可以看得出來會需要兩個迴圈分別去增加 item1 和 item2 的 index
然後因為最後一個 index 可以不用比較，所以外層的迴圈可以少比一次故 numbers.length - 1

#### Solution
```
function twoSum(numbers, target) {
    for (let i = 0; i < numbers.length - 1; i++) {
        for (let j = 1; j < numbers.length; j++) {
            if (numbers[i] + numbers[j] === target) {
                return [i, j]
            }
        }
    }
}
```

