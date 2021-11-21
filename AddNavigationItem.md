``` swift
let backBarButton = UIBarButtonItem(title: " ", style: .plain, target: self, action: nil)
backBarButton.tintColor = Constants.Colors.color1//UIColor(named: "basic")
navigationItem.backBarButtonItem = backBarButton // 다음 네비게이션의 뒤로가기버튼 세팅
        
navigationController?.hidesBarsOnSwipe = true
navigationItem.backBarButtonItem?.isEnabled = true
        
let rightBtn = UIBarButtonItem(title: "", style: .plain, target: self, action: #selector(myInfoView(_:)))
rightBtn.tintColor = Constants.Colors.color1//UIColor(named: "basic")
rightBtn.image = UIImage(systemName: "person.fill")
navigationItem.rightBarButtonItem = rightBtn //아이템추가

let leftButton: UIBarButtonItem = UIBarButtonItem(barButtonSystemItem: .add, target: self, action: #selector(buttonPressed(_:)))
navigationItem.leftBarButtonItem = leftButton

.
.
.
.
.
.
@objc func myInfoView(_ sender:Any){
    performSegue(withIdentifier: "sideMenuSegue", sender: nil)
}
```
