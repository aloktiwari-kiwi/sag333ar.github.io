###Parse JSON Data from supplied file


```
// a string which will hold path of file named `IndiaPost.json`
let str:String? = NSBundle.mainBundle().pathForResource("IndiaPost", ofType: "json")

// load file
let data:NSData? = NSData(contentsOfFile: str!)

// try to parse the data in form of json		
do {
  // if json-data parsed
  let jsonData:AnyObject? = try NSJSONSerialization.JSONObjectWithData
                              (data!, options: NSJSONReadingOptions.AllowFragments)

  // and if parsed json-data is an array
  if let arrayData:NSArray = jsonData as? NSArray {

    // use your json-array - here I'm setting it to property named `arrayOfLeftMenuItems`
    self.arrayOfLeftMenuItems = arrayData
  }
} catch {
  // handle exception. Here, I'm just logging the error
  print(error)
}
```
