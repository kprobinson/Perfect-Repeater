# Perfect Repeater

<p align="center">
    <a href="http://perfect.org/get-involved.html" target="_blank">
        <img src="http://perfect.org/assets/github/perfect_github_2_0_0.jpg" alt="Get Involed with Perfect!" width="854" />
    </a>
</p>

<p align="center">
    <a href="https://github.com/PerfectlySoft/Perfect" target="_blank">
        <img src="http://www.perfect.org/github/Perfect_GH_button_1_Star.jpg" alt="Star Perfect On Github" />
    </a>  
    <a href="http://stackoverflow.com/questions/tagged/perfect" target="_blank">
        <img src="http://www.perfect.org/github/perfect_gh_button_2_SO.jpg" alt="Stack Overflow" />
    </a>  
    <a href="https://twitter.com/perfectlysoft" target="_blank">
        <img src="http://www.perfect.org/github/Perfect_GH_button_3_twit.jpg" alt="Follow Perfect on Twitter" />
    </a>  
    <a href="http://perfect.ly" target="_blank">
        <img src="http://www.perfect.org/github/Perfect_GH_button_4_slack.jpg" alt="Join the Perfect Slack" />
    </a>
</p>

<p align="center">
    <a href="https://developer.apple.com/swift/" target="_blank">
        <img src="https://img.shields.io/badge/Swift-4.0-orange.svg?style=flat" alt="Swift 4.0">
    </a>
    <a href="https://developer.apple.com/swift/" target="_blank">
        <img src="https://img.shields.io/badge/Platforms-OS%20X%20%7C%20Linux%20-lightgray.svg?style=flat" alt="Platforms OS X | Linux">
    </a>
    <a href="http://perfect.org/licensing.html" target="_blank">
        <img src="https://img.shields.io/badge/License-Apache-lightgrey.svg?style=flat" alt="License Apache">
    </a>
    <a href="http://twitter.com/PerfectlySoft" target="_blank">
        <img src="https://img.shields.io/badge/Twitter-@PerfectlySoft-blue.svg?style=flat" alt="PerfectlySoft Twitter">
    </a>
    <a href="http://perfect.ly" target="_blank">
        <img src="http://perfect.ly/badge.svg" alt="Slack Status">
    </a>
</p>

The Perfect "Repeater" is a simple library that takes a closure and executes it at the specified interval until the closure returns false or the application is terminated.

Note that a demo is located at [https://github.com/PerfectExamples/Perfect-Repeater-Demo](https://github.com/PerfectExamples/Perfect-Repeater-Demo) that shows the operation of the library.

## Compatibility with Swift

The master branch of this project currently compiles with **Xcode 9** or the **Swift 4** toolchain on Ubuntu, and is compatible with both Perfect 2.x and 3.x

## Building

Add this project as a dependency in your Package.swift file.

``` swift
.Package(url:"https://github.com/PerfectlySoft/Perfect-Repeater.git", majorVersion: 1)
```

## Usage

Include in your file the import statement:

``` swift
import PerfectRepeater
```

The base form of executing this is:

``` swift 
Repeater.exec(timer: <Double>, callback: <Closure>)
```

To demonstrate the process of repeating a closure containing your code and optionally re-queuing:

``` swift
var opt = 1

let c = {
	() -> Bool in
	print("XXXXXX")
	return true
}
let cc = {
	() -> Bool in
	print("Hello, world! (\(opt))")
	if opt < 10 {
		opt += 1
		return true
	} else {
		print("cc exiting.")
		return false
	}
}

Repeater.exec(timer: 3.0, callback: c)
Repeater.exec(timer: 2.0, callback: cc)
```

## Further Information
For more information on the Perfect project, please visit [perfect.org](http://perfect.org).
