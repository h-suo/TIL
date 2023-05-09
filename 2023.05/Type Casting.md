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

---
## 느낀점
- 내용
