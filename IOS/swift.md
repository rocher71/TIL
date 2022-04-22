# Collection 타입

## Array

- 선언

```swift
var numbers: Array<Int> = Array<Int>()
var names = [String]()
var names: [String] = []
```

- 전체적인 사용법

```swift
var numbers: Array<Int> = Array<Int>()
numbers.append(1)
numbers.append(2)
numbers.append(3) //[1, 2, 3]

numbers.insert(4, at: 2) //[1, 2, 4, 3]
numbers.remove(at: 0) //[2, 4, 3]
```

## Dictionary

순서 없이 key, value 쌍으로 사용되는 타입

- 선언

```swift
var dic: Dictionary<String, Int> = Dictionary<String, Int>()
var dic2: [String: Int] = [:]
```

- 전체적인 사용

```swift
var dic: [String: Int] = ["age":21]
dic["김철수"] = 5
dic["이영희"] = 3 //["age":21, "김철수":5, "이영희":3]

dic["이영희"] = 6 //["age":21, "김철수":5, "이영희":6]

dic.removeValue(forKey: "이영희")
//["age":21, "김철수":5]
```

## Set

순서가 없고, 멤버가 유일한 것을 보장하는 타입

```swift
var set: Set = Set<Int>() //이 형태로만 선언 가능

set.insert(10)
set.insert(20)
set.insert(30)
set.insert(30) // {30, 20, 10} 순서대로 정렬x, 중복 저장x

set.remove(20) // {10, 30}
```
