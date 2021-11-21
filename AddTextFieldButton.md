``` swift
private func setTextFieldButton(){
        let textFieldButton = UIButton(type: .custom)
        textFieldButton.frame = CGRect(x: 0, y: 0, width: 20, height: 20)
        textFieldButton.setImage(UIImage(named: ""), for: .normal)
       // textFieldButton.addTarget(self, action: nil, for: .touchUpInside)
        dateTextField.rightView = textFieldButton
        dateTextField.rightViewMode = .always
    }
```
