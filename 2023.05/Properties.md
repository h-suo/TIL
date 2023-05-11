5월 11일 목요일

## Properties
- 구조체, 클래스, 열거형과 연관된 값

### Stored Properties(저장 프로퍼티)
- 저장 프로퍼티는 단순히 값을 저장하는 프로퍼티
```swift
struct User {
    let name: String
    let age: Int
}

var user = User(name: "Erick", age: 10)
print("유저 이름: \(user.name), 나이: \(user.age)")

// "유저 이름: Erick, 나이: 10"
```

### 구조체 인스턴스
- 구조체의 인스턴스는 let으로 선언하면 프로퍼티를 변경할 수 없음
- class는 참조타입이니 때문에 let으로 선언하여도 프로퍼티 변경 가능
```swift
let user = User(name: "Erick", age: 10)
user.age = 20 // Error: Cannot assign to property: 'age' is a 'let' constant
```

</br>

## Initialization
- 클래스, 구조체, 열거형 인스턴스를 사용하기 위해 저장 프로퍼티의 초기 값을 설정

### 초기값 설정
- 저장 프포퍼티를 사용하기 전에 반드시 값을 초기화 해야 함
- 기본값 혹은 특정값 설정

### Initializers
- 특정 타입의 인스턴스를 생성
- init()이 가장 기본 형태임
```swift
struct Erick {
    let name: String
    let age: Int
    
    init() {
        name = "Erick"
        age = 10
    }
}

let user = Erick()
print("유저 이름: \(user.name), 나이: \(user.age)")

// "유저 이름: Erick, 나이: 10"
```

### Default Property Values
- 

---
## 느낀점
- 내용
