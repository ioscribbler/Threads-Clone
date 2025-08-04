# Threads-Clone

This repository contains handy code snippets and examples featured on our YouTube channel, <a href="https://www.youtube.com/@ioscribbler/videos" target="_blank"><b>ioscribbler</b></a>.

## Introduction
This repo includes mock data, assets nad other components featured in our SwiftUI Threads clone tutorial series on YouTube. Everything here is designed to be easily copy-pasted, so you can follow along or extend the project in your own way.

## <a name="snippets">📦 Snippets(Code to Copy)</a>

<details>
<summary><code>Theme Colors</code></summary>
<br>
 
```swift
Copy the ThemeColors from above directly into your assets Folder in XCode.
```
</details>


<details>
<summary><code>Date Extension</code></summary>
<br>
 
```swift
extension Date {
    func formattedRelative() -> String {
        let now = Date()
        let calendar = Calendar.current

        guard
            let minutes = calendar.dateComponents(
                [.minute],
                from: self,
                to: now
            ).minute,
            let hours = calendar.dateComponents(
                [.hour],
                from: self,
                to: now
            )
                .hour,
            let days = calendar.dateComponents(
                [.day],
                from: self,
                to: now
            ).day
        else {
            return ""
        }

        if minutes < 60 {
            return "\(minutes)m"
        } else if hours < 24 {
            return "\(hours)h"
        } else if days <= 10 {
            return "\(days)d"
        } else {
            let formatter = DateFormatter()
            formatter.dateFormat = "dd.MM.yyyy"
            return formatter.string(from: self)
        }
    }
}
```
</details>

<details>
<summary><code>Post data</code></summary>
<br>
 
```swift
import Foundation 

struct PostData: Identifiable {
    let id = UUID()
    var postCreatedDate: Date
    var profileImage: String
    var profileName: String
    var text: String
    var likeCount: Int
    var commentCount: Int
    var repostCount: Int
    var sharedCount: Int
    var photos: [String]
}
```
</details>


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

<details>
<summary><code>Profile Images</code></summary>

<br>

```swift
Copy the ProfileImages folder from above directly into your assets Folder in XCode.
```

</details>

<details>
<summary><code>Profiles Mock Data</code></summary>

<br>

```swift
import SwiftUI

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

    static let mockPosts: [PostData] = [
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 10),
            profileImage: "pr1",
            profileName: "Lena",
            text:
                "Nothing beats a walk in the fresh morning air. The trees, the breeze, the silence—it’s all medicine 🍃",
            likeCount: 84,
            commentCount: 6,
            repostCount: 2,
            sharedCount: 1,
            photos: [
                "pr1", "pr1", "pr1", "pr1",
            ]
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60),
            profileImage: "pr2",
            profileName: "DevJake",
            text:
                "When SwiftUI clicks… it *clicks*. Just built a clean UI in 20 mins without touching constraints.",
            likeCount: 230,
            commentCount: 19,
            repostCount: 5,
            sharedCount: 3,
            photos: []
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60 * 5),
            profileImage: "pr3",
            profileName: "SarahHikes",
            text:
                "A full day in the wild with no signal, just fresh pine, a trail, and my own pace. Highly recommend.",
            likeCount: 145,
            commentCount: 11,
            repostCount: 4,
            sharedCount: 2,
            photos: ["pr3", "pr3"]
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60 * 24 * 3),
            profileImage: "pr4",
            profileName: "Andy",
            text:
                "First time trying street photography 📸 Loved the energy, the chaos, and the unexpected frames.",
            likeCount: 0,
            commentCount: 0,
            repostCount: 2,
            sharedCount: 0,
            photos: ["pr4"]
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60 * 24 * 5),
            profileImage: "pr5",
            profileName: "EmilyCodes",
            text: """
                Working remotely has changed everything:
                1. Less time in traffic
                2. More time with family
                3. Finally focused deep work
                Highly recommend async teams 💻
                """,
            likeCount: 310,
            commentCount: 27,
            repostCount: 11,
            sharedCount: 6,
            photos: []
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60 * 24 * 30),
            profileImage: "pr6",
            profileName: "NomadLife",
            text:
                "Café hopping in Portugal today. Amazing espresso, even better vibes 🇵🇹☕️",
            likeCount: 102,
            commentCount: 9,
            repostCount: 3,
            sharedCount: 1,
            photos: ["pr6", "pr6"]
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60 * 24 * 60),
            profileImage: "pr7",
            profileName: "Jason",
            text:
                "No caption. Just 7 snapshots from the most beautiful day I've had in years.",
            likeCount: 77,
            commentCount: 5,
            repostCount: 2,
            sharedCount: 0,
            photos: [
                "pr7", "pr7", "pr7",
                "pr7", "pr7", "pr7", "pr7",
            ]
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60 * 24 * 150),
            profileImage: "pr8",
            profileName: "Mia",
            text:
                "Some days are for deep thoughts. Others are for donuts. Today was definitely a donut day 🍩",
            likeCount: 0,
            commentCount: 0,
            repostCount: 0,
            sharedCount: 0,
            photos: []
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60 * 24 * 365),
            profileImage: "pr9",
            profileName: "BenUI",
            text: """
                SwiftUI tip:
                Use `.transition(.opacity.combined(with: .slide))` when switching views for smooth animations.
                Makes a HUGE difference 👌
                """,
            likeCount: 160,
            commentCount: 14,
            repostCount: 6,
            sharedCount: 2,
            photos: []
        ),
        PostData(
            postCreatedDate:  Date().addingTimeInterval(-60 * 60 * 24 * 730),
            profileImage: "pr10",
            profileName: "ExplorerJess",
            text:
                "Quick throwback to my Iceland trip. Unreal colors, endless waterfalls, and total peace.",
            likeCount: 201,
            commentCount: 18,
            repostCount: 7,
            sharedCount: 4,
            photos: ["pr10", "pr10", "pr10"]
        ),
    ]

}
```

</details>

<details>
<summary><code>ThreadsIconShape</code></summary>

<br>

```swift
import SwiftUI

struct ThreadsIconShape: Shape {
    func path(in rect: CGRect) -> Path {
        var path = Path()
        let scaleX = rect.width / 48
        let scaleY = rect.height / 48

        func scale(_ x: CGFloat, _ y: CGFloat) -> CGPoint {
            CGPoint(x: x * scaleX, y: y * scaleY)
        }

        path.move(to: scale(39.9999, 16))
        path.addCurve(
            to: scale(7.99995, 16),
            control1: scale(35.9999, 0),
            control2: scale(11.9999, 0)
        )
        path.addCurve(
            to: scale(23.9999, 44),
            control1: scale(3.99995, 32),
            control2: scale(10.9999, 44)
        )
        path.addCurve(
            to: scale(31.9999, 24),
            control1: scale(36.9999, 44),
            control2: scale(43.9999, 28.8)
        )

        path.move(to: scale(31.9999, 24))
        path.addCurve(
            to: scale(17.9999, 32),
            control1: scale(19.9999, 19.2),
            control2: scale(13.9999, 28)
        )
        path.addCurve(
            to: scale(31.9999, 24),
            control1: scale(21.9999, 36),
            control2: scale(31.9999, 34)
        )

        path.move(to: scale(31.9999, 24))
        path.addCurve(
            to: scale(17.9999, 16),
            control1: scale(31.9999, 14),
            control2: scale(21.9999, 12)
        )

        return path
    }
}
```

</details>
