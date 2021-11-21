``` swift
let tapGesture = UITapGestureRecognizer(target: self, action: #selector(self.dismissKeyboard (_:)))
        tapGesture.cancelsTouchesInView = false
        self.view.addGestureRecognizer(tapGesture)
        
        .
        .
        ..
        .
@objc func dismissKeyboard (_ sender: UITapGestureRecognizer) {
  textView.resignFirstResponder()
}
```
