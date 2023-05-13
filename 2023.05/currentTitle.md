5월 12일 금요일

## currentTitle
- 버튼에 표시된 제목
- 버튼에 제목이 표시되어 있고 버튼의 기능들이 비슷하다면 switch문으로 나눠 하나의 @IBAction으로 처리할 수 있음

```swift
@IBAction func orderJuiceTapped(_ sender: UIButton) {
        guard let title = sender.currentTitle else { fatalError("버튼 제목이 없음") }
        
        switch title {
        case "딸기쥬스 주문":
            orderJuice(.strawberryJuice)
        case "바나나쥬스 주문":
            orderJuice(.bananaJuice)
        case "파인애플쥬스 주문":
            orderJuice(.pineappleJuice)
        case "키위쥬스 주문":
            orderJuice(.kiwiJuice)
        case "망고쥬스 주문":
            orderJuice(.mangoJuice)
        case "딸바쥬스 주문":
            orderJuice(.strawberryBananaJuice)
        case "망키쥬스 주문":
            orderJuice(.mangoKiwiJuice)
        default:
            break
        }
    }
```

---
## 느낀점
- 비슷한 동작을 하는 함수가 있다면 하나로 처리할 수 있는 방법에 대해 생각해보자
