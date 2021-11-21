``` swift
/// shadow가 있으려면 layer.borderWidth 값이 필요
        emptyView.layer.borderWidth = 1
        /// 테두리 밖으로 contents가 있을 때, 마스킹(true)하여 표출안되게 할것인지 마스킹을 off(false)하여 보일것인지 설정
        emptyView.layer.masksToBounds = false
        /// shadow 색상
        emptyView.layer.shadowColor = UIColor.black.cgColor
        /// 현재 shadow는 view의 layer 테두리와 동일한 위치로 있는 상태이므로 offset을 통해 그림자를 이동시켜야 표출
        emptyView.layer.shadowOffset = CGSize(width: 0, height: 20)
        /// shadow의 투명도 (0 ~ 1)
        emptyView.layer.shadowOpacity = 0.8
        /// shadow의 corner radius
        emptyView.layer.shadowRadius = 5.0
        ```
