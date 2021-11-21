1. AppDelegate 코드
``` swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // Override point for customization after application launch.
        GADMobileAds.sharedInstance().start(completionHandler: nil)
        UNUserNotificationCenter.current().requestAuthorization(options: [UNAuthorizationOptions.badge,.alert,.sound]) { granted, error in
            if granted{
                UNUserNotificationCenter.current().delegate = self
            }
        }
        return true
    }
```
  
2. 스케쥴 코드
``` swift
func schedule(){
        UIApplication.shared.applicationIconBadgeNumber = 0
        let alamCheck = UserDefaults.standard.bool(forKey: "Alam")
        if alamCheck {
            
        }else{
      //  let center = UNUserNotificationCenter.current()
      //  center.removePendingNotificationRequests(withIdentifiers: ["challenge"])
      //  center.removeDeliveredNotifications(withIdentifiers:  ["challenge"]) //노티피케이션 취소
        
            UserDefaults.standard.set(true, forKey: "Alam")
            let content = UNMutableNotificationContent()
            content.title = "Endure Timer".localized
            content.body = "Is your challenge going well?".localized
            content.badge = 1
            content.sound = UNNotificationSound.default
            
            let trigger = UNTimeIntervalNotificationTrigger(timeInterval: 604800, repeats: true)
            
            let request = UNNotificationRequest(identifier: "challenge", content: content, trigger: trigger)
            
            UNUserNotificationCenter.current().add(request){(error) in
                
                UserDefaults.standard.set(false, forKey: "Alam")
                if let error = error {
                    print(error)
                }
            }
        }
        
    }
```
