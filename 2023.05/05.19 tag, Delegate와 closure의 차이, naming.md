5월 19일 금요일

## tag
- 뷰 객체를 식별하는데 사용할 수 있는 정수형 프로퍼티

- 뷰 객체에 tag를 지정한 뒤 비슷한 동작을 한다면 하나의 함수에서 분기처리 할 수 있음
```swift
strawberryStockStepper.tag = 0
bananaStockStepper.tag = 1
// ...

switch sender.tag {
case 0:
    // ...
case 1: 
    // ...
// ...
default:
    break
}
```
</br>

## Delegate와 closure의 차이
- 둘 다 스택에 쌓인 뷰가 원래 뷰로 데이터 전달을 하는데 사용할 수 있음
- 전통적으로 delegate 패턴을 사용하는 것이 맞음
- `completionhandler`를 만들어 사용하는 closure는 Escaping 클로저에서 주로 사용함

</br>

## naming
### 파일명
- 파일명의 단어 첫글자는 대문자로

### 클래스, 구조체,익스텐션, 프로토콜, 열거형 이름
- 대문자의 명사로 시작
- Pascal casing을 사용

### 함수, 메서드, 인스턴스 이름
- 소문자의 동사로 시작
- 함수명
  - 값의 설정 : 접두사 set 붙인다.
  - 값 추가 : 배열 등에 값 넣을 시 접두사 push 붙인다.
  - 값 빼오기 : 배열 등에서 값 빼올 시 접두사 pop 붙인다.
  - 생성 : 접두사 create
  - 열기 : 접두사 open
  - 닫기 : 접두사 close
  - 어떤 행위를 한다 : 접두사 do
  - 입력받는다 : 접두사 input
  - 저장, 기록 : 접두사 save, write
  - 반환값이 있다, 함수가 무엇인가 나오거나 추출되어질 경우 : 접두사 bring, extract, read

### 변수, 상수 이름
- 소문자의 명사로 시작
- 변수
  - 지역변수 : 소문자의 명사로 시작
  - 전역변수 : g_ 로 시작하기
  - Bool 값 : 접두사 is
  - 리스트 : 접미사 List 붙여주기

---
## 느낀점
- 클로져보단 delegate 패턴을 자주 사용하고 익숙해지자
- currentTitle이 직관적일 수 있지만 버튼이 아닌 다른 객체라면 tag를 사용하는 것도 좋다
- 네이밍 많이 틀리고 많이 
