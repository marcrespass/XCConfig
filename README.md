# Xcode configuration files for macOS and iOS

See:
* [The Unofficial Guide to xcconfig files](https://pewpewthespells.com/blog/xcconfig_guide.html)
* [Overusing Xcode Targets Misses the Mark](https://tworingsoft.com/blog/2018/05/08/overusing-xcode-targets-misses-the-mark.html)
* [Conditional Compilation, Part 2: Including and Excluding Source Files](https://davedelong.com/blog/2018/07/25/conditional-compilation-in-swift-part-2/)

1. Drop Config-iOS into your iOS project.
2. Set 2Project-Debug as the project Debug config file and 2Project-Release as the project Release config file
3. Set App-Debug as the app target's Debug config and App-Release as the app target's Release config.
    * You can then delete all of the settings in your project and use the external xcconfig files which are easier to manage and easier to diff.

[BuildSettingExtractor](https://github.com/dempseyatgithub/BuildSettingExtractor) makes it easy to extract the settings of your current project and setup configuration files to replace the Xcode project settings.

* xcconfig files for app, framework, tests. The *-Debug and *-Release files import their shared file which imports 1XcodeWarnings.xcconfig
* the files are named this way so that they sort well by name

* Project
	* 1XcodeWarnings.xcconfig
	    * imported by 2Project.xcconfig it has all of the warning flags
	    * Special thanks to Jon Reid for [XcodeWarnings](https://github.com/jonreid/XcodeWarnings)
	* 2Project-Debug.xcconfig
	    * set 2Project as the Project's Debug configuration file
	* 2Project-Release.xcconfig
	    * set 2Project as the Project's Release configuration file

* App
	* App-Debug.xcconfig
	* App-Release.xcconfig
	* App-Shared.xcconfig

* Framework

	* Framework-Debug.xcconfig
	* Framework-Release.xcconfig
	* Framework-Shared.xcconfig

* Tests
	* Tests-Debug.xcconfig
	* Tests-Release.xcconfig
	* Tests-Shared.xcconfig

## Build-Phases

* Scripts to set a Run Script build phases
    * build-script
        * runs on release builds, sets CFBundleVersion according to git
    * swiftlint-command
        * run SwiftLint
    * todo-fixme
        * adds TODO and FIXME to obj-c projects
