### Insert following method to play a video within a UIView

---

In this case, 'DrAryaStartup.mp4' is the video which is part of Application.
Here, I'm going to play video in an UIImageView named 'imgV'

```Objective-c
- (void)playVideo {
    NSString *videoPath = [[NSBundle mainBundle] pathForResource:@"DrAryaStartup" ofType:@"mp4"];
    NSURL *videoURL = [NSURL fileURLWithPath:videoPath];
    
    AVPlayer *player = [AVPlayer playerWithURL:videoURL];
    AVPlayerLayer *layer = [AVPlayerLayer layer];
    [layer setPlayer:player];
    [layer setFrame:self.imgV.bounds];
    [layer setBackgroundColor:[UIColor clearColor].CGColor];
    [layer setVideoGravity:AVLayerVideoGravityResizeAspect];
    
    [self.imgV.layer addSublayer:layer];
    
    [player play];
}
```

---