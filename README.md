KSPhotoBrowser
==============
[![License MIT](https://img.shields.io/badge/license-MIT-green.svg?style=flat)](https://raw.githubusercontent.com/skx926/KSPhotoBrowser/master/LICENSE)&nbsp;
[![CocoaPods](http://img.shields.io/cocoapods/v/KSPhotoBrowser.svg?style=flat)](http://cocoapods.org/?q=KSPhotoBrowser)&nbsp;
[![CocoaPods](http://img.shields.io/cocoapods/p/KSPhotoBrowser.svg?style=flat)](http://cocoapods.org/?q=KSPhotoBrowser)&nbsp;
[![Support](https://img.shields.io/badge/support-iOS%208.0%2B%20-blue.svg?style=flat)](https://www.apple.com/nl/ios/)&nbsp;

### A beautiful photo browser with interactive dismissal animation.

![Rotation~](https://raw.github.com/skx926/KSPhotoBrowser/master/Demo/Images/Rotation.gif)<br>
![Blur~](https://raw.github.com/skx926/KSPhotoBrowser/master/Demo/Images/Blur.gif)<br>
![Scale~](https://raw.github.com/skx926/KSPhotoBrowser/master/Demo/Images/Scale.gif)


Features
==============
- 4 different interactive dismissal animations(Rotation, Scale, Slide).
- 3 different background styles(Blur Photo, Blur, Black).
- 2 different loading styles(Determinate, Indeterminate).
- 2 different pager styles(Dot, Text).
- Support bounce animation.
- Optimized for image which has a very large height.
- Can display one or more images by providing either image urls or UIImage objects.

### Follow-up
- Support Landscape orientation browse.
- Support video browse.


Usage
==============
### Display images from urls
```objc
NSArray *urls = @[@"http://ww4.sinaimg.cn/bmiddle/a15bd3a5jw1f12r9ku6wjj20u00mhn22.jpg",
                  @"http://ww2.sinaimg.cn/bmiddle/a15bd3a5jw1f01hkxyjhej20u00jzacj.jpg"];
NSMutableArray *items = @[].mutableCopy;
for (int i = 0; i < urls.count; i++) {
    // Get the large image url
    NSString *url = [urls[i] stringByReplacingOccurrencesOfString:@"bmiddle" withString:@"large"];
    UIImageView *imageView = _imageViews[i];
    KSPhotoItem *item = [KSPhotoItem itemWithSourceView:imageView imageUrl:[NSURL URLWithString:url]];
    [items addObject:item];
}
KSPhotoBrowser *browser = [KSPhotoBrowser browserWithPhotoItems:items selectedIndex:0];
[browser showFromViewController:self];
```

### Display images from UIImage objects
```objc
NSArray *names = @[@"a.jpg", @"b.jpg"];
NSMutableArray *items = @[].mutableCopy;
for (int i = 0; i < names.count; i++) {
    UIImageView *imageView = _imageViews[i];
    KSPhotoItem *item = [KSPhotoItem itemWithSourceView:imageView image:[UIImage imageNamed:names[i]]];
    [items addObject:item];
}
KSPhotoBrowser *browser = [KSPhotoBrowser browserWithPhotoItems:items selectedIndex:0];
[browser showFromViewController:self];
```

Installation
==============
### Cocoapods
1. Update cocoapods to the latest version.
2. Add `pod 'KSPhotoBrowser'` to your Podfile.
3. Run `pod install` or `pod update`.
4. Import `KSPhotoBrowser.h`.


### Manually
1. Download all the files of KSPhotoBrowser and add source files to your project.
2. Manually install [YYWebImage](https://github.com/ibireme/YYWebImage) to your project.
3. Import `KSPhotoBrowser.h`.


Requirements
==============
This library requires `iOS 8.0+` and `Xcode 8.0+`.


License
==============
KSPhotoBrowser is provided under the MIT license. See LICENSE file for details.


中文介绍
==============
[查看中文介绍](http://skx926.com/2017/01/04/ksphotobrowser/)
