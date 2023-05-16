5월 16일 화요일

## API design guidelines
- 명확한 표현을 사용하자, 간결함 보단 명확하고 모호하지 않게 표현

### naming 정리
- 네이밍을 할 때는 이름만으로 명확한 사용법을 제시

```swift
// 명확함
Array.remove(at: Int)
// 어디가 삭제되는 것인지 모호함
Array.remove(Int)
```

</br>

- 쓸모없는 단어 제거
- 중복된 정보를 제공하는 경우에는 제거하는게 좋음

```swift
func removeFruit(_ fruit: Fruit) -> Fruit?

// 수정
func remove(_ fruit: Fruit) -> Fruit?
```

</br>

- 변수, 매개변수, 연관 타입은 역할에 맞게 하는게 좋음

```swift
var fruitStockDictionary: [Fruit: Int] = [.kiwi: 10, .mango: 10]

// 수정
var fruitStock: [Fruit: Int] = [.kiwi: 10, .mango: 10]
```

</br>

- 메서드나 함수를 사용할 때 문장 처럼 느껴지도록 전치사를 잘 활용하는 것이 좋음

```swift
Array.insert(x, at: n)
compare(a, and: b)
add(a, to: b)
```

</br>

- 어려운 용어보단 접근하기 쉬운 용어를 사용
- 축약어를 지양

</br>

- 함수에서 매개 변수가 감춰져 있더라고 명확하게 역활을 알려줘야 한다.

 ```swift
 func move(from start: Point, to end: Point)
 ```
 
 </br>
 
 - 전달인자 레이블을 잘 활용하는 것도 좋지만 도움이 안된다면 생략

```swift
min(number1, number2)
zip(sequence1, sequence2)
```

---
## 느낀점
- 네이밍은 어렵다.. 명확한 표현을 사용하자
