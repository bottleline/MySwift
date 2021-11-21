``` swift
func showSelectAlert(){
        let controller = UIAlertController(title: "Select Channel".localized, message: "", preferredStyle: .alert)

        let okAction = UIAlertAction(title: "OK".localized, style: .default) {[weak self] (action) in
            
        }
        
        let cancelAction = UIAlertAction(title: "Cancel".localized, style: .cancel) {[weak self] (action) in
            
        }
        
        controller.addAction(okAction)
        controller.addAction(cancelAction)
        self.present(controller, animated: true, completion: nil)
    }
```
