# Configuration for macOS and iOS

Drop Config-iOS into your iOS project. Set 2Project as the project config file. Set App-Debug as the Debug config and App-Release as the Release config. You can then delete all of the settings in your project and use the external xcconfig files which are easier to manage and easier to diff.

* xcconfig files for app, framework, tests

* Project
	* 1XcodeWarnings.xcconfig
	    * imported by 2Project.xcconfig it has all of the warning flags
	* 2Project.xcconfig
	    * set 2Project as the Project xcconfig file

* App
	* App-Debug.xcconfig
	* App-Release.xcconfig
	    * Debug and Release import Shared
	    * Set Debug as the debug configuration file and Release for the release configuration
	* App-Shared.xcconfig

* xcconfig files for framework and test targets

	* Framework-Debug.xcconfig
	* Framework-Release.xcconfig
	* Framework-Shared.xcconfig
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
