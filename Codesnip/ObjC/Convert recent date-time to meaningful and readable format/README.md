###Convert recent date-time to meaningful and readable format

---

```Objective-c
+ (NSString *)stringForTimeIntervalSinceCreated:(NSDate *)dateTime serverTime:(NSDate *)serverDateTime{
  NSInteger MinInterval;
  NSInteger HourInterval;
  NSInteger DayInterval;
  NSInteger DayModules;
    
  NSInteger interval = abs((NSInteger)[dateTime timeIntervalSinceDate:serverDateTime]);
  if(interval >= 86400) {
    DayInterval  = interval/86400;
    DayModules = interval%86400;
    if(DayModules!=0) {
      if(DayModules>=3600){
        //HourInterval=DayModules/3600;
        return [NSString stringWithFormat:@"%i days", DayInterval];
      } else {
        if(DayModules>=60){
          //MinInterval=DayModules/60;
          return [NSString stringWithFormat:@"%i days", DayInterval];
        } else {
          return [NSString stringWithFormat:@"%i days", DayInterval];
        }
      }
    } else {
      return [NSString stringWithFormat:@"%i days", DayInterval];
    }
  } else {
    if(interval>=3600) {
      HourInterval= interval/3600;
      return [NSString stringWithFormat:@"%i hours", HourInterval];
    } else if(interval>=60){
      MinInterval = interval/60;
      return [NSString stringWithFormat:@"%i minutes", MinInterval];
    } else {
      return [NSString stringWithFormat:@"%i Sec", interval];
    }
  }
}
```

---

Example Outputs

* Last seen 5 days ago
* Last seen 3 mins ago
* Last seen 2 seconds ago
* Profile picture udpated 3 weeks ago
