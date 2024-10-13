---
title: "Label"
draft: false
weight: 60
appledoc_url: https://developer.apple.com/documentation/swiftui/labelstyle
xcode_version: "16.1 beta 3"
tags:
 - "Xcode 16.1 beta 3"
---

{{< liteyoutube "p3eztg5x04o" >}}

## System Styles

Use the snippet below to see all of the built-in styles

```swift            
Label {
    Text("Pizza Party")
} icon: {
    Image(systemName: "party.popper")
}
.labelStyle(.automatic)

Label {
    Text("Pizza Party")
} icon: {
    Image(systemName: "party.popper")
}
.labelStyle(.titleOnly)

Label {
    Text("Pizza Party")
} icon: {
    Image(systemName: "party.popper")
}
.labelStyle(.iconOnly)

Label {
    Text("Pizza Party")
} icon: {
    Image(systemName: "party.popper")
}
.labelStyle(.titleAndIcon)
```

## Custom Style

Create your style struct and have it conform to `LabelStyle`. It is customary for all label styles to be named `...LabelStyle`. The `Configuration` type contains `.icon` and `.title` for you to use as you wish to style the label.

```swift
struct PartyNametagLabelStyle: LabelStyle {
    func makeBody(configuration: Configuration) -> some View {
        HStack {
            configuration.icon

            configuration.title

            configuration.icon
                .rotation3DEffect(.radians(.pi), axis: (x: 0, y: 1, z: 0))
        }
        .padding(10)
        .overlay {
            Capsule()
                .stroke(lineWidth: 5)
        }
    }
}
```

In order to use the nice `.labelStyle(.partyNameTag)` syntax, we must extend the `LabelStyle` protocol. Without this, we would have to use `.labelStyle(PartyNameTagLabelStyle())`, which is now considered an old way of using styles.

```swift
extension LabelStyle where Self == PartyNameTagLabelStyle {
    static var partyNameTag: Self { .init() }
}
```

See the label style in action by using the following code in your view. 

```swift
Label {
    Text("Pizza Party")
} icon: {
    Image(systemName: "party.popper")
}
.labelStyle(.partyNameTag)
```

## Explore

* Under what contexts does the automatic style change?

{{< xcode-version >}}
{{< apple-doc-url >}}