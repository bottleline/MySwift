1. 슬라이더뷰가 있는 뷰 컨트롤러 클래스 생성
``` swift
class ControlViewController : UIViewController{
    //슬라이더 객체 정의
    let slider = UISlider()
    
    var sliderValue : Float{
        return self.slider.value
    }
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        //슬라이더의 최소값 / 최대값 설정
        self.slider.minimumValue = 0
        self.slider.maximumValue = 100
        
        //슬라이더의 영역과 크기를 정의하고 루트 뷰에 추가한다.
        self.slider.frame = CGRect(x: 0, y: 0, width: 170, height: 30)
        self.view.addSubview(self.slider)
        
        //뷰 컨트롤러의 콘텐츠 사이즈를 지정한다.
        self.preferredContentSize = CGSize(width: self.slider.frame.width, height: self.slider.frame.height + 10)   
    }
}
```

2. 경고창 생성
``` swift
@objc func sliderAlert(_ sender : Any){
  //콘텐츠 뷰 영역에 들어갈 뷰 컨트롤러를 생성
  let contentVC = ControlViewController()
        
  //경고창 객체를 생성
  let alert = UIAlertController(title: nil, message: "글의 평점을 입력해주세요", preferredStyle: .alert)
        
  alert.setValue(contentVC, forKey: "contentViewController")
        
  let okAction = UIAlertAction(title: "OK", style: .default, handler: nil)
  alert.addAction(okAction)
        
  self.present(alert, animated: false)
}
```
