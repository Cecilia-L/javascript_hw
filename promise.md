# 1. Promise
## (1) Promise란?
**Promise란** 
자바스크립트 비동기 처리에서 사용되는 객체입니다.
*(비동기 처리란 특정 코드의 실행이 완료될 때까지 기다리지 않고 다음 코드를 먼저 수행하는 javascript의 특성)*
Promise 패턴을 사용하면 비동기 작업들을 순차적으로 진행하거나 병렬로 진행하는 등의 컨트롤이 보다 수월해지고 코드의 가독성이 좋아진다는 장점이 있습니다.
Promise는 '지금은 없는데 이상이 없으면 이따가 줄거고 없으면 알려줄게~' 라는 약속이라고 생각하면 됩니다. Promise는 4가지의 상태(state)가 될 수 있는데, 
그 종류는 
**pending(약속 수행 중), fulfilled(약속이 지켜진 상태), rejected(약속이 어떤 이유로 인해 못 지켜진 상태), settled(약속이 지켜졌든 안 지켜
졌든 결론이 나 있는 상태)**
입니다.

## (2) Promise 기초(선언부와 실행부)
```javascript
//Promise 선언
var _promise = function (param) {
  return new Promise(function (resolve, reject){
  // 비동기를 표현하기 위해 setTimeout 함수를 사용
    window.setTimeout(function () {
    // parameter가 참이면
      if (param) {
      //해결됨!
        resolve("해결 완료")
      }
      // parameter
      else{
      //실패
      reject(Error("실패!"));
      }
    }, 3000);
  }); 
};

//promise 실행
_promise(true)
.then(function (text) {
  //성공이라면
  console.log(text);
},
function (error){
  //실패라면
  console.log(error)
});
```
선언부에서는 비동기 작업이 끝난 뒤 결과물을 약속대로 잘 줄 수 있다면 첫번째 parameter로 주입되는 resolve 함수를 호출하고, 실패한다면 두번째 parameter
로 주입되는 reject 함수를 호출하게 됩니다.<br>
실행부에서는 _promise()를 호출하면 Promise 객체가 return 되고 이 객체에는 정상적으로 비동기작업이 마쳤을 때 호출하는 then이라는 API가 있습니다.
then API를 호출해서 비동기 작업이 완료되면 그 결과에 따라 성공 혹은 실패 메시지가 console log에 뜹니다. 
