---
title: "Label"
draft: true
weight: 50
appledoc_url: https://developer.apple.com/documentation/swiftui/buttonstyle
xcode_version: "16.1 beta 3"
tags:
 - "Xcode 16.1 beta 3"
---

* Applies to `NavigationLink` unless it is in a `List` or `Form`
* `Link` looks like a `Button` but you cannot change the style

## Discussion

* Must use a style if you want an `isPressed` appearance

## Customizable

### Button

#### System Styles

* Use the snippet below to see all of the built-in button styles

```swift
Button("Auto Button Style") { }
    .buttonStyle(.automatic)

Button("Plain Button Style") { }
    .buttonStyle(.plain)

Button("Bordered Button Style") { }
    .buttonStyle(.bordered)

Button("Bordered Button Style Prominent") { }
    .buttonStyle(.borderedProminent)

Button("Borderless Button Style") { }
    .buttonStyle(.borderless)
```

#### Custom Styles

* Inherit from `ButtonStyle` in almost all cases
* Only inherit from `PrimitiveButtonStyle` to define your own interactions
* Can add properties to the style struct if desired

#### Custom ButtonStyle

* Inherit from `ButtonStyle` in almost all cases
* No need to add gestures to work, everything is included

Create your style struct and have it conform to `ButtonStyle`. It is customary for all button styles to be named `...ButtonStyle`. The `Configuration` type contains `.label`, `.isPressed`, and `.role` for you to use as you wish to style the button.

```swift
struct MyButtonStyle: ButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        HStack(alignment: .firstTextBaseline) {
            image(for: configuration.role)

            configuration.label
        }
        .overlay {
            if configuration.isPressed {
                border
            }
        }
    }

    var border: some View {
        RoundedRectangle(cornerRadius: 5)
            .stroke(lineWidth: 3)
    }

    func image(for role: ButtonRole?) -> Image {
        let systemName = switch role {
            case .cancel: "xmark.circle"
            case .destructive: "trash"
            default: "face.smiling"
        }

        return Image(systemName: systemName)
    }
}
```

In order to use the nice `.buttonStyle(.myButton)` syntax, we must extend the `ButtonStyle` protocol. Without this, we would have to use `.buttonStyle(MyButtonStyle())`, which is now considered an old way of using styles.

```swift
extension ButtonStyle where Self == MyButtonStyle {
    static var myButton: Self { .init() }
}
```

See the button style in action by using the following code in your view. 

```swift
Button("My Button Style") { }
    .buttonStyle(.myButton)

Button("My Button Style", role: .cancel) { }
    .buttonStyle(.myButton)

Button("My Button Style", role: .destructive) { }
    .buttonStyle(.myButton)
```

#### Custom PrimitiveButtonStyle

* Only inherit from `PrimitiveButtonStyle` when `ButtonStyle` is not sufficient
* You must add a gesture to run the button's action

The Configuration type contains `.label`, `.trigger`, and `.role` for you to use as you wish to style the button.

Here is the setup

```swift
struct MyPrimitiveButtonStyle: PrimitiveButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        configuration.label
            .foregroundStyle(color(for: configuration.role))
            .onTapGesture(perform: configuration.trigger)
    }

    func color(for role: ButtonRole?) -> Color {
        switch role {
            case .cancel: .orange
            case .destructive: .purple
            default: .green
        }
    }
}

extension PrimitiveButtonStyle where Self == MyPrimitiveButtonStyle {
    static var myPrimitiveButton: Self { .init() }
}
```
and the usage

```swift
Button("My Primitive Button Style") { }
    .buttonStyle(.myPrimitiveButton)

Button("My Primitive Button Style", role: .cancel) { }
    .buttonStyle(.myPrimitiveButton)

Button("My Primitive Button Style", role: .destructive) { }
    .buttonStyle(.myPrimitiveButton)
```

#### Add Button Style Properties

If you also need to pass arguments to your style, you can add them like any other struct and pass the arguments through the extension. 

Add the property to the struct.

```swift
struct MyButtonStyle: ButtonStyle {
    let myToggleProperty: Bool

    func makeBody(configuration: Configuration) -> some View {
        //
    }
}
```

Change the `var` to a `func` with a parameter that is passed to the struct.

```swift
extension ButtonStyle where Self == MyButtonStyle {
    static func myButton(myToggle: Bool): Self { 
        .init(myToggleProperty: myToggle) 
    }
}
```

Pass your value as an argument where you use the button style.

```swift
Button("My Button Style") {
    // no-op
}
.buttonStyle(.myButton(myToggle: true))
```

{{< xcode-version >}}
{{< apple-doc-url >}}