###Sending Push notifications using Google Cloud messaging on iOS

#####iOS Setup

***Step 1.*** Add `pod 'Google/CloudMessaging'` in to your pod file.

***Step 2.*** Install the pods - `pod install`

***Step 3.*** Make Sure you disable the `enable bitcode` from your target->build settings.

***Step 4.*** Now go to any-browser and open `https://developers.google.com/mobile/add` & click on `Pick a platform`, choose `iOS App`.

***Step 5.*** Do as shown in the following `gif` file.

![Enable Cloud messaging.gif](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/Enable%20Cloud%20messaging.gif?raw=true)

***Step 6.*** As Shown in the last step in above image, You would need dev-certification-p12 & production-certifcate-p12 for specific app-id.
So, [Click here to view detailed article for that.](http://google.com)

