#### Question
You will be given a number and you will need to return it as a string in Expanded Form. 


#### Example
```
expandedForm(12); // Should return '10 + 2'
expandedForm(42); // Should return '40 + 2'
expandedForm(70304); // Should return '70000 + 300 + 4'
```

##### 想法
首先先找出比如(70304) => '70000 + 300 + 4' 的對應關係，
發現如果切成 array 後用 index 去計算就可以了，但是要先把順序反過來最後再倒回去


#### Solution
```
function expandedForm(num) {
    return num.toString().split('').reverse().map((item, index) => item * Math.pow(10, index))
        .filter((item) => item > 0).reverse().join(' + ')
}
```