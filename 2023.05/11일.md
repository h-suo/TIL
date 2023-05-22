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
- 기본값을 프로퍼티의 선언시에 줄 수도 있음
```swift
struct User {
    let userNumber: Int = 101
}
```

</br>

## NotificationCenter
- 등록된 관찰자에게 정보를 방송할 수 있음
- NotificationCenter.default는 기본알림센터

### addObserver
- NotificationCenter에 관찰자를 추가하여 selector에 있는 함수를 알림과 함께 호출

### post
- 주어진 name과 sender로 알림을 만들고 NotificationCenter에 게시함

### 예제
- YouTuber의 addVideo()를 실행할 때 "newVideo"라는 이름의 알람을 게시하면, Subscriber 클래스 생성자에서 추가된 관찰자가 printMessage를 실행하는 간단한 예제

```swift
class YouTuber {
    
    func addVideo() {
        NotificationCenter.default.post(name: Notification.Name("newVideo"), object: nil)
    }
}

class Subscriber {
    
    init() {
        NotificationCenter.default.addObserver(self, selector: #selector(printMessage), name: Notification.Name("newVideo"), object: nil)
    }
    
    @objc func printMessage() {
        print("새로운 영상이 올라왔습니다.")
    }
}

let sub = Subscriber()
let you = YouTuber()

you.addVideo()

// "새로운 영상이 올라왔습니다."
```

</br>

---
## 느낀점
- 프로퍼티의 기본값을 주는 것을 속성이 잘 변하지 않고 인스턴스마다 차이가 없는 속성일 경우, 이니셜라이져를 활용할 때는 인스턴스마다 다른 값을 주어야할때라고 생각된다.
- 노티피케이션을 이용해 특정 액션에 반응하는 함수를 만들 수 있다. (뷰가 달라도 가능)
