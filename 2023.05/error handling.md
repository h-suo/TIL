5월 8일 월요일

---
## Error Handling
- 프로그램을 실행 중 발생하는 에러를 처리하는 것

</br>

### Error
- 열거형으로 에러를 그룹화하고 추가적인 정보를 제공 가능
```swift
enum InputError: Error {
    case invalidInputError
}
```

</br>

### throw
- throw를 사용하여 에러를 던질 수 있음
```swift
throw Input. invalidInputError
```

</br>

###  throwing function
- 함수의 선언부 파라미터 뒤에 throws를 사용하여 에러를 던지는 throwing function를 만들 수 있음
- 오직 throwing function만 에러를 던질 수 있음, throwing function를 실행한다면 반드시 에러를 처리하거나 throws를 붙여야함

```swift
func userInput() throws -> String {
    guard let userInput = readLine() else { throw Input.invalidInputError }

    return userInput
}
```

</br>

### do-catch
- do 구문 안에서 발생하는 에러를 catch로 잡을 수 있음
- catch 뒤에 에러의 종류를 명시해주지 않는다면 발생하는 모든 에러를 지역상수 error로 바인딩
```swift
do { 
    try userInput()
} catch Input.invalidInputError {
    print("잘못된 입력입니다.")
} catch {
    print("알수없는 오류.")
}
```

</br>

### try?
- try? 사용하여 에러가 발생하면 nil을 리턴할 수 있음
```swift
let x = try? userInput()
```

</br>

---
## Architecture 그리고 Design Pattern
- 둘 다 설계한다는 의미로 건축에서 비롯된 용어
- 문제 해결을 위해 사용되는 정형화된 양식을 디자인패턴이라고 할 수 있음
- 아키텍쳐란 도면을 그리는 것과 같이 앱을 설계하는 것

---
## 느낀점
- 에러를 종류별로 나누고 분류하여 던져줄 수 있고, 나는 그것을 적시적소에서 받을 줄 알아야 한다.

## 성장방법
- 발생가는한 에러를 enum 타입으로 분류하고 어디서 do-catch문을 써야하는지 생각하고 코드로 짜보자.
