# AppBlocker
Block applications by their bundle identifier from launching in the Finder

![AppBlocker](https://github.com/erikberglund/AppBlocker/blob/master/AppBlockerScreenshot.png)

_As the blocking is done by the bundle identifier, the location or name of the application bundle doesn't matter_

# Disclaimer
This script doesn't literally "block" the execution of an application, it just gets notified when an application is about to be launched, and sends a SIGKILL to the process being launched.

It's a simple method to help administrators stop their users from using applications the organization has decided should not be allowed. If you have a management framework with a similar feature, you should use that instead.

For more powerful blacklisting of binary execution, look at Google's Santa project: https://github.com/google/santa

# Configure Applications
 
 Add the bundle identifier for each application you wish to block to the list *blockedBundleIdentifiers*
 
 ```python
 blockedBundleIdentifiers = ['com.apple.InstallAssistant.Sierra']
 ```
 
 You can use either exact bundle identifiers or a regex pattern.
 
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
 
 Changing icon for the alert is not currently in the script, but could easily be added when creating the alert [#L55](https://github.com/erikberglund/AppBlocker/blob/master/AppBlocker.py#L55).
