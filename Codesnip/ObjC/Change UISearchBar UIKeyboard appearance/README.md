###How to change UISearchBar Keyboard Appearance

---

```Objective-c
+ (void)changeSearchBarColor:(UISearchBar *)searchBar {
	for (UIView *subview in searchBar.subviews) {
		for (UIView *subSubview in subview.subviews) {
			if ([subSubview conformsToProtocol:@protocol(UITextInputTraits)]) {
				UITextField *textField = (UITextField *)subSubview;
				[textField setKeyboardAppearance: UIKeyboardAppearanceAlert];
				break;
			}
		}
	}
}
```

---