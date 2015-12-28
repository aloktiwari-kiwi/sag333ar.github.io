####Convert data to Base64 String

```Swift
class func base64_string_from_data(data:NSData) -> String {
	let base64EncodedString = data.base64EncodedStringWithOptions(NSDataBase64EncodingOptions(rawValue: 0))
	return base64EncodedString
}
```

---

####Convert Base64 String to data

```Swift	
class func base64_data_from_string(string:String) -> NSData {
	let data = NSData(base64EncodedString: string, options: NSDataBase64DecodingOptions(rawValue: 0))!
	return data
}
```
