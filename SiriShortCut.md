### 1
``` 
1. Capabilites 에 Siri 추가
```

### 2
``` swift
// 2. Scene Delegate 에 추가
//Tells the delegate to handle the specified Handoff-related activity.

func scene(_ scene: UIScene, continue userActivity: NSUserActivity) {
        if let vc = window?.rootViewController as? ViewController{
            vc.shortcut() // 숏컷으로 실행할 메소드 추가
        }
        
    }
```

### 3
``` swift
func shortcut(){
        //Key moment 저장
        let activity = NSUserActivity(activityType: "kr.kevin.ioT.Excute") // NSUserActivity 를 생성하여 실행되는 순간을 포착함
        
        activity.title = "동작실행하기" // user activity 타이틀 지정
        
        //프로퍼티를 활성화하여 객체를 사용할수 있는 작업을 구성
        activity.isEligibleForSearch = true // activity 검색 가능 여부
        activity.isEligibleForPrediction = true // activity 예측 가능 여부
        activity.isEligibleForHandoff = true // activity handoff 기능 지원 여부
        activity.isEligibleForPublicIndexing = true
        
        activity.resignCurrent()
        
        self.userActivity = activity
        self.userActivity?.becomeCurrent() // useractivity 객체를 시스템에 등록한다.

        self.excute(2, 0) // 지정한 동작을 실행
    }
```
