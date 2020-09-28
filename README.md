# PhilipsHue-PSModule
This Module allows you to detect a Philips Hue Bridge in your Network, currently you can connect, create new user and get all lights that are installed in your environment.

It's based on the https://developers.meethue.com/ API Developer Guide Version 1.0

The first thing you need to do is, detect your Philips Hue Bridge with the get-PHBridge cmdlet.

I'm using the supported UPnPDeviceFinder to detect the Bridge
After this step i store the Information from http://YourPhilipsHueBridgeIP/description.xml
in a PS-Object. This cmdlet has several switches like -IP or -SerialNumber, see Examples...

It also includes an Error handler if no Device with the ModelName '*Philips hue bridge*' was found.
It's recommended to store the Information about your Hue Bridge, because the detection took a while.
The Module offers an easy way to store User Login Information. Use 'get-PHBridge -StoreConfig' to store it in the User Profil of the current user $($env:USERPROFILE + '\PhilipsHueBridge.xml').
You can access the stored user Login Information via 'get-PHBConfig' for further use.
