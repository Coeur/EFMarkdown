# EFMarkdown

[![CI Status](http://img.shields.io/travis/EyreFree/EFMarkdown.svg?style=flat)](https://travis-ci.org/EyreFree/EFMarkdown)
[![Version](https://img.shields.io/cocoapods/v/EFMarkdown.svg?style=flat)](http://cocoapods.org/pods/EFMarkdown)
[![License](https://img.shields.io/cocoapods/l/EFMarkdown.svg?style=flat)](http://cocoapods.org/pods/EFMarkdown)
[![Platform](https://img.shields.io/cocoapods/p/EFMarkdown.svg?style=flat)](http://cocoapods.org/pods/EFMarkdown)

A CocoaPods wrapper of [cmark](https://github.com/commonmark/cmark) in Swift, based on [EFCMark](https://github.com/EyreFree/EFCMark), inspired by [markdown](https://github.com/vapor-community/markdown) and [Markoff](https://github.com/thoughtbot/Markoff).

## Overview

![](https://raw.githubusercontent.com/EyreFree/EFMarkdown/master/assets/sample1.png)|![](https://raw.githubusercontent.com/EyreFree/EFMarkdown/master/assets/sample2.png)|![](https://raw.githubusercontent.com/EyreFree/EFMarkdown/master/assets/sample3.png)|![](https://raw.githubusercontent.com/EyreFree/EFMarkdown/master/assets/sample4.png)  
:---------------------:|:---------------------:|:---------------------:|:---------------------:

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

- XCode 8.0+
- Swift 3.0+

## Installation

EFMarkdown is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "EFMarkdown"
```

## Usage

### 1. Markdown -> HTML

You can use `EFMarkdown` to make Markdown string to HTML string easily:

```swift
let markdown = "# Hello"
var html = ""
do {
    html = try EFMarkdown().markdownToHTML(markdown, options: EFMarkdownOptions.safe)
    print(html) // This will return "<h1>Hello</h1>\n"
} catch let error as NSError {
    print ("Error: \(error.domain)")
}
```

### 2. View Markdown

You can use `EFMarkdownView` to make a preview of Markdown:

```swift
let screenSize = UIScreen.main.bounds
let markView = EFMarkdownView()
markView.frame = CGRect(x: 0, y: 20, width: screenSize.width, height: screenSize.height - 20)
self.view.addSubview(markView)
markView.load(markdown: "# Hello", options: [.default])
```

### Options

You can pass different options to the underlying `cmark` library. By default `safe` is passed.

The available options are:

* default
* sourcePos
* hardBreaks
* safe
* noBreaks
* validateUTF8
* smart
* githubPreLang
* liberalHtmlTag

For more information on the available options, see [`cmark`](https://github.com/github/cmark).

## Author

EyreFree, eyrefree@eyrefree.org

## License

![](https://www.gnu.org/graphics/gplv3-127x51.png)

EFMarkdown is available under the GPLv3 license. See the LICENSE file for more info.
