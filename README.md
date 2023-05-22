# VCV Rack 2 modules
Modules are developed under macOS with the help of [Erb Eurorack-Blocks](https://github.com/ohmtech-rdi/eurorack-blocks). I'll do my best to make them Windows and Linux friendly...

## Installation

Copy and past the module directory into the default VCV Rack 2 plugins location wich is /Documents/Rack2/plugins/ by default under macOS.

## Additional steps

As you maybe know, code has to be signed to be distributed and run on macOS and every Apple products. Unfortunately, I'm not part of the Apple developer program, hence I can't sign my code. But, thanks to [Raphaël Dingé from Erb](https://github.com/ohmtech-rdi/eurorack-blocks) who pointed me to the solution, you can run VCV Rack 2 modules if you re-sign them with your OS device certificate and "allow downloaded apps" to run on your device.

Once the module is copied to the default VCV Rack2 plugins location, this alert pops up the first time you launch VCV :

![Screenshot of the security alert raised by VCV Rack2](/pics/SecurityAlert.png)

As mentionned earlier, this is a normal behavior, the code is not signed.
Follow this procedure:
1. Re-sign the code:

For instance, with the FMEinheit module, type those lines in your favorite terminal :
```
cd ~/Documents/Rack2/plugins/FMEinheit
codesign --force -s - plugin.dylib
```
2. Add a security exception for plugin.dylib :

Go to System preferences > Security & Privacy. You'll notice this message :
“plugin.dylib can’t be opened because Apple cannot check it for malicious software.”
You just have to "Allow it anyway".

Launch VCV Rack 2 and you now have another security alert in wich you can "Open" the "plugin.dylib".

That's all! :+1:

All details about modules are available here: https://omsinserial.blogspot.com
