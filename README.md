# KIF-bootcamp

This bootcamp serves as an introduction point into the KIF framework and other testing tools for iOS. It covers a majority of the common scenarios one might encounter while developing tests for iOS applications.

Fork this repo and request evaluation from ETT members experienced in developing KIF tests.

Software:

- Xcode 7.x.x (Try to remain consistent with the version that the development team is using)
- Cocoapods
- KIF
- Nocilla


#KIF Basics

## Task #0: Setup

##### Useful material and links: 

- [Objective-C Basics] (http://tryobjectivec.codeschool.com/levels/1)
- [Xcode Cheat Sheet] (http://www.git-tower.com/blog/xcode-cheat-sheet)
- [Cocoapods] (https://cocoapods.org/)
- [KIF Framework README] (https://github.com/kif-framework/KIF)


##### Objective:
1. Set up KIF framework on the sample app
2. Add a test that launches the app and waits (use [tester waitForTimeInterval:5] to wait)

##### Description:

If you are new to Objective-C, I would recommend running through the Objective-C Basics course on Codeschool. It's a quick and gamified way to familiarize yourself with the basics of Objective-C syntax. If you are familiar with Java/C most of the underlying concepts should not be new to you.

Follow the installation instructions from the KIF Framework README. We will be using Cocoapods to install KIF, so make sure you have the latest stable version installed on your machine. 

 **NOTE:** You should add your test target in the xcodeproj file, and then open xcworkspace only after you have installed the pod. Additionally to run the project on a simulator below 9.1, you will have to change "Deployment Target" to something lower (e.g. 8.0)


In order to complete this task you will need to create your first test class and write a simple test.

## Task #1: Exploring the KIF API

##### Useful material and links: 

- [iOS Accessibility Inspector] (https://developer.apple.com/library/ios/technotes/TestingAccessibilityOfiOSApps/TestAccessibilityiniOSSimulatorwithAccessibilityInspector/TestAccessibilityiniOSSimulatorwithAccessibilityInspector.html) 
- [KIF Tests - Source code examples] (https://github.com/kif-framework/KIF/tree/master/KIF%20Tests)

##### Objective:
Add a test that selects a Pivot from the table view, and makes sure their job title and projects leading value is displayed in the detail view.

##### Description:

In order to complete this task you will need to create a new test class, and write a test that combines two of the core functions of KIF; waiting for a view to be visible and tapping on a view.

## Task #2: Adding accessibility labels

##### Useful material and links: 

- [KIF Tests - Source code examples] (https://github.com/kif-framework/KIF/tree/master/KIF%20Tests)

##### Objective:
1. Add an accessibility label to the table view that contains the ETT Pivots
2. Add an accessibility label to the text entry field in the details view
3. Use your newly created accessibility labels to write a new test, one that loops through the the rows and taps on each and then enters some text into the detail view's text field.

##### Description:

In order to complete this task you will need to figure out where in the source code to add your accessibility labels. Hint: A good starting point is to look where other screen elements are being styled/initialized

Once you have added accessibility labels you can confirm your additions by using the accessibility inspector. Use some new KIF functions in order to select specific rows in the table view, and to enter text into your text field.

## Task #3: References to objects and using their methods

##### Objective:
1. Add tests that utilize reference to existing objects and use their methods

##### Description:
You can get a pointer to the original object simply by casting your waits to the desired object (e.g. (UIView *)[tester waitForViewWithAccessibilityLabel:@"SomeView"]). You can assign this to a variable and then manipulate the object directly using its methods. 

In order to complete this task, get a reference to the tableView object, and initiate a selection directly using the delegate method tableView:didSelectRowAtIndexPath:.


## Task #4: Before and After your tests

##### Useful material and links: 

- [KIFTestCase.h] (https://github.com/kif-framework/KIF/blob/master/Classes/KIFTestCase.h)

##### Objective:
1. Experiment with the beforeAll, beforeEach, afterEach, and afterAll methods

##### Description:

Get used to using these methods to peform tasks at different points in your code between tests.

In order to complete this task, create a test class with several tests in it and utilize NSLog to print out debug output showing the use of each function. Perform actual test steps in these methods to set up, and reset state in between your tests.

## Task #5: Stubbing network requests

##### Useful material and links: 

- [Nocilla] (https://github.com/luisobo/Nocilla)
- [Charles Proxy on the iOS Simulator] (https://www.charlesproxy.com/documentation/faqs/ssl-connections-from-within-iphone-applications/)

##### Objective:
1. Install Nocilla on the bootcamp app
2. Use Nocilla to stub the network request being used to fetch ETT Pivots and give them new job titles

##### Description:

Get used to Nocilla and all the different ways you can stub network requests. You can use Charles Proxy to intercept the content of the network calls from the app, and edit it for your stub.

In order to complete this task, create a test class that makes use of Nocilla to stub new values in for ETT Pivots, and verifies them using the skills you've learned up until this point.
