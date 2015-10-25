## Contents ##

  * [Introduction](#Introduction.md)
  * [Requirements](#Requirements.md)
  * [Installing FireShot](#Installing_FireShot.md)
  * [Getting the library](#Getting_the_library.md)
  * [Embedding](#Embedding.md)
  * [Examples](#Examples.md)


## Introduction ##

This page describes how to use FireShot API at your web pages.

## Requirements ##

To be able taking web page captures using javascript, the following stuff should be installed and set up:

  1. Mozilla Firefox 2 or above (http://getfirefox.com)
  1. FireShot addon (v. 0.91 and higher) for Firefox (http://screenshot-program.com/fireshot)

## Installing FireShot ##

FireShot can be installed from FireShot's homepage at Mozilla. You need to open [this link](https://addons.mozilla.org/en-US/firefox/addon/5648) in Firefox browser and click "Add to Firefox" button. The installation should start. After installation completed please restart Firefox and make sure you're seeing the red button "S" at the top right corner:



![http://screenshot-program.com/images/tool_button_fx.gif](http://screenshot-program.com/images/tool_button_fx.gif)

## Getting the library ##

The library can be downloaded from http://screenshot-program.com/dloads/fsapi.js


## Embedding ##

Embedding is quick and simple. First of all, unpack the library script **fsapi.js** to the place you'll be using it from.

At the `<HEAD>` section of the web page add the following lines:

```
//The global variable FireShotAPI will be declared.
<script type="text/javascript" src="fsapi.js"></script>
```

Now you can launch FireShot's functions. The following methods are available:

```
FireShotAPI.editPage(Entire);   // Capture web page (Entire = true for capturing the web page entirely) and *edit*
FireShotAPI.savePage(Entire);   // Capture web page and *save to disk*
FireShotAPI.copyPage(Entire);   // Capture web page and *copy to clipboard*
FireShotAPI.emailPage(Entire);  // Capture web page and *EMail*
FireShotAPI.exportPage(Entire); // Capture web page and *open it in a third-party editor*
FireShotAPI.uploadPage(Entire); // Capture web page and *upload to free image hosting*
FireShotAPI.printPage(Entire);  // Capture web page and *print*

FireShotAPI.isAvailable();      // Check silently whether the addon is available at the client's PC, returns *true* if everything is OK. Otherwise returns *false*.

FireShotAPI.checkAvailability() // Check whether the addon is available and display the message if required
```

For example, let it be a button that uploads entire web page to free image hosting:

```
<input type="button" onClick="FireShotAPI.uploadPage(true)" value="Capture and Upload">
```

Or a simple link that sends the visible part of the page via e-mail:

```
<a href="#" onClick="FireShotAPI.emailPage(false); return false">Send visible part via e-mail</a>
```

## Examples ##

The example below sums up the information stated above:

```
<html>

<head>
<script type="text/javascript" src="fsapi.js"> </script>
</head>

<body onload="FireShotAPI.checkAvailability()">
<input type="button" onClick="FireShotAPI.uploadPage(true)" value="Capture and Upload this Page">
</body>

</html>

```

A more detailed example is available at http://screenshot-program.com/fireshot/api_demo.php