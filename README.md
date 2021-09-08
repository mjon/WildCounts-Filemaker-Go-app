# WildCounts Filemaker Go app

This iPhone database runs on the free FileMaker Go app. It was built with the (not free) FileMaker Pro (http://filemaker.com/) which you'll need if you want to make changes to the database.

I built the app for my own use. I use it to make date-time-stamped and geotagged observations of species in my route and site surveys or as casual notes. These observations can be text notes, audio notes, or drawings. You could reconfigure it to make observations of just about anything.

I've included screenshots so you can see what it does. At the moment I have it optimised for the screen size of my iPhone SE (the screenshots are from the older iPhone 4S version).

In my case, I enter each text observation in a shorthand format of my own design which is later expanded and translated on my computer with R scripts ODBC-connected to a Filemaker database on my computer (which I call WildCounts Hoard). I've used this set-up to log many hundreds of thousands of observations, including on my bike with the app on my iPhone connected to a bluetooth microphone on my bike helmet.

Note that you can add a separate app icon to your iPhone home screen using Apple's free Configurator app from the Mac App Store. Include the path "FMP://%7E/WildCounts" add an icon, copy the resulting mobileconfig file to your iPhone and you'll be able to click on the icon to open WildCounts via Safari.

# KNOWN ISSUES

There is sometimes a lag in the geotags on observations in FileMaker Go. This has been the case for several iterations of iOS, FileMaker Go, and different iPhones. I think this is an iPhone/iOS thing as I've seen similar lags in the geotagging of some of the photos I take with my iPhone, if data is turned off and I travel between locations.

My solution to get more accurate geotags on my observations is to run a GPS track at the same time (I use the free Cyclemeter app on my iPhone or use my Garmin GPSMAP64 GPS unit) and then use an R script to combine the observation date-time-stamps with the Cyclemeter GPX tracks.

I'm still running this on Filemaker Go 17 as I had an issue with Filemaker Go 18 stopping my audio recording when I shifted to the compass app. Since Filemaker Go 17 didn't do this, I've stuck with that.

# ATTRIBUTION

This is creative commons attribution 4.0. Do what you like with it.

Jon.Sullivan@lincoln.ac.nz

# VERSION HISTORY

Note that only 0.9.5 and now 0.9.9.9 have been uploaded to Github.

0.9.5 26 August 2017
I (finally) upgraded the app dimensions for a 4 inch iPhone screen, and made a few minor formatting improvements. No functional changes were made.

0.9.6 28 August 2017
I didn't get the screen size quite right (I was using the screen sizes appropriate for FileMaker 13 but the new FileMaker Go has slightly different menu sizes. Fixed.

0.9.7 11 February 2019
Watcher renamed to WildCounts.

0.9.9 12 April 2019
Minor change to shift “Casual observation from inside” as a Purpose across to “Stationary indoors” in Movement. WildCounts Hoard got updated as well to reflect this change.

0.9.9.1 31 January 2020
I added “Site coordinate” to the bottom of the site-curate and note-curate screens so that I can more consistently enter manual coordinates in the event that the GPS isn’t working or isn’t accurate (after exactly that happened on the past weekend).
I also added “direct sun percentage” to the weather options for Routes, Sites, and Notes.
This version of the app was first put on my iPhone on 6 Feb. 2020.

0.9.9.2 20200520
I added the field “GPS track source” to keep track of where the GPS information comes from for each route and site survey. I also removed “Partial site“ and “Partial route” from the app layouts, since I haven’t used those in a long time.

0.9.9.3 20200617
It’s raining so I did what I’ve been meaning to do for some time and added “precipitation percentage” to watcher sites and watcher routes in WildCounts and WildCounts Hoard. For longer surveys, I can now enter the percentage of time with precipitation rather than (or as well as) the duration in minutes with precipitation. Any complexities like a mix of different precipitation types in the survey still gets dealt with in the weather comments.
In the same update, I’ve cleaned up Purpose and Movement, in both WildCounts and WildCounts Hoard. Now, “Casual observation” is just “Survey”, “Stationary indoors” has been joined by “Moving indoors” (for when I’m moving between rooms), and “Exploring within 80 m” is just “Exploring” (with the assumption that the GPS track will capture my movements).

0.9.9.3 20200625
I tweaked the shorthand dashboard layout on this version to remove the old start, stop, pause on, and pause off buttons that I no longer use. I also increased the font size of the page from 13 point to 14 point. (For completeness, I retained the old layout as “shorthand dashboard (old version)” but none of the app buttons take me to that.

0.9.9.4 20200807
“External microphone” and “Timelapse” fields added to better keep track of when these are used. However, note that I’m a bit inconsistent in how I’m applying “External microphone” as I usually carry my RØDE external mic in my bag and get it out only when I need it, just like I do my monocular. So, I’m usually saying “no” for these when I’m biking, because I don’t usually use them, but that doesn’t mean that I occasionally need to get them from my bag to confirm an ID or record a song or call. In those case, the use of monocular is always included in the observation and the use of RØDE external mic is reflected in the different audio file name when I use the RØDE app.

0.9.9.5 20210108
I split my “Site coordinate” field from the “site surveys” table into “Site latitude“, “Site longitude”, and “Site GPS accuracy m” and “Site radius m”, and filled those new fields with the contents of “Site coordinate”.

0.9.9.6 20210124
I added a new field, countPeoplePresent, to site surveys and route surveys. This can be used in addition to the named Co-observers.

0.9.9.7 20210620
Months ago I changed What looked for to whatSoughtSet, and What looked forID to whatSoughtSetID, in WildCounts Hoard, but I forgot to do the same to the WildCounts app. I’ve just updated the WildCounts app. (I also had to sweep through and reimport all the WildCounts databases since February to add the correct values to whatSoughtSet and whatSoughtSetID for their sites and routes.)
I also (finally) added scripts to enter in some of the survey fields, starting with “it’s indoors” and “it’s exploring no plants no roads”.

0.9.9.8 20210822
I added the field “Continuous audio recorder” to site and route surveys, and to Watcher Hoard, to keep track of when I have an Audiomoth recording continuously at a site where I'm surveying.

0.9.9.9 20210901
I added scripts to fill in fields for “It’s running” and “It’s biking”. I also corrected a spelling error in the dropdown for “Garmin GPSMAP64” (it was “Garmin GPSMPA64”, now fixed in older observations). I also added the later model AudioMoth with soldered microphone as an option to the continuous audio recording dropdown (this is what I’m using at home in our garden, but I use a more compact and robust plain AudioMoth on my runs).
