``` swift
func applyGradient(colors: [CGColor],_ radius:CGFloat) {
        self.backgroundColor = nil
        self.layoutIfNeeded()
        let gradientLayer = CAGradientLayer()
        gradientLayer.colors = colors
        gradientLayer.startPoint = CGPoint(x: 0, y: 0)
        gradientLayer.endPoint = CGPoint(x: 0, y: 1)
        gradientLayer.frame = self.bounds
        gradientLayer.cornerRadius = radius

        self.layer.insertSublayer(gradientLayer, at: 0)
 
    }
   
```
