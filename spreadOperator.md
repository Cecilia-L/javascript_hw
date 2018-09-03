# 5. Spread Operator(Array/Object Spread)
## Spread Operator란?
ES6에 추가된 문법으로 ...을 사용해서 배열의 값들을 받아오거나 편하게 확장시킬 수 있게 해줍니다. 
```javascript
let array = [1,2,3];
console.log(array); //[1,2,3]
console.log(...array); // 1 2 3
```
## (1) Array Spread
array 앞에 '...'을 찍어서 선언합니다.
```javascript
let num = [1,2,3]
let num2 =[4,5,6]
let spread = [0, ...num , ...num2 ];
console.log(spread); // [0, 1, 2, 3, 4, 5, 6]
```
```javascript
let arr = [1,2,3,4]
let [arr1, arr2, ...arr3] = arr; // arr1은 1, arr2 는 2, arr3은 [3,4]라는 값을 가지게 됩니다.
```
## (2) Object Spread
```javascript
let str = [{name:1}, {name:2}];

console.log(str); //[{name:1}, {name:2}]
console.log(...str); //{ name: 1 } { name: 2 }
```
