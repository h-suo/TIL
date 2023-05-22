4월 25일 화요일

---
## Git
### Git의 구조
1. Working Directory
- 실제 작업공간
- git add 명령어를 통해 변경사항을 Stage Area로 업로드

2. Stage Area
- Git이 변경이력을 관리하는 구역
- 이곳에 올라온 파일만 저장소에 추가 및 수정 가능
- git commit 명령어를 통해 파일을 Local Repository로 업로드
> Stage Area가 필요한 이유 : 특정 파일만 업로드하고 싶을 때 그리고 특정 파일에는 로그를 남기고 싶지 않을 때, git add <파일명> 명령어로 파일을 선택하여 Stage Area로 옮길 수 있다.

3. Local Repository
- 작업자의 컴퓨터에 존재하는 저장소
- git push 명령어를 통해 Local repository의 내용을 Remote repository로 업로드

4. Remote Repository
- 외부 서버에 위치한 저장소
- 다른 작업자들이 관리하는 로컬 저장소의 접점

### fetch와 pull의 차이
- fetch는 Remote repository의 파일을 Local repository로만 다운로드
- pull은 Local repository에서 Working Directory로 가져오는 merge도 수행
- 즉 pull = fetch + merge

## enumerated()
- (n, x)를 반환함
- n은 0부터 시작하는 연속적인 정수, x는 요소
```swift
for ( index, number ) in numbers.enumerated() {
    print("\(index + 1) 번: \(number)")
}

// prints "1 번: 5"
// prints "2 번: 10"
// prints "3 번: 15"
// prints "4 번: 20"
```
위 코드와 같이 인덱스와 요소를 같이 가져올 수 있다.

---
## 느낀점
- git의 구조를 공부하니 명령어를 사용하는 이유와 목적을 이해할 수 있었음
- enumerated()와 같은 인스턴스 메서드를 사용하면 코드를 간편화할 수 있다는 것을 느낌

## 성장방법
- 인스턴스 메서드 등을 이용해 코드를 간소화하는 연습을 해야함
- 단순히 기능만 하는 코드가 아닌 더 가독성 높고 효율적인 코드를 짤 수 있도록 노력하고, 효율적인 코드란 무엇인지 고민해야함
