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
