###Apply Transparency to UINavigationBar in iOS

***Step 1.*** Put following lines of code in your class

```Objective-c
- (void)applyTransparencyToNavigationControllersBar:(UINavigationController *)nvCtr {
    nvCtr.navigationBar.translucent = YES;
    nvCtr.navigationBar.shadowImage = [UIImage new];
    nvCtr.view.backgroundColor = [UIColor clearColor];
    [nvCtr.navigationBar setBackgroundImage:[UIImage new] forBarMetrics:UIBarMetricsDefault];
    nvCtr.navigationBar.backgroundColor = [UIColor clearColor];
}
```

---

***Step 2.*** Invoke above method by passing your UINavigationController's object as parameter to following method.

---