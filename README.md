# JSH
JSH (Java SHell) is a shell designed as a replacement for BASH or other UNIX like shells. Works on Windows, Mac, and Linux, however for Windows and Mac it will populate in a directory within the users home directory location.  On Linux, the system should be run as root, and will populate itself in the root directory.  If not run as root, it will act the same as it would on Windows or Mac.

********
PLEASE NOTE
JSH is still in early development!!
In its current state its close to a quarter complete
********

# Why JSH?
JSH is lightweight, fast, and easy to work with.
It is fully extensible, with a Module framework, and a Command framework
It is cross-platform

# FAQS

Where does JSH populate?

  - JSH will create a directory "jsh" within /bin on linux that contains all commands
  - JSH will create a directory "modules" within / on linux that contains all modules
  - JSH will create a file "module.lst" that contains a list of all modules on the system
  - JSH will create a directory "JSH" in /var/log to log all errors to
  - JSH will create a directory "config" in / on linux that contains configuration files
  
Will JSH replace my current shell?
    
 - While this is the intended outcome, JSH cannot yet replace a linux shell completely
  
Is JSH Multi-Threaded?
 
 - Yes, all Commands and Modules are run in separate threads to prevent system hangups

Can Commands call Module methods?

 - Yes, commands can depend on modules
 - JSH loads commands and modules into the same scope allowing commands to refer to module methods and variables
  
# Command Creation
  
To create a Command that can be used by JSH, 

 - Extend the terra.shell.command.Command class
 - Place all runtime code within the start() method
 - Copy the compiled class file to the JSH command bin directory
 
# Module Creation

To create a Module that can be used by JSH,

  - Extend the terra.shell.modules.Module class with class named module
  - Place all pre-runtime code within the onEnable() method
    - This code will be run when the module is loaded, before it is actually run
  - Place runtime code within the run() method
  - Copy compiled files into a sub-directory of JSH's modules directory
  - Append /module.lst with the directory name containing the module files
  
  # Documentation
  
  https://einstein12345.github.io/docs/index.html
  
