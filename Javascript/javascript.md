# JAVASCRIPT

## 배열

* idx로 배열의 요소 삭제하는 법 : "splice"
```javascript
let arr = [1, 2, 3, 4, 5];
const idx = arr.indexOf(4);
if(idx > -1) arr.splice(idx,1);
// [1, 2, 3, 5]
```
* 객체 배열에서 value값으로 index 찾기
```javascript
let arr = [
  {cd : 55, name : "영희"},
  {cd : 38, name : "철수"}];
let idx = arr.findIndex(i=>i.name == "철수");
//idx : 1
```
여기서 i는 꼭 i가 아니어도 된다. obj 등등도 가능.

## 변수

* 깊은 복사 하는 법 : "cloneDeep"
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


## Textarea 줄바꿈 그대로 db에 입력하고 출력하기
* db에 저장하기 전에 ```\n``` -> ```<br/>```로 변환,  <br>
  가져온 후 출력하기 전 ```<br/>``` -> ```\n``` 변환
```html
<!-- textarea에 wrap="hard", cols="~" 속성을
꼭 넣어줘야 한다고 하는데, 확인은 안해봤다. -->
<textarea model="cntnt" wrap="hard" cols="30"></textarea>
<button onclick="saveDB(cntnt);">저장</button>
<span>{{dbCntnt}}</span>
<script>
function saveDB(cntnt){
  //\n -> <br/>
  cntnt = cntnt.replace(/(?:\r\n|\r|\n)/g,'<br/>');
  //db 저장
}
function getDB(){
  //http 통신해서 가져옴
  //<br/> -> \n
  dbCntnt = dbCntnt.replace(/<br\s*\/?>/mg,'\n');
}
</script>
```
