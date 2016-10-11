# AppBlocker
Block applications by their bundle identifier from launching in the Finder

![AppBlocker](https://github.com/erikberglund/AppBlocker/blob/master/AppBlockerScreenshot.png)

_Because the blocking is done by the bundle identifier, the location or name of the application bundle doesn't matter_

# Disclaimer
For true blacklisting of binary execution, look at Google's Santa project: https://github.com/google/santa

This script doesn't literally "block" the execution of an application, it gets notified when an application is being launched and sends a `SIGKILL` signal to the process.

It's a simple method to help administrators stop their users from using applications the organization has decided should not be allowed. If you have a management framework with a similar feature, you should use that instead.

# Configure Applications
 
 Add the bundle identifier for each application you wish to block to the list *blockedBundleIdentifiers*
 
 ```python
 blockedBundleIdentifiers = ['com.apple.InstallAssistant.Sierra']
 ```
 
 You can use either exact bundle identifiers or a regex pattern.
 
 If you also want to delete the application when it's launched, set **deleteBlockedApplication** to True
 
 ```python
 deleteBlockedApplication = True
 ```
 
# Configure Alert Message
 
 To disable the alert shown to users, set variable **alertUser** to False
 
  ```python
 alertUser = False
 ```
 
 To change the text shown in the alert, modify the **alertMessage** and **alertInformativeText** variables respectively.
 
 ```python
alertMessage = "The application \"{appname}\" has been blocked by IT"
alertInformativeText = "Contact your administrator for more information"
 ```
 
 To change the icon shown in the alert, modify the **alertIconPath**
 
 ```python
 alertIconPath = "/System/Library/CoreServices/CoreTypes.bundle/Contents/Resources/Actions.icns"
 ```
