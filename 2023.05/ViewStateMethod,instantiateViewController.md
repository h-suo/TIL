5월 18일 목요일

## View State Method
- 뷰의 가시성이 바뀐다면 그에 따른 메서드를 호출함

### loadView()
- 컨트롤러가 관리하는 뷰를 만들때 호출
- 직접 호출하는 것은 좋지 않음

### viewDidLoad()
- 컨트롤러의 뷰가 메모리에 로드된 후 호출
- view 객체를 초기화할 때 주로 사용

### viewWillAppear(_:)
- 뷰가 뷰 계층 구조에 추가될 것이라고 알림

### viewDidAppear(_:)
- 뷰가 뷰 계층 구조에 추가됬다는 것을 알림

### viewWillDisappear(_:)
- 뷰가 뷰 계층 구조에 제거될 것이라고 알림

### viewDidDisappear(_:)
- 뷰가 뷰 계층 구조에 제거됬다는 것을 알림

</br>

## instantiateViewController(withIdentifier:)
- 지정된 식별자로 뷰컨트롤러로 만들고 스토리보드로 초기화함
- 즉 스토리보드를 사용하여 뷰를 만들었다면 `instantiateViewController`로 접근해야함

```swift
// 뷰를 코드로 만들었을때
let pushViewController = ChangeStockViewController()
// 뷰를 스토리보드로 만들었을때
let pushViewController = storyboard?.instantiateViewController(withIdentifier: "ChangeStockViewControllerID")
```

---
## 느낀점
- 뷰 상태 메서드는 재정의를 통해 대부분 뷰와 관련된 동작을 함, 언제 어떤 함수를 사용할지는 개발자의 몫
