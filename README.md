# Configuration for macOS and iOS

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

## info-plist

* Info.plist replacements for different targets

## Build-Phases

* Scripts to set a Run Script build phases
    * build-script
    * swiftlint-command
    * todo-fixme
    * fix-images
    * update-framework-version

## POM

* app-pom.xml