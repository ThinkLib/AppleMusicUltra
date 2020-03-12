![Apple Music Ultra](Media/Cover.jpg)

# Ultra for Apple Music
 A custom Apple Music client with themes, personalized settings and more.

## Themes
![Apple Music Ultra](Media/themes-7.gif)

Ultra for Apple Music is a personalized Music client with custom themes, settings and more using CSS->JavaScript injection through the beautiful object that is WKWebView.

## [Download Latest Stable Build](https://github.com/revblaze/AppleMusicUltra/releases/download/v0.3-alpha/Ultra_v0.3-alpha.zip)
`Ultra-v0.3.zip (5.5MB) build 3`

Left-click `Ultra for Apple Music.app > Open` to bypass the App Store wall & drag-drop to `/Applications` if you want to keep it after trying. 🤗

Updating from an older version? Drag and drop to `/Applications` and click `Replace`.

<i>This app is currently under heavy development</i>

# Customization
Allow users to personalize their Apple Music with customization.

**Basic Syntax:** `setTheme(Style, darkMode: Bool, media: Any, type: String)`

### Styles
![Apple Music Ultra](Media/transparent-4.gif)
Styles are the top-layer effects that appear over every theme type. Using `setTheme`, they can be set to overlap your object-based theme to add some vibrant effects; or alternatively, they can be set to blur your system background using the built-in function `setTransparentTheme()`.

**Tansparent:** `setTheme(NSVisualEffectView.Material, darkMode: Bool, media: nil, type: "transparent")`

**with Object:** `setTheme(NSVisualEffectView.Material, darkMode: Bool, media: Object, type: String)`

### Custom User Themes
![Apple Music Ultra](Media/custom-fade-5.gif)
```
 let imageURL = selectImageFile()
 setTheme(NSVisualEffectView.Material, darkMode: Bool, media: URL, type: "image")
 ```
 
 ```
 func selectImageFile() -> URL {
     let dialog = NSOpenPanel()
     dialog.allowsMultipleSelection = false
     dialog.allowedFileTypes = ["png", "jpg", "jpeg"]
     
     if (dialog.runModal() == NSApplication.ModalResponse.OK) {
         if let result = dialog.url?.absoluteURL {
             return result
         }
     }
}
```

## Structure <sup>for now...</sup>
```
let fx = NSVisualEffectView.Material
struct Style {                                 //                          rawValue
    static let preset = fx.appearanceBased     // Default Preset               0
    // Light Mode                              LIGHT
    static let frosty   = fx.sheet             // Frosty       (Opaque)        11
    static let bright   = fx.mediumLight       // Bright       (Middle)        8
    static let energy   = fx.light             // Vibrant      (Transparent)   1
    // Dark Mode                               DARK
    static let cloudy   = fx.ultraDark         // Cloudy       (Opaque)        9
    static let dark     = fx.toolTip           // Dark         (Middle)        17
    static let vibrant  = fx.dark              // Vibrant      (Transparent)   2
}
```


## Requirements
Requires macOS 10.14 or later.

<sub><i>Please note that the app is being built with Swift 5.</i></sub>
