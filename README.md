# Threads-Clone

This repository contains handy code snippets and examples featured on our YouTube channel, <a href="https://www.youtube.com/@ioscribbler/videos" target="_blank"><b>ioscribbler</b></a>.

## Introduction
This repo includes mock data, assets nad other components featured in our SwiftUI Threads clone tutorial series on YouTube. Everything here is designed to be easily copy-pasted, so you can follow along or extend the project in your own way.

## <a name="snippets">📦 Snippets(Code to Copy)</a>

<details>
<summary><code>What is new custom icons</code></summary>
<br>
 
```swift
 struct MockHelper {
    static let whatIsNewActionIcons: [Image] = [
        Image(systemName: "photo.on.rectangle.angled"),
        Image(systemName: "camera"),
        Image(systemName: "document"),
        Image(systemName: "microphone"),
        Image(systemName: "number"),
        Image(systemName: "line.3.horizontal.decrease"),
        Image(systemName: "mappin.circle"),
    ]
}
```
</details>

<details>
<summary><code>Page selection enum</code></summary>
<br>
  
```swift
enum PageSelection: CaseIterable {
    case forYou
    case following
    
    static let pageSelectionID = "PageSelectionID" // used for matched geo effect
    
    var title: String {
        switch self {
        case .forYou:
            return "For You"
        case .following:
            return "Following"
        }
    }
}
```

</details>
