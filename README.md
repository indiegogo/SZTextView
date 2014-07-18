# SZTextView 

[![Build Status](https://travis-ci.org/glaszig/SZTextView.svg?branch=master)](https://travis-ci.org/glaszig/SZTextView)
[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/glaszig/sztextview/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

A drop-in UITextView replacement which gives you: a placeholder.  
Technically it differs from other solutions in that it tries to work like UITextField's private `_placeholderLabel` so you should not suffer ugly glitches like jumping text views or loads of custom drawing code.

## Requirements

Your iOS project. (Tested on iOS versions 5.0, 6.1, 7.0 and 7.1)

> **Note**: This is ARC-enabled code. You'll need Xcode 4.2 and OS X 10.6, at least.  
> **Note**: To run the tests you'll need Xcode 5 with XCTest.

## Installation

Either clone this repo and add the project to your Xcode workspace or use [CocoaPods](http://cocoapods.org).

## Usage

```objc
SZTextView *textView = [SZTextView new];
textView.placeholder = @"Enter lorem ipsum here";
textView.placeholderTextColor = [UIColor lightGrayColor];
textView.font = [UIFont fontWithName:@"HelveticaNeue-Light" size:18.0];
```

Analogously you can use the `attributedPlaceholder` property to set a fancy `NSAttributedString` as the placeholder:

```objc
NSMutableAttributedString *placeholder = [[NSMutableAttributedString alloc] initWithString:@"Enter lorem ipsum here"];
[placeholder addAttribute:NSForegroundColorAttributeName value:[UIColor redColor] range:NSMakeRange(0,2)];
[placeholder addAttribute:NSForegroundColorAttributeName value:[UIColor greenColor] range:NSMakeRange(2,4)];
[placeholder addAttribute:NSForegroundColorAttributeName value:[UIColor blueColor] range:NSMakeRange(6,4)];

textView.attributedPlaceholder = placeholder;
```

Both properties `placeholder` and `attributedPlaceholder` are made to stay in sync.
If you set an `attributedPlaceholder` and afterwards set `placeholder` to something else, the set text gets copied to the `attributedPlaceholder` while trying to keep the original text attributes.  
Also, `placeholder` will be set to `attributedPlaceholder.string` when using the `attributedPlaceholder` setter.

A simple demo and a few unit tests are included.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

# License

Published under the [MIT license](http://opensource.org/licenses/MIT).

**Note**

I've developed this component for [Cocktailicious](http://www.cocktailiciousapp.com). You should check it out \*shamelessplug\*.  
Please let me now if and how you use this component. I'm curious.

