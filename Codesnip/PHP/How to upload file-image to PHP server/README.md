###How to upload an image to PHP server using iOS app?

---

#####PHP Code is as follows

```php
<?php
$uploaddir = 'uploads/';
$file = basename($_FILES['uploadedfile']['name']);
$uploadfile = $uploaddir . $file;

echo "file=".$file; //is empty, but shouldn't

if (move_uploaded_file($_FILES['uploadedfile']['tmp_name'], $uploadfile)) {
    echo $file;
}
else {
    echo "error";
}
?>
```

#####iOS Code is as follows

```Objective-c
NSData *imageData = UIImagePNGRepresentation(delegate.dataBean.image);
NSString *urlString = [NSString stringWithFormat:@"%@test.php", delegate.dataBean.hosterURL];

NSMutableURLRequest *request = [[NSMutableURLRequest alloc] init];
[request setURL:[NSURL URLWithString:urlString]];
[request setHTTPMethod:@"POST"];

NSString *boundary = [NSString stringWithString:@"---------------------------14737809831466499882746641449"];
NSString *contentType = [NSString stringWithFormat:@"multipart/form-data; boundary=%@",boundary];
[request addValue:contentType forHTTPHeaderField: @"Content-Type"];

NSMutableData *body = [NSMutableData data];
[body appendData:[[NSString stringWithFormat:@"\r\n--%@\r\n",boundary] dataUsingEncoding:NSUTF8StringEncoding]];
[body appendData:[[NSString stringWithFormat:@"Content-Disposition: form-data; name=\"uploadedfile\"; filename=\"test.png\"\r\n"] dataUsingEncoding:NSUTF8StringEncoding]];
[body appendData:[[NSString stringWithString:@"Content-Type: application/octet-stream\r\n\r\n"] dataUsingEncoding:NSUTF8StringEncoding]];
[body appendData:[NSData dataWithData:imageData]];
[body appendData:[[NSString stringWithFormat:@"\r\n--%@--\r\n",boundary] dataUsingEncoding:NSUTF8StringEncoding]];
[request setHTTPBody:body];

NSData *returnData = [NSURLConnection sendSynchronousRequest:request returningResponse:nil error:nil];
NSString *returnString = [[NSString alloc] initWithData:returnData encoding:NSUTF8StringEncoding];

NSLog([NSString stringWithFormat:@"Image Return String: %@", returnString]);
```
