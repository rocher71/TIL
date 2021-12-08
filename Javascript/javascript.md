# JAVASCRIPT

## 배열

* idx로 배열의 요소 삭제하는 법
```javascript
let arr = [1, 2, 3, 4, 5];
const idx = arr.indexOf(4);
if(idx > -1) arr.splice(idx,1);
// [1, 2, 3, 5]
```

## 변수

* 깊은 복사 하는 법
```html
// cdn
<script src="https://cdn.jsdelivr.net/npm/lodash@4.17.21/lodash.min.js"></script>
<script src="lodash.js"></script>
<script src="//cdnjs.cloudflare.com/ajax/libs/underscore.js/1.5.2/underscore-min.js"></script>
<script>
  import * as _ from 'lodash';  
  let copyVar = _.cloneDeep(originData);
</script>
```
