``` swift
private func setDatePicker(){
        datePicker.minimumDate = Calendar.current.date(byAdding: .year, value: -10, to: Date())
        datePicker.maximumDate = Calendar.current.date(byAdding: .year, value: 0, to: Date())
        datePicker.addTarget(self, action: #selector(datePickerChanged), for: .valueChanged)
    }
```
