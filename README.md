# HGJSearchBar
* 在分类中扩展系统搜索框，自动显示隐藏取消按钮
* 添加了输入栏的背景颜色属性
* 创建后默认宽度为屏幕宽高度44，可以继续按照普通搜索栏自定义

## CocoaPods
``` pod 'HGJSearchBar' ```

##Requirements
* Swift
* Xcode 5 or higher
* iOS 6.0 or higher
* ARC

## ScreenShot
![](https://nj01ct01.baidupcs.com/file/627e6ccfb08bb023f96c3362952b13c7?bkt=p3-1400627e6ccfb08bb023f96c3362952b13c79f2da719000000007ea3&fid=1649281771-250528-16510458369690&time=1489824413&sign=FDTAXGERLBHS-DCb740ccc5511e5e8fedcff06b081203-6nXQQ9vB6oADw%2FER3%2ByvlMuImUE%3D&to=63&size=32419&sta_dx=32419&sta_cs=1&sta_ft=gif&sta_ct=4&sta_mt=4&fm2=MH,Yangquan,Netizen-anywhere,,guangdongct&newver=1&newfm=1&secfm=1&flow_ver=3&pkey=1400627e6ccfb08bb023f96c3362952b13c79f2da719000000007ea3&sl=72286287&expires=8h&rt=sh&r=799797593&mlogid=1778227530142062037&vuk=282335&vbdid=107365255&fin=HGJSearchBar1.gif&fn=HGJSearchBar1.gif&rtype=1&iv=0&dp-logid=1778227530142062037&dp-callid=0.1.1&hps=1&csl=400&csign=M4kekPQy5kwNJRJCL0hZXCCSi9s%3D&by=themis)
## delegate and block
```swift
public protocol HGJSearchDelegate : NSObjectProtocol {
    
    func HGJSearchBar(_ searchBar: UISearchBar, textDidChange searchText: String)
    
}

typealias HGJSearchBlock = (_ searchBar: UISearchBar, _ searchText: String) -> Void

```

## Usage Demo

1.方法一
```swift
    let searchBar = UISearchBar.init(HGJSearchBlock: { (searchBar, text) in

        print("\(text)")

    })

    searchBar.textfieldColor = UIColor.red  // 默认为UIColor.gray

    self.tableView.tableHeaderView = searchBar
```

2. 方法二
+ FirstStep （创建对象）
```swift
        let searchBar = UISearchBar(HGJDelegate: self)
        searchBar.textfieldColor = UIColor.red  // 默认为UIColor.gray
        self.tableView.tableHeaderView = searchBar
```
+ Second （代理对象遵守协议,并实现协议）
```swift
    func HGJSearchBar(_ searchBar: UISearchBar, textDidChange searchText: String) {
        print("\"" + searchText + "\"")
    }
```

## Contact
>如果你发现bug或有更好的改进，please pull reqeust me
