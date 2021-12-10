# JAVASCRIPT

## html에서 if문

* v-if, v-else-if, v-else
```html
<div v-if="isA == true">
  A
</div>
<div v-else-if="isB == true">
  B
</div>
<div v-else>
  C
</div>
```
v-else 뒤에는 아무것도 안 써도 됨.

## radio버튼
- script에 있는 변수값에 따라 미리 check
```html
// :checked attribute 추가해주기!
<input type="radio" :checked="fruit == '사과'">
```
```html
//전체 코드
<input type="radio" name="radioBtn" id="apple" :checked="fruit == '사과'"/>
<label for="apple">사과</label>
<input type="radio" name="radioBtn" id="banana" :checked="fruit == '바나나'"/>
<label for="banana">바나나</label>
//script
<script>
export default{
  data(){
    fruit: "바나나"
  }
}
</script>
```
