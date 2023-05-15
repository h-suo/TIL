5월 15일 월요일

## KVO
- 객체의 프로퍼티가 변경되면 다른 객체가 알 수 있도록 하는 패턴
- Model과 View 처럼 분리되어 있는 객체에서 사용할 수 있음

### 예시
- 내가 관찰할 대상에 NSObject를 상속
- 관찬할 프로퍼티에 `@objc`와 `dynamic` 키워드를 사용해야함

```swift
class Youtuber: NSObject {
    @objc dynamic var lastVideo: String = ""
    
    func updateVideo(_ video: String) {
        self.lastVideo = video
    }
}
```

- 관찰자에서는 관찰할 객체를 선언하고 `observe(_:options:changeHandler:)`를 통해 프로퍼티를 관찰할 수 있음

```swift
class Subcriber: NSObject {
    @objc var youtuber: Youtuber
    var newVideoAlarm: NSKeyValueObservation?
    
    init(youtuber: Youtuber) {
        self.youtuber = youtuber
        super.init()
        
        newVideoAlarm = observe(\.youtuber.lastVideo, options: [.old, .new]) { video, change in
            print("새로운 영상이 올라왔습니다. 영상 제목: \(change.newValue!)")
        }
    }
}
```

---
## 느낀점
- 
