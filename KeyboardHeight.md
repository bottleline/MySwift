``` swift
NotificationCenter.default.addObserver(
            self,
            selector: #selector(keyboardWillShow),
            name: UIResponder.keyboardWillShowNotification,
            object: nil)
NotificationCenter.default.addObserver(
            self,
            selector: #selector(keyboardWillHide),
            name: UIResponder.keyboardWillHideNotification,
            object: nil)
            
            
            
.
.
.
.
.
.
@objc private func keyboardWillShow(_ notification: Notification) {
        guard let userInfo = notification.userInfo,
            let keyboardFrame = userInfo[UIResponder.keyboardFrameEndUserInfoKey] as? CGRect else {
                return
        }
        
        let contentInset = UIEdgeInsets(
            top: 0.0,
            left: 0.0,
            bottom: keyboardFrame.size.height,
            right: 0.0)
        collectionView.contentInset = contentInset
        collectionView.scrollIndicatorInsets = contentInset // 스크롤뷰 콜렉션뷰 등 스크롤 되는 뷰를 클릭했을때 
    }
```
