Cordova Plugin for Opentok iOS SDK
===

Weave video chat into your web ( and now mobile! ) application.

## Step 1. Install / create Cordova app
<http://phonegap.com/start/>
> Make sure 'use automatic reference counting' is **not** selected when you create the project.  
> Before you proceed, make sure you have run the application and 'www' is linked in your project. If not, please look at the Cordova docs again!   
![www](http://songz.github.com/phonegap-plugin-opentok/images/www.png)

## Step 2. Install Opentok Framework
The Easiest way is to do this: take a working Opentok app and clone Opentok Framework and all the dependencies to your project.  Here's how to do that.

1. Clone from <https://github.com/opentok/OpenTok-iOS-Hello-World.git> and open the Hello-World xcode project.  
Be sure to git clone with --recursive to grab the required OpenTok iOS SDK submodule!  
`git clone --recursive https://github.com/opentok/OpenTok-iOS-Hello-World.git`

2. Drag the Opentok.framework and all dependencies from Hello-World in xcode into your project's *Frameworks* folder.   
Make sure `Copy items into destination group's folder` is **not** selected  
![framework](http://songz.github.com/phonegap-plugin-opentok/images/frameworks.png)

3. click on your project in **Project Manager** and select **Build Settings**  

> Make sure **Standard (armv7)** is selected for **Architectures**  
> Make sure **armv7** is the ONLY option selected for **Valid Architectures**   
>> Sometimes xcode doesn't update immediately. Click outside on the white box and your change will appear!

![architecture](http://songz.github.com/phonegap-plugin-opentok/images/arch.png)  

**Note** When testing, please run your app in your device, **NOT** the simulator. Opentok SDK require access to camera, and simulator does not have camera and will therefore give you errors. 

## Step 3. Install Opentok Phonegap Plugin
1. Clone from <https://github.com/songz/phonegap-plugin-opentok>

2. Copy `OpentokPlugin.h`, `OpentokPlugin.m`, `OpentokStreamInfo.h`, and `OpentokStreamInfo.h` into your **Classes** folder  
> Make sure `Copy items into destination group's folder` **is selected**  
![ios](http://songz.github.com/phonegap-plugin-opentok/images/iosplugin.png)

3. Copy `Opentok.iOS.js` into your `www` folder, the file will automatically appear in your xcode project manager  
![js](http://songz.github.com/phonegap-plugin-opentok/images/jsplugin.png)

4. In project manager, under `Supporting Files` folder, select `Cordova.plist`
> Under `Plugins`, add a new entry: `Tokbox`, `OpentokPlugin`  
>> Make sure your drag your entry to the bottom. Sometimes, the entry does not update immediately. Click on another file, then click on plist again.  

> Under `ExternalHosts`, add a new entry with the value *.  
![plist](http://songz.github.com/phonegap-plugin-opentok/images/cplist.png) 


### Done!

---

## Getting Started on your Project:
All your editing will be done in your www folder.

To use the opentok library, make sure you include **Opentok.iOS.js** file in your HTML document.  
` <script type="text/javascript" charset="utf-8" src="Opentok.iOS.js"></script>`

For smoother experience with video, you should prevent dragging. Uncomment the following lines in the HTML:

    function preventBehavior(e) 
    { 
      e.preventDefault(); 
    };
    document.addEventListener("touchmove", preventBehavior, false);

All code should be written in `onDeviceReady` function because it is executed after all the devices/libraries DOM has loaded.

	function onDeviceReady()
	{
		// do your thing!
	}

---

## Quick Tutorial:
Go through our [15 minute tutorial](http://www.tokbox.com/opentok/api/documentation/gettingstarted)! After that, try implementing the same thing on your cordova app.   
Included in the repo is a sample.html that you can copy/paste that is modeled after the getting started tutorial. Have Fun!

----

License
===

Copyright (c) 2012 TokBox, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:


The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

The software complies with Terms of Service for the OpenTok platform described in http://www.tokbox.com/termsofservice

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
