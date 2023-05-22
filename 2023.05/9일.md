5월 9일 화요일

## Type Casting
- 타입케스팅으 인스턴스의 타입을 확인하거나 같은 계층에 있는 다른 superclass나 subclass로 취급하느 방법

### Check Type
- is르 사용하여 타입을 확인할 수 있음
```swift
let array: [Any] = [1, "스위프트", 13, "iOS"]

for item in array {
    
    if item is Int {
        print("\(item)는 Int타입입니다.")
    } else if item is String {
        print("\(item)는 String타입입니다.")
    }
}

// "1는 Int타입입니다."
// "스위프트는 String타입입니다."
// "13는 Int타입입니다."
// "iOS는 String타입입니다."
```

### Downcasting
- as?와 as!를 이용하여 다운캐스팅을 할수있음
- as?느 특정 타입인지 확신할 수 없을 때
- as!는 특정 타입이 확실할 때

### Any, AnyObject
- Any : 함수 타입을 포함해 모든 타입을
- AnyObject : 모든 클래스 타입의 인스턴스

```swift
for item in array {
    switch item {
    case let intType as Int:
        print("\(intType)은 Int 타입")
    case let stringType as String:
        print("\(stringType)은 String 타입")
    default:
        break
    }
}

// "1은 Int 타입"
// "스위프트은 String 타입"
// "13은 Int 타입"
// "iOS은 String 타입"
```

</br>

## init(uniqueKeysWithValues:)
- 주어진 (키, 값)을 이용해 새로운 딕셔너리르 만드는 이니셜라이져
```swift
let nameArray = ["minsu", "sungmin", "han"]
let nameAgeDic: [String: Int] = Dictionary(uniqueKeysWithValues: nameArray.map { ($0, 30) })

print(nameAgeDic)

// "["han": 30, "minsu": 30, "sungmin": 30]"
```

</br>

## CaseIterable
- 프로토콜로 열거형에서 채택하면 모든 값을 컬렉션으로 제공함
```swift
enum Fruit: CaseIterable {
    case strawberry
    case banana
    case pineapple
    case kiwi
    case mango
}

let fruitList = Fruit.allCases
print(fruitList is [Fruit])

// "true"
```

---
## 느낀점
- uniqueKeysWithValues를 사용하여 반복적인 값을 가지는 딕셔너리를 쉽게 만들 수 있음
- CaseIterable을 사용하여 열거형의 case들을 배열로 사용할 수 있음
