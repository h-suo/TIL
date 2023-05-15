5월 15일 월요일

## KVO
- 객체의 프로퍼티가 변경되면 다른 객체가 알 수 있도록 하는 패턴
- Model과 View 처럼 분리되어 있는 객체에서 사용할 수 있음

### 예시
- 내가 관찰할 대상에 NSObject를 상속
- 관찬할 프로퍼티에 `@objc`와 `dynamic` 키워드를 사용해야함

```swift
class MyObjectToObserve: NSObject {
    @objc dynamic var myDate = NSDate(timeIntervalSince1970: 0)
    
    func updateDate() {
        myDate = myDate.addingTimeInterval(Double(2 << 30))
    }
}
```

- 관찰자에서는 관찰할 객체를 선언하고 `observe(_:options:changeHandler:)`를 통해 프로퍼티를 관찰할 수 있음

```swift
class MyObserver: NSObject {
    @objc var objectToObserve: MyObjectToObserve
    var observation: NSKeyValueObservation?
    
    init(object: MyObjectToObserve) {
        objectToObserve = object
        super.init()
        
        observation = observe(
            \.objectToObserve.myDate,
            options: [.old, .new]
        ) { object, change in
            print("myDate changed from: \(change.oldValue!), updated to: \(change.newValue!)")
        }
    }
}
```

---
## 느낀점
- 
