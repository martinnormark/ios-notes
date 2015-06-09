# iOS 9 notes
Personal favorites from WWDC 2015.

## Foundation
 - New API to correctly display person names: [`NSPersonNameComponentsFormatter`](https://developer.apple.com/library/prerelease/ios/releasenotes/General/iOS90APIDiffs/frameworks/Foundation.html)
 
## UIKit
 - [`UIStackView`](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UIStackView_Class_Reference/index.html#//apple_ref/occ/cl/UIStackView)
 - New localization API to query the text direction of the current user [added to UIView](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UIView_Class/index.html#//apple_ref/swift/clm/UIView/c:objc(cs)UIView(cm)userInterfaceLayoutDirectionForSemanticContentAttribute:)
 - [`UILayoutGuide`](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UILayoutGuide_Class_Reference/index.html#//apple_ref/occ/cl/UILayoutGuide): No more dummy views to reserve a rectangular space that can interact with Auto Layout.
 

## Apple Pay
 - Display an interface that lets users add cards to Apple Pay from within your app using [`PKAddPaymentPassViewController`](https://developer.apple.com/library/prerelease/ios/documentation/PassKit/Reference/PKAddPaymentPassViewController_Class/index.html)
 - Support for line items with non-final amounts, using new `type` parameter [`summaryItemWithLabel:amount:type:`](https://developer.apple.com/library/prerelease/ios/documentation/PassKit/Reference/PKPaymentSummaryItem_Ref/index.html#//apple_ref/occ/clm/PKPaymentSummaryItem/summaryItemWithLabel:amount:type:)

## HomeKit
 - Location and Event triggers [added to HomeKit](https://developer.apple.com/library/prerelease/ios/releasenotes/General/iOS90APIDiffs/frameworks/HomeKit.html).

## Swift 2

- Open Source !!!
- Swift 2 [migration tool](https://developer.apple.com/swift/) in Xcode 7

  >Xcode 7 includes a powerful migrator that will help convert your application and playground code to work with the latest syntax improvements in Swift 2.0.



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
