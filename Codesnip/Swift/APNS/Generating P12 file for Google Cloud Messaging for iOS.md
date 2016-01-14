###Generating P12 file for Google Cloud Messaging for iOS

***Step 1***. Open [Your Developer Account](https://developer.apple.com/membercenter/index.action)

***Step 2***. Open `Certificates, Identifiers & Profiles`

![Certificates, Identifiers & Profiles](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/Certificates_Identifiers_Profiles.png?raw=true)

***Step 3***. Click on `Identifiers` & Click on `+` on top-right corner to `add application identifier`

***Step 4***. Provide `app name` and make sure your specify `Explicit APP ID` only. In following screen-shot `com.sagarrkothari.sampleapp` is sample one

![Sample image](http://google.com)

***Step 5***. Under `App Services` section, please make sure to enable `Push Notifications` as indicated below.

![Sample image](http://google.com)

***Step 6***. Click `Continue`.

***Step 7***. Click `Submit`.

***Step 8***. Click `Done`.

***Step 9***. From the list of `App IDs` click on your app-id.

***Step 10***. Click on `Edit`.

![Sample image](http://google.com)

***Step 11.*** Scroll until the screen depicted as follows don't appear. Mostly it would be at the end of page.

![Sample image](http://google.com)

***Step 12.*** Click on `Create Certificate` for `Dev/Production` as per your need.

***Step 13.*** Now, you will need CSR file. For this, Go to `Keychain access`.

***Step 14.*** In `Keychain access`, open `Keychain access` menu & select the option as shown below.

![Sample image](http://google.com)

***Step 15.*** Enter email id & choose option `saved to disk` (`DO NOT` tick on let me specify key pair info)

![Sample image](http://google.com)

***Step 16.*** Click continue & save the file(`CertificateSigningRequest.certSigningRequest`) on desktop.

***Step 17.*** Go back to browser & click on `Continue` & upload `CertificateSigningRequest.certSigningRequest` file.

![Sample image](http://google.com)

