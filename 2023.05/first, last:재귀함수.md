5월 5일 금요일

---
## first, last
- 인스턴스 프로퍼티
- first는 컬렉션의 첫 번째 요소를, last는 컬렉션의 마지막 요소를 말한다.
```swift
let numbers: [Int] = [1, 2, 3, 4, 5]
print(numbers.first!)
print(numbers.last!)

// "1"
// "5"
```
- !를 붙이는 이유는  옵셔널을 강제 언래핑해주기 위해 사용

## 재귀함수
- 재귀함수란 함수 내부에서 자기 스스로를 호출하는 함수이다.
```swift
func printMenu() {
    let userInput = getUserInput()
    
    switch userInput {
    case "1번":
        // ...
    case "2번":
        // ...
    default:
        print("잘못된 입력")
        printMenu()
    }
}
```
### 재귀함수의 장점
- 조금 더 쉽고 명확하게 코드를 짤 수 있다.

### 재귀함수의 문제
- 계속해서 스스로가 호출되어 반복될 경우 스택오버플로우가 발생할 수 있다.

---
## 느낀점
- first, last와 같이 속성에 쉽게 접근할 수 있는 방법들도 있다.
- 재귀함수는 명확하지만 오류를 일으킬 수 있다.

## 성장방법
- 문제점을 잘 알고 사용하자
- 반복이 많이 되지 않는 프로그램에서는 재귀함수의 사용이 더 명확할 수도 있다.
