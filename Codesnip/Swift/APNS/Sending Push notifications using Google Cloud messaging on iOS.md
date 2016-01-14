###Sending Push notifications using Google Cloud messaging on iOS

#####iOS Setup

***Step 1.*** Add `pod 'Google/CloudMessaging'` in to your pod file.

***Step 2.*** Install the pods - `pod install`

***Step 3.*** Make Sure you disable the `enable bitcode` from your target->build settings.

***Step 4.*** Now go to any-browser and open `https://developers.google.com/mobile/add` & click on `Pick a platform`, choose `iOS App`.

***Step 5.*** Do as shown in the following `gif` file.

![Enable Cloud messaging.gif](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/Enable%20Cloud%20messaging.gif?raw=true)

***Step 6.*** As Shown in the last step in above image, You would need dev-certification-p12 & production-certifcate-p12 for specific app-id.
So, [Click here to view detailed article for that.](https://goo.gl/v7j7SL) 

***Step 7.*** Now upload that `.p12` file as indicated in following image.

![Enable Cloud messaging.gif](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/Enable_Cloud messaging_2.gif?raw=true)

***Step 8.*** Import that `GoogleService-Info.plist` into your project. Make sure your project/target has the same app/bundle-identifier.

***Step 9.*** Add Bridging header & import as follows.

```ObjC
#import <Google/CloudMessaging.h>
```

***Step 10.*** Add following protocols to your `AppDelegate`

```Swift
class AppDelegate: UIResponder, UIApplicationDelegate, GGLInstanceIDDelegate, GCMReceiverDelegate {
```

***Step 11.*** Update `didFinishLaunchingWithOptions` method as follows.

```Swift
func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {
	var configureError: NSError?
	GGLContext.sharedInstance().configureWithError(&configureError)
	assert(configureError == nil, "Error configuring Google services: \(configureError)")
	gcmSenderID = GGLContext.sharedInstance().configuration.gcmSenderID
	
	let gcmConfig = GCMConfig.defaultConfig()
	gcmConfig.receiverDelegate = self
	GCMService.sharedInstance().startWithConfig(gcmConfig)
}
```

***Step 12.*** Update `didRegisterForRemoteNotificationsWithDeviceToken` method as follows.

```Swift
func application(application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: NSData) {
	let instanceIDConfig = GGLInstanceIDConfig.defaultConfig()
	instanceIDConfig.delegate = self
	GGLInstanceID.sharedInstance().startWithConfig(instanceIDConfig)
	registrationOptions = [kGGLInstanceIDRegisterAPNSOption:deviceToken,kGGLInstanceIDAPNSServerTypeSandboxOption:true]
	GGLInstanceID.sharedInstance().tokenWithAuthorizedEntity(gcmSenderID, scope: kGGLInstanceIDScopeGCM, options: registrationOptions, handler: registrationHandler)
}
```
