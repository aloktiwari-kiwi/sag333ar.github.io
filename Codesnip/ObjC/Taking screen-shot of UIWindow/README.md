###How to take a screen-shot of a UIWindow

---

```Objective-c
- (UIImage *)getTheScreenShotFromWindow
{
    // get the window size
    UIWindow *window = [[[UIApplication sharedApplication] delegate] window];
    CGSize size = window.size;
    
    // check the scale - retina or regular 
    if ([[UIScreen mainScreen] respondsToSelector:@selector(scale)])
        UIGraphicsBeginImageContextWithOptions(size, NO, [UIScreen mainScreen].scale);
    else
        UIGraphicsBeginImageContext(size);
    
    // get the context    
    window.rootViewController.view.layer renderInContext:UIGraphicsGetCurrentContext()];
    
    // save the context to image
    UIImage *image = UIGraphicsGetImageFromCurrentImageContext();
    UIGraphicsEndImageContext();
    
    // return the image
    return image;
}
```

---