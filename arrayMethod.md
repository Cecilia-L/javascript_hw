# 4. Array Methods (map, reduce, filter, slice, splice)
## (1) map()
배열 내의 모든 원소에 대하여 제공된 함수를 호출하고 결과를 모아 새로운 배열을 return 하는 메소드 인자. (단, 기존의 객체는 수정하지 않는 메소드입니다.)
<br>
사용법: 배열.map((요소, 인덱스, 배열) => {return 요소});
```javascript
const number = [1,2,3];
let result = number.map((v) => {
  return v + 1;
});
result; // [2,3,4]
```

## (3) filter()
배열의 원소 중 제공된 함수를 통과하는 원소만 반환하는 메소드 인자

```javascript
const array = [1,2,3,4];
array.filter(el => el < 3); // [1,2]
array; //[1,2,3,4]
```

## (4) slice()
배열의 start에 해당하는 요소부터 end 바로 전의 요소까지 선택하여 새로운 배열을 만듭니다.<br>
형태: array.slice(start,end) //start와 end 에는 숫자가 들어갑니다. 
```javascript
const array = [1,2,3,4,5]
console.log(array.slice(2,4)); // [3,4]
```
## (5) splice()
배열 중간의 원소를 삭제하거나 추가하고 싶을 때 사용하는 메소드입니다.<br>
형태: splice(인덱스, 인덱스부터 삭제할 원소의 개수)
```javascript
const array = [1,2,3,4,5]
console.log(array.splice(2,1)); //[3] 즉 삭제된 원소가 등장함
console.log(array); //[1,2,4,5]
```

