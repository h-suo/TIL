5월 2일 화요일

---
## enum의 원시값
### Int를 원시값으로 가졌을 때
<img width="442" alt="스크린샷 2023-05-02 오전 10 16 05" src="https://user-images.githubusercontent.com/109963294/235559430-93f573b0-3e11-4f71-ac6d-1e5047fb8084.png">

- 자동으로 0, 1, 2가 할당됨

### String을 원시값으로 가졌을 때
<img width="442" alt="스크린샷 2023-05-02 오전 10 22 55" src="https://user-images.githubusercontent.com/109963294/235559572-5eed0f45-8b84-4d91-b570-3750653469c2.png">

- 자동으로 case 명이 할당됨
- 번호에 따라 케이스를 나눠야 할 때 사용하면 좋을 것 같음

## switch와 튜플
```swift
switch (computerRockPaperScissors, playerRockPaperScissors) {
    case (.paper, .scissors), (.scissors, .rock), (.rock, .paper):
        print("이겼습니다!")
    case (.scissors, .paper), (.rock, .scissors), (.paper, .rock):
        print("졌습니다!")
    default:
        print("비겼습니다!")
    }
```
- switch 문에 튜플 사용하여 두개의 값을 동시에 비교 가능

---
## 느낀점
- 여러 기능을 활용하여 코딩을 할 수록 명확한 코드가 되는 것인지 아니면 코드가 더러워지는 것인지 헬갈림

## 성장방법
- 다른 사람이 보기에도 쉽고 이해하기 쉬운 코드를 짜려고 노력하자
- namespace란 무엇인지 공부가 필요
