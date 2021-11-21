
1. TextField Delegate 사용 
``` swift
    func textField(_ textField: UITextField, shouldChangeCharactersIn range: NSRange, replacementString string: String) -> Bool {
        guard let text = textField.text else {return false}
        
        // 최대 글자수 이상을 입력한 이후에는 중간에 다른 글자를 추가할 수 없게끔 작동
        if text.count >= maxLength && range.length == 0 && range.location < maxLength {
            return false
        }
        
        return true
    }
```
  
2. Notification 사용

``` swift
NotificationCenter.default.addObserver(self,
                                               selector: #selector(textDidChange(_:)),
                                               name: UITextField.textDidChangeNotification,
                                               object: textField)
```
  
``` swift
@objc private func textDidChange(_ notification: Notification) {
        if let textField = notification.object as? UITextField {
            if let text = textField.text {
                
                if text.count > maxLength {
                    // 8글자 넘어가면 자동으로 키보드 내려감
                    textField.resignFirstResponder()
                }
                
                // 초과되는 텍스트 제거
                if text.count >= maxLength {
                    let index = text.index(text.startIndex, offsetBy: maxLength)
                    let newString = text[text.startIndex..<index]
                    textField.text = String(newString)
                }
                
                else if text.count < 2 {
                    warningLabel.text = "2글자 이상 8글자 이하로 입력해주세요"
                    warningLabel.textColor = .red
                    
                }
                else {
                    warningLabel.text = "사용 가능한 닉네임입니다."
                    warningLabel.textColor = .green

                }
            }
        }
    }
    
    func onlyAlphabet() ->String{
        let okayChars : Set<Character> = Set("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLKMNOPQRSTUVWXYZ1234567890")
      return String(text.filter {okayChars.contains($0) })
    }

```
