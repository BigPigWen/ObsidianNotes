# From a technical point of view
+ Qt Creator is a plugin loader with many plugins
+ Plugins can depend in and interact with each other
+ Endless possibilities (more or less)
# From a practical point point of view
+ Creating a plugin is not hard
+ Maintaining and distributing a plugin can be challenging
+ Qt Creator is released under GPLv3,but it's more relaxed with plugins
# Plugin structure
 ## What you need
 + A plugin class
 # Optionally
 + Some way to handle setting
 + An options page
 + A widget for the options page
# plugin life cycle
## startup
All plugins are put in a loading queue according to their dependencies
+ `plugin()` constructor called following queue order
+ `initialize()` called following queue order - everything that requires dependencies can be done here
+ `extensionsInitialized()` called in reverse queue order
+ `Core::ICore` sends signal `coreAboutToOpen()`
Qt Creator UI is shown
+ `Core::ICore` sends signal `coreOpened()`
+ `delayedInitialize()` called in reverse queue order - This is for non critical initialization to minimize loading time of Qt Creator
+ `PluginManager` sends the `initializationDone()` signal
## shutdown
+ `Core::ICore` sends the `coreAboutToClose()` signal
+ `aboutToShutdown()` called following queue order
  + Returns `SynchronousShutdown` to notify termination
  + Returns `AsynchronousShutdown` to make Qt Creator wait until the signal `asynchronousShutdownFinished()`
+ `~plugin()` destructor called in reverse queue order
# Setting up
## Download and install
+ Qt Creator
+ Qt (including Qt Script)
## Clone and build
+ Qt Creator code
> git clone --recursive https://github.com/qt-creator/qt-creator.git
> git clone --recursive https://code.qt.io/qt-creator/qt-creator.git
  
+ Remember to checkout a branch before building
+ Make sure your compiler is compatible with the one used for building Qt Creator
+ I recommend a debug and a release build
# Creating
## Creating a plugin
File > New File or Project > Library > Qt Creator Plugin
![[images/Pasted image 20240822110018.png]]
## Meta data
![[images/Pasted image 20240822110857.png]]
+ Deploy into:
  + Qt Creator build - for your build
  + Local user setting - system availability
## How can we extend that?
### More features
+ Better time handling (consider inactivity)
+ Show different messages at different times (intervals or absolute)
+ Allow to accept/cancel notification
+ Track usage (session length, session times, user response, etc...)
+ Play sounds
+ ...
### More options
+ Customize message (s)
+ Customize sounds
+ ...