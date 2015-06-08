# iOS 9 notes
Personal favorites from WWDC 2015.

## Foundation
 - New API to correctly display person names: [`NSPersonNameComponentsFormatter`](https://developer.apple.com/library/prerelease/ios/releasenotes/General/iOS90APIDiffs/frameworks/Foundation.html)
 
## UIKit
 - New localization API to query the text direction of the current user [added to UIView](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UIView_Class/index.html#//apple_ref/swift/clm/UIView/c:objc(cs)UIView(cm)userInterfaceLayoutDirectionForSemanticContentAttribute:)

## HomeKit
 - Location and Event triggers [added to HomeKit](https://developer.apple.com/library/prerelease/ios/releasenotes/General/iOS90APIDiffs/frameworks/HomeKit.html).

## Swift 2

Open Source !!!

#### `guard`
```swift
guard let name = person["name"] else {
	return
}
```

#### `#availability`
```swift
if #available(iOS 9, OSX 10.10, *) {
    // Use iOS 9 APIs on iOS, and use OS X v10.10 APIs on OS X
} else {
    // Fall back to earlier iOS and OS X APIs
}
```

#### Protocol extensions (with constraints)
```swift
extension CollectionType where Generator.Element : TextRepresentable {
    func asList() -> String {
        return "(" + ", ".join(map({$0.asText()})) + ")"
    }
}
```

#### Error handling
```swift
func loadData() throws { }

func test() {
	￼do {
		￼try loadData()
	} catch {
		￼print(error)
	}
}
```
