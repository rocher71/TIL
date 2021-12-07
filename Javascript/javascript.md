# JAVASCRIPT

## 배열

* idx로 배열의 요소 삭제하는 법
```javascript
let arr = [1, 2, 3, 4, 5];
const idx = arr.indexOf(4);
if(idx > -1) arr.splice(idx,1);
// [1, 2, 3, 5]
```
