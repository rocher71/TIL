# Props & Emit

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
  props: {
    key: vaue
  }
}
```
