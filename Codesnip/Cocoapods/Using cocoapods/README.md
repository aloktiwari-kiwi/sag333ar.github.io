###Using CocoaPods for iOS Application development

---

####Installing CocoaPods
If cocoapod is not already available, install it using following command.

```
$ sudo gem install cocoapods
```

---

###Updating (Installing latest) CocoaPods

***Step 1.*** Update rubygem 

```
sudo gem update --system
```

***Step 2.*** Install CocoaPods

```
sudo gem install cocoapods
```

***Step 3.*** Setup the installed Cocoapods

```
pod setup
```

---


###Using CocoaPods

***Step 1.*** Navigate to `YourXCodeProject.xcodeproj`

***Step 2.*** Create file called `Podfile` (no extension & exact name)

***Step 3.*** Enter the text contents as follows in that file.

```
# Under target name, you should give your project's target name.
# In this case, we've given KRC as the target/product name.

target "KRC" do

# add the dependencies here. In this case, I've added SRKUtility, SidePanles etc.
	pod 'SRKUtility'
	pod 'JASidePanels'
	pod 'Fabric'
	pod 'Crashlytics'
	pod 'iRate'
	pod 'apptentive-ios'

# make sure to put the "end"

end

```

---