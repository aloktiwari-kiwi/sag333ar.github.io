###Generating P12 file for Google Cloud Messaging for iOS

***Step 1***. Open [Your Developer Account](https://developer.apple.com/membercenter/index.action)

***Step 2***. Open `Certificates, Identifiers & Profiles`

![Certificates, Identifiers & Profiles](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/Certificates_Identifiers_Profiles.png?raw=true)

***Step 3***. Click on `Identifiers` & Click on `+` on top-right corner to `add application identifier`

***Step 4***. Provide `app name` and make sure your specify `Explicit APP ID` only. In following screen-shot `com.sagarrkothari.sampleapp` is sample one

![Explicit_APP_ID](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/Explicit_APP_ID.png?raw=true)

***Step 5***. Under `App Services` section, please make sure to enable `Push Notifications` as indicated below.

![Push Notifications](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/Push_notification.png?raw=true)

***Step 6***. Click `Continue`.

***Step 7***. Click `Submit`.

***Step 8***. Click `Done`.

***Step 9***. From the list of `App IDs` click on your app-id.

***Step 10***. Click on `Edit`.

![Edit Application ID](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/Edit_notification.png?raw=true)

***Step 11.*** Scroll until the screen depicted as follows don't appear. Mostly it would be at the end of page.

![Scroll to end](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/scroll_to_push_notification.png?raw=true)

***Step 12.*** Click on `Create Certificate` for `Dev/Production` as per your need.

***Step 13.*** Now, you will need CSR file. For this, Go to `Keychain access`.

***Step 14.*** In `Keychain access`, open `Keychain access` menu & select the option as shown below.

![Keychain Request](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/keychain_request.png?raw=true)

***Step 15.*** Enter email id & choose option `saved to disk` (`DO NOT` tick on let me specify key pair info)

![Keychain save CertificateSigningRequest](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/keychain_create.png?raw=true)

***Step 16.*** Click continue & save the file(`CertificateSigningRequest.certSigningRequest`) on desktop.

***Step 17.*** Go back to browser & click on `Continue` & upload `CertificateSigningRequest.certSigningRequest` file.

![Keychain save CertificateSigningRequest](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/upload_request.png?raw=true)

***Step 18.*** Download the certificate. Double click on downloaded certificate. Go to key-chain, select added certificate along with private key as shown below.

![Export to p12](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Swift/APNS/export_to_p12.png?raw=true)

***Step 19.*** Now, Right click on PrivateKey+Certificate & export it as `.p12`