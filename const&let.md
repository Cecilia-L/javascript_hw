# 2. const & let
기존에는 JavaScript에서 변수를 선언하는 방법은 var 를 이용하는 것 뿐이었으나, ES6로 넘어가면서 let과 const라는 새로운 선언방법이 생겼습니다. const
와 let 은 각각 어떤 공통점과 차이점이 있는지 살펴보겠습니다.
## (1) const와 let의 공통점
**첫째**, const와 let로 선언한 변수의 범위는 블록 단위로, {} 로 감싸고 있는 범위 내에서만 변수가 유효합니다. 예시를 통해 보면 유효범위에 대해서 쉽게 
이해할 수 있습니다.
```javascript
let name = 'Cecilia';
console.log(name); // Cecilia

if (true) {
  let name = 'Billy';
  console.log(name); // Billy
}
console.log(name); //Cecilia
```
위의 예시에서 let 대신 const가 쓰여도 마찬가지로 같은 결과가 나오게 됩니다.<br>
**둘째**, const와 let은 엄격합니다. 앞서 선언한 변수를 다시 선언하면 다음과 같이 오류를 발생시킵니다.
```javascript
const food = 'pasta';
const food = 'chicken'; //TypeError: Duplicate declaration "food"(중복 선언)
```

## (2) const와 let의 차이점
**const는**
string, number, boolean, null, undefined에서 상수로 동작합니다. 따라서 **단순형**의 경우, 상수로 사용하는 경우에는 const로, 
값의 변경이 있는 경우에는 let으로 변수를 선언하는 것이 바람직합니다.
하지만 **참조형**의 경우(array, object, function), const로 선언해도 멤버의 값을 조작하는 것이 가능하기 때문에 const로 선언하는 것이 바람직합니다. 예를 들어보겠습니다.
```javascript
const number = [1,2];
const yb = number; // yb는 number를 참조한다.

number.push(3);
yb[0] = 10;

console.log(number, yb) //[10,2,3] [10,2,3]
```
```javascript
const animal = {
  type: "dog",
  age: 3
};
animal.type = "cat";
console.log(animal); //{type: 'cat', age: 3}
```
