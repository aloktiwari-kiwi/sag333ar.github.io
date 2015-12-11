###Format a JSON String Pretty Print

---

```Objective-c
+ (NSString*) formatJSONPretty:(NSData *)data {
	id obj = [NSJSONSerialization JSONObjectWithData:data options:NSJSONReadingAllowFragments error:nil];
	if (obj) {
		NSData* d = [NSJSONSerialization dataWithJSONObject:obj options:NSJSONWritingPrettyPrinted error:nil];
		return [[NSString alloc] initWithData:d encoding:NSUTF8StringEncoding];
	} else {
		return nil;
	}
}
```

---