#### Question
Bob is preparing to pass IQ test. The most frequent task in this test is to find out which one of the given numbers differs from the others. Bob observed that one number usually differs from the others in evenness. 

Help Bob — to check his answers, he needs a program that among the given numbers finds one that is different in evenness, and return a position of this number.

Keep in mind that your task is to help Bob solve a real IQ test, which means indexes of the elements start from 1 (not 0)


#### Example
```
iqTest("2 4 7 8 10") => 3 // Third number is odd, while the rest of the numbers are even
iqTest("1 2 1 1") => 2 // Second number is even, while the rest of the numbers are odd
```

##### 想法
利用 filter 可以篩出分別是奇數和偶數的矩陣，再去比較兩個矩陣的長度，就可以知道哪一個數字在其矩陣是異類


#### Solution
```
function iqTest(string) {

    let arr = string.split(' ').map(number => parseInt(number));
    let evenArr = arr.filter(number => number % 2 === 0);
    let oddArr = arr.filter(number => number % 2 !== 0);

    return evenArr.length > oddArr.length ? arr.indexOf(oddArr[0]) + 1 : arr.indexOf(evenArr[0]) + 1;
}
```