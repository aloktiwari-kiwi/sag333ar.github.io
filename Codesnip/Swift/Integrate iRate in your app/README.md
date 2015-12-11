###Integrate iRate in your app

---

***Step 1.*** Open pod file & add pod as follows.

```
pod 'iRate'
```

---

***Step 2.*** Install Pod & open `your-app-Bridging-Header.h` & import iRate library as follows.

```
#import <iRate/iRate.h>
```

***Step 3.*** Open AppDelegate.swift

Your `didFinishLaunchingWithOptions` method should look like as follows.

```

	iRate.sharedInstance().applicationBundleID = "com.yourcompany.yourapp"
	iRate.sharedInstance().cancelButtonLabel = nil
	iRate.sharedInstance().daysUntilPrompt = 5
	iRate.sharedInstance().usesUntilPrompt = 15
```

---

***Step 3.*** To launch App Rating, put code as follows

```
	func rateThisApp() {
		iRate.sharedInstance().openRatingsPageInAppStore()
	}
```