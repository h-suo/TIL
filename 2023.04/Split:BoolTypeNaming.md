4월 28일 금요일

---
## split
주어진 요소의 주변 요소를 가장 긴 하위 시퀀스로 반환함
```swift
func split(
    separator: Self.Element,
    maxSplits: Int = Int.max,
    omittingEmptySubsequences: Bool = true
) -> [Self.SubSequence]
```
components와 단순히 리턴값만 다른 것이 아닌 값을 잘라내는 기준이 다름
```swift
let numbers = "1 2   3"

let componentsNumbers = numbers.components(separatedBy: " ")
let splitNumbers = numbers.split(separator: " ")

print(componentsNumbers)
print(splitNumbers)

// "["1", "2", "", "", "3"]"
// "["1", "2", "3"]"
```
위 코드와 같이 components는 구분기호를 기준으로 값을 나눠 리턴하고, split은 주어진 요소 앞뒤로 자름

## Bool 타입 네이밍
Bool 타입을 네이밍 할 때는 접두사로 ```is```를 붙여야 함
```swift
var isVictory: Bool = true
```
참고: https://velog.io/@hayeon/Swift-네이밍-및-개발-규칙

---
## 느낀점
- 메서드의 동작 방식이 비슷해보여도 결과의 차이가 클 수 있음
- 네이밍이 가장 기본적이지만 어렵고, 정해진 규칙이 있음

## 성장방법
- 메서드에 따라 여러 케이스를 테스트 해보자
- 네이밍을 할 때 규칙에 맞게 쓰자
- 관련 문서 좀 읽자
