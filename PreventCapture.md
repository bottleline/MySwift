# 스위프트 캡처 방지
 
SceneDelegate
```
 func sceneWillEnterForeground(_ scene: UIScene) {
        // Called as the scene transitions from the background to the foreground.
        // Use this method to undo the changes made on entering the background.
        NotificationCenter.default.addObserver(self, selector: #selector(alertPreventScreenCapture(_:)), name: UIApplication.userDidTakeScreenshotNotification, object: nil)
        NotificationCenter.default.addObserver(self, selector: #selector(alertPreventScreenCapture(_:)), name: UIScreen.capturedDidChangeNotification, object: nil)
    }
  .
  .
  .
  
  @objc func alertPreventScreenCapture(_ notification:Notification)->Void{
        let controller = UIAlertController(title: "캡쳐를 하시면 안됍니다.", message: "캡쳐를 하면 안돼요.", preferredStyle: .alert)
        let okAction = UIAlertAction(title: "네", style: .default)
        controller.addAction(okAction)
        
        hideScreen()
        
        self.window?.rootViewController!.present(controller,animated:true,completion:nil)
    }
    
    fileprivate func hideScreen(){
        if UIScreen.main.isCaptured{
            window?.isHidden = true
        }else{
            window?.isHidden = false
        }
    }

```
