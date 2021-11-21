``` swift
let navBar = UINavigationBar(frame: CGRect(x: 0, y: 0, width: view.frame.size.width, height: 44))
view.addSubview(navBar)

let navItem = UINavigationItem(title: "SomeTitle")
let doneItem = UIBarButtonItem(barButtonSystemItem: .done, target: nil, action: #selector(selectorName:))
navItem.rightBarButtonItem = doneItem

navBar.setItems([navItem], animated: false)
```
