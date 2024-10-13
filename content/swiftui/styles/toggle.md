---
title: "Toggle"
draft: false
weight: 30
appledoc_url: https://developer.apple.com/documentation/swiftui/view-styles#Styling-toggles
xcode_version: "16.1 beta 3"
tags:
 - "Xcode 16.1 beta 3"
---

{{< liteyoutube "D8TUsPrDP48" >}}

## System Styles

Use the snippet below to see all of the built-in styles.

```swift
Toggle("Automatic", isOn: $myBool)
    .toggleStyle(.automatic)

Toggle("Button Toggle Style", isOn: $myBool)
    .toggleStyle(.button)

Toggle("Switch Toggle Style", isOn: $myBool)
    .toggleStyle(.switch)
```

## Custom Style

Create your style struct and have it conform to `ToggleStyle`. It is customary for all toggle styles to be named `...ToggleStyle`. The `Configuration` type contains `.label`, `.isOn`, and `.isMixed` for you to use as you wish to style the button. It is up to you to use a gesture with an updating state if you want to have an `isPressed` appearance.

```swift
struct MyToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        VStack {
            configuration.label
            
            image(systemName: systemName(isOn: configuration.isOn))
        }
        .onTapGesture {
            configuration.isOn.toggle()
        }
        .overlay {
            if configuration.isMixed {
                warningBorder
            }
        }
    }

    func systemName(isOn: Bool) -> String {
        isOn ? "hare" : "xmark.circle"
    }

    func image(systemName: String) -> some View {
        Image(systemName: systemName)
            .resizable()
            .scaledToFit()
            .frame(width: 50, height: 50)
    }

    var warningBorder: some View {
        Rectangle()
            .stroke(lineWidth: 3)
            .foregroundStyle(.orange)
    }
}
```

In order to use the nice `.toggleStyle(.myToggle)` syntax, we must extend the `ToggleStyle` protocol. Without this, we would have to use `.toggleStyle(MyToggleStyle())`, which is now considered an old way of using styles.

```swift
extension ToggleStyle where Self == MyToggleStyle {
    static var myToggle: Self { .init() }
}
```

See the toggle style in action by using the following code in your view. 

```swift
Toggle("My Toggle Style", isOn: $myBool)
    .toggleStyle(.myToggle)
```

If you want to use a multi-value switch, consider this example. Note that the state property used here is initialized as `@State private var sources = [false, false, false]`. Using the index to retrieve the state values is not something I would ever recommend but I do not want to complicate this example by creating a new type just for this example. 

```swift
Toggle(sources: $sources, isOn: \.self) {
    Text("Play with `isMixed`")
}
.toggleStyle(.myToggle)

Toggle("Source 1/3", isOn: $sources[0])
Toggle("Source 2/3", isOn: $sources[1])
Toggle("Source 3/3", isOn: $sources[2])
```

Note that if the states are all `false` or mixed then the "parent" toggle will be considered "off" and when you turn it "on" it will change all of the states to `true`. The parent toggle will only be "on" if all the states are `true` and then if you turn it off all of the states will  be turned to `false` simultaneously.

## Explore

* Under what contexts does the automatic style change?

{{< xcode-version >}}
{{< apple-doc-url >}}