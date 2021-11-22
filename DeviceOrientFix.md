``` swift
func application(_ application: UIApplication, supportedInterfaceOrientationsFor window: UIWindow?) -> UIInterfaceOrientationMask {
        if supportAllOrientation{
            return UIInterfaceOrientationMask.all
        }else{
            return .portrait
        }
    }
```
