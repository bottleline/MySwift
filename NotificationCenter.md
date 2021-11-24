``` swift
//수신측

NotificationCenter.default.addObserver(self, selector: #selector(receiveM(notification:)), name: NSNotification.Name.reloadTable, object: nil)
.
.
.
.
deinit{
        NotificationCenter.default.removeObserver(self, name: NSNotification.Name.reloadTable, object: nil)
    }
    .
    .
    .
    .
 @objc func receiveM(notification:Notification){
        guard let newCd = notification.userInfo?["data"] as? ChatData else {return}
        chatData.append(newCd)
        tableView.reloadData()
    }
```

``` swift
//발신측
NotificationCenter.default.post(name: NSNotification.Name.reloadTable, object: nil, userInfo: ["data" : cd])
.
.
.
.
extension NSNotification.Name{
    static let reloadTable = NSNotification.Name("ReloadTable")
}
```
