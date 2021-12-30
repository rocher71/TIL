# Props & Emit
v-model은 동일 component 내에서 입력 값을 component data와 바인딩 하기에 최적인 directive이다.
그러나 v-model로 부모, 자식, 형제 component간에 data binding을 하기에는 data흐름을 추적하기 쉽지 않고, 디버깅 측면에서 적합하지 않다. 다른 component간에는 단방향 data binding directive 사용하는 것이 권장된다.
단방향 data binding은 props와 emit을 통해 구현 가능하다.

### Props
부모 -> 자식 데이터 전달

### Emit
자식 -> 부모 데이터 전달


## 규칙
1. 전달 키와 받는 키가 동일해야함.
2. 받는 키를 등록해줘야 함.

#### 참고
1. import 코드가 포함 되어있는 파일이 부모 component임.

* 자식 component 파일에서 다음과 같이 사용

```javascript
//자식 component
export default{
  props: ["membrId", 'membrCnt'],
}
```

<br>

## Watch
child component에서 사용하는 메소드(?)로 부모 컴포넌트에서 쏴주는 props 값이 계속 바뀔 때, 이 값을 그때 그때 받아오기 위해 쓰임.
* 받아오려는 props의 이름과 같은 이름으로 watch 내부에 메소드를 선언해주면 된다.
```JAVASCRIPT
export default {
  props: ['membrID'],
  watch: {
    membrID(newVal) {
      console.log("membrID : ", newVal);
    },
  },
  methods: {
    log(){
      console.log('membrId : ', this.membrId);
  }
```
