``` swift
@objc func showSelectAlert(_ sender:Any){
        let controller = UIAlertController(title: "Enter the name of the challenge".localized, message: "", preferredStyle: .alert)

        controller.addTextField { uiTextField in
            uiTextField.placeholder = ""
        }
     
        let ok = UIAlertAction(title: "Ok".localized, style: .default) {[weak self] (action) in
            if let fieldList = controller.textFields{
                if let name = fieldList.first{
                    self.etcName = name.text ?? "etc".localized
                }
            }
        }
        let cancel = UIAlertAction(title: "Cancel".localized, style: .cancel,handler:nil)
        
        controller.addAction(ok)
        controller.addAction(cancel)
        self.present(controller, animated: true, completion: nil)
    }
```
