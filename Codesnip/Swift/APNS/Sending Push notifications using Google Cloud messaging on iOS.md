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

and make sure that you've following `variables` defined under `window?` object.

```Swift
	// GCM
	var connectedToGCM = false
	var subscribedToTopic = false
	var gcmSenderID: String?
	var registrationToken: String?
	var registrationOptions = [String: AnyObject]()
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

***Step 13.*** Update `didReceiveRemoteNotification` method as follows.

```Swift
func application( application: UIApplication, didReceiveRemoteNotification userInfo: [NSObject : AnyObject]) {
		print("Notification received: \(userInfo)")
		GCMService.sharedInstance().appDidReceiveMessage(userInfo)
		UIApplication.sharedApplication().applicationIconBadgeNumber = UIApplication.sharedApplication().applicationIconBadgeNumber + 1
}
```

***Step 14.*** Update `didReceiveRemoteNotification userInfo:fetchCompletionHandler:` method as follows.

```Swift
func application(application: UIApplication, didReceiveRemoteNotification userInfo: [NSObject : AnyObject], fetchCompletionHandler handler: (UIBackgroundFetchResult) -> Void) {
		print("Notification received: \(userInfo)")
		GCMService.sharedInstance().appDidReceiveMessage(userInfo);
		UIApplication.sharedApplication().applicationIconBadgeNumber = UIApplication.sharedApplication().applicationIconBadgeNumber + 1
}
```

***Step 15.*** Update `didFailToRegisterForRemoteNotificationsWithError` method as follows.

```Swift
func application(application: UIApplication, didFailToRegisterForRemoteNotificationsWithError error: NSError) {
	print("Handle error")
}
```

***Step 16.*** Add following methods to your `AppDelegate.swift`

```Swift
func registrationHandler(registrationToken: String!, error: NSError!) {
	if (registrationToken != nil) {
		self.registrationToken = registrationToken
		print("Registration Token: \(registrationToken)")
	} else {
		print("Registration to GCM failed with error: \(error.localizedDescription)")
	}
}

func onTokenRefresh() {
	GGLInstanceID.sharedInstance().tokenWithAuthorizedEntity(gcmSenderID, scope: kGGLInstanceIDScopeGCM, options: registrationOptions, handler: registrationHandler)
}
func willSendDataMessageWithID(messageID: String!, error: NSError!) {
	if (error != nil) {
		// Failed to send the message.
	} else {
		// Will send message, you can save the messageID to track the message
	}
}

func didSendDataMessageWithID(messageID: String!) {

}

func didDeleteMessagesOnServer() {

}
```

***Step 17.*** Update `applicationDidEnterBackground` & `applicationDidBecomeActive` method as follows.

```Swift
func applicationDidEnterBackground(application: UIApplication) {
	GCMService.sharedInstance().disconnect()
	self.connectedToGCM = false
}

func applicationDidBecomeActive(application: UIApplication) {
	GCMService.sharedInstance().connectWithHandler({
		(NSError error) -> Void in
		if error != nil {
			print("Could not connect to GCM: \(error.localizedDescription)")
		} else {
			self.connectedToGCM = true
			print("Connected to GCM")
		}
	})
}
```

***Step 18.*** Run the project in iOS Device. From the log, look for `"Registration Token: ` text. Copy Token & generate request as follows.

**URL** : `https://gcm-http.googleapis.com/gcm/send`

**Headers** 

1. `Content-Type` : `application/json`
2. `Authorization` : `key=MY_SERVER_KEY` generated from https://console.developers.google.com/home/dashboard?project=YOUR_PROJECT

**MEHOTD** : `POST`

**BODY** : as follows

```json
{
  "to" : "l5ERMbNVd_U:APA91bFjOXoXZb01C-lEppOXXDGSRUnd0ZmJFahaeeoN6QoGc7p4wErWKSOB4nYhLePotUUBxuAxUSxz5U1IB_s9MHjLNl5QAtq1B3ii7VYOWV8Yjd0smAeo2XW7_YDlEM8K8guPEjME",
  "data" : {
    "message" : "great match!",
    "action" : "display",
     "title" : "Alert from SKothari", 
     "deviceType" : "IOS" 
    },
   "notification" : {
   	"body" : "Hello from GCM"
   }
}
```

![Sample usecase from DHC](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/sample_usecase_from_dhc.png?raw=true)