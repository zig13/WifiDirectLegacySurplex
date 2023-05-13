# Wi-Fi Direct for Hosting Surplex

This is a copy of the Windows sample that allows 'soft AP' support on Windows 10 through the WiFi Direct interfaces.
The sample code sets a random password every time it is ran which makes it not so useful for enabling a connection to a "dumb" device such as Surplex VR tracking shoes.

This version is modified to set the SSID to "surplex-io" and the passcode to "abcd1234" which are the defaults in the Surplex firmware.
Simply run the .exe, type start into the console, and hit enter to generate a Wifi network for your shoes to connect to.
When each connect you should get a notification in the window so you know it has worked.

You will still need to find out what IP address is assigned to your PC on the network. For me it was 192.168.137.1 and that might be standard.

## Sample Info

The sample is organized up into the following files:

- **WlanHostedNetworkWinRT.cpp/h** : This contains the code that uses the API in the WlanHostedNetworkHelper class. There is also a IWlanHostedNetworkListener interface that can be used by another application to receive notifications from events in the Wi-Fi Direct API. This part may be used as is or modified to fit your application needs.
- **SimpleConsole.cpp/h** : This is a simple console using iostreams to take command line input and start or stop the Wi-Fi Direct legacy AP. It implements the IWlanHostedNetworkListener to handle receiving messages from the API.
- **WiFiDirectLegacyAPDemo.cpp** : Main entry point that starts the simple console.

**Note** This sample requires Windows 10 to execute, as it uses new API's. It also requires a Wi-Fi Card and Driver that supports Wi-Fi Direct.

To obtain information about Windows 10, go to [Windows 10](http://go.microsoft.com/fwlink/?LinkID=532421)

To obtain information about Microsoft Visual Studio 2015 and the tools for developing Windows apps, go to [Visual Studio 2015](http://go.microsoft.com/fwlink/?LinkID=532422)

## Credit
Credit to Motomotes on StackOverflow who basically provided the code I needed.
I only edited the consolefile to correctly give the now hardcoded SSID and passcode

## Related topics

### Reference

[Wi-Fi Direct WinRT API](https://msdn.microsoft.com/en-us/library/windows.devices.wifidirect.aspx)

[WlanHostedNetwork* API (deprecated in Windows 10)](https://msdn.microsoft.com/en-us/library/windows/desktop/dd815243.aspx)

## System requirements

**Client:** Windows 10 Insider Preview

**Server:** Windows 10 Insider Preview

**Phone:**  Windows 10 Insider Preview

## Build the sample

1. Start Microsoft Visual Studio 2015 and select **File** \> **Open** \> **Project/Solution**.
2. Go to the directory to which you unzipped the sample. Double-click the Visual Studio 2015 Solution (.sln) file. 
3. Press Ctrl+Shift+B, or select **Build** \> **Build Solution**. 
