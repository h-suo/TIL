4월 27일 목요일

---
## Optional
값의 없거나 래핑된 값이 있음을 나타내는 타입

### Optional Binding
흔히 사용하는 if let, guard let, Switch를 이용해서 새로운 변수에 조건부 바인딩이 가능
```swift
let number: Int? = 10

if let num = number {
    print(num)
}
```

### Optional Chaining
래핑된 인스턴스에 속성이나 메서드에 접근할 때, 체인 연산자(?)를 사용하여 접근 가능
```swift
struct User {
    var name: String
    var age: Int
}

var userA: User? = User(name: "erick", age: 20)

if let name = userA?.name {
    print("UserA name is \(name)")
}

// "UserA name is erick"

userA?.name = "zion"

if userA?.name.hasPrefix("zion" ) == true {
   print("UserA name is zion")
}

// "UserA name is zion"
```

## Use the nil-coalescing operator
?? 연산자를 사용하여 nil일 경우 기본값을 제공

## Unconditional Unwrapping
! 연산자를 사용하여 강제 언래핑이 가능함

## components(separatedBy:)
String의 인스턴스 메서드로 주어진 구분 기호로 나눈 String을 포함하는 배열을 반환
```swift
func components(separatedBy separator: String) -> [String]
```
---
## 느낀점
- 평소에 인지하지 않고 사용하던 옵셔널 체이닝에 대해 이해하게 됨
- components를 사용하면 split과 달리 [String]으로 값을 반환하는 이유를 알게 됨

## 성장방법
- 비슷한 동작을 하는 메서드라도 반환 값이 다르거나 두개의 차이를 모른다면 찾아보자

