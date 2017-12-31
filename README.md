# WATCHER Filemaker Go app

This iPhone database runs on the free FileMaker Go app. It was built with the (not free) FileMaker Pro (http://filemaker.com/) which you'll need if you want to make changes to the database.

I built the app for my own use. I use it to make date-time-stamped and geotagged observations of species in my route and site surveys or as casual notes. These observations can be text notes, audio notes, or drawings. You could reconfigure it to make observations of just about anything.

I've included screenshots so you can see what it does. At the moment I have it optimised for the screen size of my iPhone SE (the screenshots are from the older iPhone 4S version).

In my case, I enter each text observation in a shorthand format of my own design which is later expanded and translated on my computer with R scripts ODBC-connected to a Filemaker database on my computer (which I call Watcher Hoard). I've used this set-up to log hundreds of thousands of observations, including on my bike with the app on my iPhone connected to a bluetooth microphone on my bike helmet.

Note that you can add a separate app icon to your iPhone home screen using Apple's free Configurator app from the Mac App Store. Include the path "FMP://%7E/Watcher" add an icon, copy the resulting mobileconfig file to your iPhone and you'll be able to click on the icon to open Watcher via Safari.

#KNOWN ISSUES

There is sometimes a lag in the geotags on observations in FileMaker Go. This has been the case for several iterations of iOS, FileMaker Go, and different iPhones. I think this is an iPhone/iOS thing as I've seen similar lags in the geotagging of some of the photos I take with my iPhone, if data is turned off and I travel between locations.

My solution to get more accurate geotags on my observations is to run a GPS track at the same time (I use the free Cyclemeter app) and then use an R script to combine the observation date-time-stamps with the Cyclemeter GPX tracks.

#ATTRIBUTION

This is creative commons attribution 4.0. Do what you like with it.

Jon.Sullivan@lincoln.ac.nz
