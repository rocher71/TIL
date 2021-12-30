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
<!-- :checked attribute 추가해주기! -->
<input type="radio" :checked="fruit == '사과'">
```
```html
<!-- 전체 코드 -->
<input type="radio" name="radioBtn" id="apple" :checked="fruit == '사과'"/>
<label for="apple">사과</label>
<input type="radio" name="radioBtn" id="banana" :checked="fruit == '바나나'"/>
<label for="banana">바나나</label>
<!-- script -->
<script>
export default{
  data(){
    fruit: "바나나"
  }
}
</script>
```


## filter
Vue는 텍스트 형식화를 적용할 수 있는 필터를 지원한다. Mustache 구문나 'v-bind' 표현법을 이용할 때 사용가능하다.
- 숫자에 콤마 삽입하기
```html
<span>{{price | addCommaToNum}}</span>
<!-- script -->
<script>
export default{
  data(){
    price: "1000000"
  },
  filters:{
    addCommaToNum: function (str) {
      return String(str).replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
  }
}
</script>
<!-- 출력 : 1,000,000 -->
```

<br>

## Data Binding
* href 바인딩 하는법 - 포인트는 `${}` !
```html
<tr v-for="(list, idx) in showList" v-bind:key="idx">
  <td>
    <a :href="`/order/${list.id}`">클릭</a>
  </td>
</tr>
```

<br>

## Moment - db date 처리하기
그냥 시간을 Date객체로 가져오면 다 우리나라 시간이랑 시차 차이가 난다.
moment를 사용하면 편리하게 처리할 수 있다.
```html
<span>{{ order.call_dt | moment("YYYY-MM-DD") }}</span>
<span>{{ order.call_dt | moment("YYYY-MM-DD HH:mm:ss") }}</span>
//script
<script>
import Vue from "vue";
import VueMoment from "vue-moment";
Vue.use(VueMoment);
let dateFormSec = this.$moment(this.originalDate).format("YYYY-MM-DD hh:mm:ss");
let dateFormDt = this.$moment(this.originalDate).format("YYYY-MM-DD");
</script>
```
