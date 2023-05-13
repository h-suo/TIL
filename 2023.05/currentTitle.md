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

</br>

## Delegate 패턴
- 하나의 객체가 모든 일을 처리하지 않고 처리하는 일을 다른 객체에게 위임하여 처리하는 것

### 예시
- 뷰컨트롤러에 테이블뷰를 연결하고, 테이블뷰의 델리게이트와 데이터소스를 `=self`로 설정하여 뷰컨트롤러로 기능을 위임함
- `extension`의 코드와 같이 tableView의 메서드를 사용할 수 있음

```swift
//ViewController.swift
class ViewController: UIViewController {
    @IBOutlet weak var tableView: UITableView!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        tableView.delegate = self
        tableView.dataSource = self
    }
}

extension ViewController: UITableViewDelegate, UITableViewDataSource {
    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return 1
    }
    
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = tableView.dequeueReusableCell(withIdentifier: "cell", for: indexPath)
        return cell
    }
}
```

### Delegate 패턴으로 데이터 전달
- 메서드만 사용하는 것이 아닌 뷰컨트롤러 간의 데이터 전달도 가능
- `SecondVC`에서 `dataSend`라는 String 데이터를 보내는 메서드를 가진 `SendProtocol` 프로토콜을 생성 
- `SendProtocol`을 채택한 변수를 생성하고 버튼을 눌렀을 때 TextField에 입력한 데이터를 전송할 수 있도록 설정

```swift
//SecondViewController.swift
protocol SendProtocol {
  func dataSend(data: String)
}

class SecondVC: UIViewController {

  @IBOutlet weak var dataTextField: UITextField!
  
  var delegate : SendProtocol?
  
  override func viewDidLoad() {
        super.viewDidLoad()
    }
    
  @IBAction func sendButtonTapped(_ sender: Any) {
    if let text = dataTextField.text {
      delegate?.dataSend(data: text)
    }
    
    self.navigationController?.popViewController(animated: true)
  }
}
```

- `FirstVC`에서 `SendProtocol`을 채택
- `nextVC.delegate = self`로 `FirstVC`를 위임자로 선언하고 `dataSend()`를 확장하여 데이터를 가져올 수 있

```swift
//FirstViewController.swift
class FirstVC: UIViewController, SendProtocol {
  
  @IBOutlet weak var dataLabel: UILabel!
  
  override func viewDidLoad() {
    super.viewDidLoad()
  }

  func dataSend(data: String) {
    dataLabel.text = data
  }
  
  @IBAction func nextButtonTapped(_ sender: Any) {
    guard let nextVC = self.storyboard?.instantiateViewController(withIdentifier: "SecondVC") as? SecondVC else { return }
    
    nextVC.delegate = self
    
    self.navigationController?.pushViewController(nextVC, animated: true)
  }
}
```

---
## 느낀점
- 비슷한 동작을 하는 함수가 있다면 하나로 처리할 수 있는 방법에 대해 생각해보자
- 뷰컨트롤러 간에 데이터 전달을 할 수 있는 여러 방법 중 상황에 맞는 것을 사용해보자
