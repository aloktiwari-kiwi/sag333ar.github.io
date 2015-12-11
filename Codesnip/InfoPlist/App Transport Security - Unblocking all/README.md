###Unblocking all

1. Go to info.plist
2. Right click on `Info.plist`
3. `Open as` -> `Source Code`
4. At the end, add following lines before `</dict></plist>` 

```xml
<key>NSAppTransportSecurity</key>
<dict>
	<key>NSAllowsArbitraryLoads</key>
	<true/>
</dict>
```
