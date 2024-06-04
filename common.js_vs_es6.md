# CommonJS vs ES6

## CommonJS 전체 내보내기
```
// exports
const obj = {
    num: 100,
    sum: function(a, b) {
        return a+b;
    },
};

module.exports = obj;

// require
const obj = require('./exportFile.js);
console.log(obj.num);
console.log(obj.sum(10, 20));
```
## CommonJS 개별 내보내기
```
// exports
exports.name = 'James';
exports.sayHello = function(){
    return 'Hello';
};

// require
const {name, sayHello} = require('./exportFile.js);
console.log(name);
console.log(sayHello());
```
## ES6 전체 내보내기
```
// export
const obj = {
    num: 100,
    sum: function(a, b) {
        return a+b;
    },
};

export default obj;

// import
import obj from './exportFile.js';
console.log(obj.num);
console.log(obj.sum(10, 20));
```
## ES6 개별 내보내기
```
// export
export const name = 'James';
export function sayHello(){
    return 'Hello';
}

// import
import {name, sayHello} from './exportFile.js';
console.log(name);
console.log(sayHello());

// 또는 import할 때 오브젝트로 묶을 수 있다.
import * as obj from './exportFile.js';
console.log(obj.name);
console.log(obj.sayHello());
```
## node.js에서 ES6 문법 사용법
export / import는 node.js에서 바로 사용할 수 없다. package.json에서 설정을 해주어야 하는데 `"type":"module"`을 추가해주면 된다. 