# 6. Export / Import
한 모듈 내에서 export 키워드를 앞에 붙이기만 하면 const, function 등 어떤 것이든 내보낼 수 있다. 내보내진 모듈은 다른 모듈에서 가져올 수 있는데 이 때
import 키워드가 사용된다. 예시는 다음과 같다.
```javascript
//ex.js
export const again = (string) => `${string} ${string}`;
export function big(string) {
  return `${string.toUpperCase()}`;
}
```
```javascript
//im.js
import {again, big} from './ex.js';
again('hi'); //'hi hi'
big('good morning'); //'GOOD MORNING'
```
## export default?
모듈에서 default 값으로 내보낸다면 import 할 때 어떠한 이름으로도 가져올 수 있다. 단, 변수 하나만 export 하는 경우에 export default 를 사용한다.
```javascript
//ex.js
export default function(string){
 return `${string.toUpperCase()}`
}
```
```javascript
//im.js
import big from './ex.js'; //이름이 달라도 여전히 ex.js에 있던 함수를 그대로 사용할 수 있다.
```
