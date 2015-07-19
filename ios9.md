# iOS 9 notes
Personal favorites from WWDC 2015.

## Foundation
 - New API to correctly display person names: [`NSPersonNameComponentsFormatter`](https://developer.apple.com/library/prerelease/ios/releasenotes/General/iOS90APIDiffs/frameworks/Foundation.html)
 
## UIKit
 - [`UIStackView`](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UIStackView_Class_Reference/index.html#//apple_ref/occ/cl/UIStackView) is a new view to make it easier to layout subviews in vertical or horizontal stacks - or any combination of the two, nested together. Litte Bites of Cocoa has a [pretty nice example](http://littlebitesofcocoa.com/post/121598537380/16-uistackview). There's also a nice [video from WWDC 2015](https://developer.apple.com/videos/wwdc/2015/?id=218) that also contains nice run through of Auto Layout "mysteries" and a little clarity with best practices.
 - New localization API to query the text direction of the current user [added to UIView](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UIView_Class/index.html#//apple_ref/swift/clm/UIView/c:objc(cs)UIView(cm)userInterfaceLayoutDirectionForSemanticContentAttribute:)
 - [`UILayoutGuide`](https://developer.apple.com/library/prerelease/ios/documentation/UIKit/Reference/UILayoutGuide_Class_Reference/index.html#//apple_ref/occ/cl/UILayoutGuide): No more dummy views to reserve a rectangular space that can interact with Auto Layout.
 - [`UICollectionView` re-ordering](http://nshint.io/blog/2015/07/16/uicollectionviews-now-have-easy-reordering/) supported natively!
 
## SafariServices
 - [`SFSafariViewController`](https://developer.apple.com/library/prerelease/ios/releasenotes/General/iOS90APIDiffs/frameworks/SafariServices.html) hands you the full blown mobile Safari experience within you app. Most importantly it let's you share cookies with your own web site/app which will help you [add context to first-run experiences](https://library.launchkit.io/how-ios-9-s-safari-view-controller-could-completely-change-your-app-s-onboarding-experience-2bcf2305137f) right after installing an app.

## Apple Pay + PassKit (Wallet)
 - Display an interface that lets users add cards to Apple Pay from within your app using [`PKAddPaymentPassViewController`](https://developer.apple.com/library/prerelease/ios/documentation/PassKit/Reference/PKAddPaymentPassViewController_Class/index.html)
 - Support for line items with non-final amounts, using new `type` parameter [`summaryItemWithLabel:amount:type:`](https://developer.apple.com/library/prerelease/ios/documentation/PassKit/Reference/PKPaymentSummaryItem_Ref/index.html#//apple_ref/occ/clm/PKPaymentSummaryItem/summaryItemWithLabel:amount:type:)
 - Dedicated [`shippingMethods`](https://developer.apple.com/library/prerelease/ios/documentation/PassKit/Reference/PKPaymentRequest_Ref/#//apple_ref/occ/instp/PKPaymentRequest/shippingMethods) array on [PKPaymentRequest](https://developer.apple.com/library/prerelease/ios/documentation/PassKit/Reference/PKPaymentRequest_Ref/), using the new [`PKShippingMethod` type](https://developer.apple.com/library/ios/documentation/PassKit/Reference/PKShippingMethod_Ref/)
 - Passbook Passes that work with Apple Pay (loyalty, rewards)
 - Quite a few new interessting methods in [`PKPassLibrary`](https://developer.apple.com/library/prerelease/ios/documentation/PassKit/Reference/PKPassLibrary_Ref/index.html#//apple_ref/occ/cl/PKPassLibrary)
 - WWDC 2015 session: [Wallet - The home for Apple Pay and more](https://developer.apple.com/videos/wwdc/2015/?id=701)

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
