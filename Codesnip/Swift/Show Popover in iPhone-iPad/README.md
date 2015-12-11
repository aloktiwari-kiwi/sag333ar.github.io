### Show Popover in iPhone-iPad

---

In this readme file, I'll explain how to show pop-over on iPhone/iPad without using any third party library.

***Step 1.*** Open your project & make sure you've one class from where you would like to show the pop-over and another class for the pop-over.

![Example-class-names-image](https://github.com/sag333ar/sag333ar.github.io/blob/master/Swift/Show%20Popover%20in%20iPhone-iPad/Classes.png?raw=true)

---

***Step 2.*** Open Storyboard & add a new view controller for pop-over & resize as per your need. Make sure you also apply the class name to view-controller.

![Example-image-for-step-2](https://github.com/sag333ar/sag333ar.github.io/blob/master/Swift/Show%20Popover%20in%20iPhone-iPad/HowToShowPopOver-1.gif?raw=true)

---

***Step 3.*** In your view-controller, add bar-button from where you can drag & drop segue to pop-over-controller. **Make sure you give the name to the segue.**

![Example-image-for-step-3](https://github.com/sag333ar/sag333ar.github.io/blob/master/Swift/Show%20Popover%20in%20iPhone-iPad/HowToShowPopOver-2.gif?raw=true)

---

***Step 4.*** In your view-controller, you make sure to extend `UIPopoverPresentationControllerDelegate`

---

***Step 5.*** Put following delegate method in your-view-controller.

```
	func adaptivePresentationStyleForPresentationController(controller: UIPresentationController) -> UIModalPresentationStyle {
		return UIModalPresentationStyle.None
	}
```

---

***Step 6.*** Put following method in your-view-controller & identify segue

```
	override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
		if segue.identifier == "from_home_to_popover" {
			if let myPopOverObj = segue.destinationViewController as? MyPopOverClass {
				myPopOverObj.modalPresentationStyle = .Popover
				myPopOverObj.popoverPresentationController?.delegate = self
			}
		}
	}
```

---

***Step 7.*** Put following code in your pop-over-controller under view-did-load.

```
    override func viewDidLoad() {
        super.viewDidLoad()
		self.preferredContentSize = CGSizeMake(500, 400)
    }
```

---

***Step 8.*** From some action, when you wish to dismiss pop-over, under your pop-over-controller put following code.

```
	@IBAction func btnDoneTapped(btn: UIButton) {
		self.dismissViewControllerAnimated(true, completion: nil)
	}
```

---

Example `output` is as follows.

![Example output](https://github.com/sag333ar/sag333ar.github.io/blob/master/Swift/Show%20Popover%20in%20iPhone-iPad/HowToShowPopOver-3.gif?raw=true)