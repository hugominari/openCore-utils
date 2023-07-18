# Utils for OpenCore

[OpenCore Legacy Patcher](https://dortania.github.io/OpenCore-Legacy-Patcher/)

#### Fix permissions of Microphone and Camera on macOS with openCore
#
### Get identifier of app
You will need to know the app identifier to fix the permissions:
codesign -dr - (drag and drop the app from finder)

In this example I will fix Google Chrome, so the command is this:
```
codesign -dr - /Applications/Google\ Chrome.app
```

Then find the line like this: ``identifier "com.google.Chrome"``

#
### Using the TCCPlus

Download this package:
[TCCPlus 1.0](https://github.com/jslegendre/tccplus/releases/tag/1.0)

the command to fix the permission: ``./tccplus add [resource] [identifier]``

Set the permission to execute:
```
cd ~/Downloads/ && chmod +x tccplus

./tccplus add Microphone com.google.Chrome
```
