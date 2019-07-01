### MVVM Clean Arch Template

### How to use
- clone this repo
- move/copy root directory into /Applications/Android Studio.app/Contents/plugins/android/lib/templates/other/clean-arch-mvvm-template
- restart your android studio

### Requirement
##### Parcelize (Kotlin only)
- Kotlin version 1.1.4 or newer
- Add this code to your app/gradle
`
android {
    // ...
    androidExtensions {
        experimental = true
    }
    // ... 
}
`
- `apply plugin: 'kotlin-android-extensions'`
##### Parcelable generator
- ![How to install the plugin](https://i.imgur.com/jceThxd.gif)
- [Full article tutorial](https://corochann.com/fast-easy-parcelable-implementation-with-android-studio-parcelable-plugin-641.html)
  
### 3 Layer
```
presentation
    ^
    |
  data
    ^
    |
  domain (knows nothing about the outer layer, this is innermost layer)
```

### Description
This template inshaa Allah use best practice to implement clean arch, to avoid misusing the architecture
1. domain layer
    - entity act as a mapper / transformer
2. data layer
    - model
    - repository (local, mock, network)
3. presentation layer 
    - mvvm
4. utils layer (available for all layer, not included on this template)
    - components, widget, custom ui, permission, utils

### TODO
- [ ] Restrict minimum [dependencies to add](https://www.i-programmer.info/professional-programmer/resources-and-tools/6845-android-adt-template-format-document.html) go to *<dependency>* 
- [ ] Support java and kotlin srcDir. You must pay attention $srcDir still pointing to src/main/java. So, if you using kotlin (src/main/kotlin), you might wanna to update this template to use hardcoded string instead.
- [ ] Provide more descriptive how to use.
- [ ] Implement datasource switch on repository
- [ ] Differentiate *Entity for room, mapper/transformer, to prevent *Entity dependent with external plugins (Room)
     
### References
- https://github.com/android10/Android-CleanArchitecture-Kotlin