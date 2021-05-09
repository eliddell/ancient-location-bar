# ancient-location-bar
Port of the Firefox XUL extension Old Location Bar to Pale Moon

## What it's for

Making the Pale Moon location bar behave more like the one from Firefox 2.

Specifically, Ancient Location Bar provides a UI for some obscure settings related 
to searching history entries and such from the location bar that are otherwise hidden 
away in about:config.  It also offers some cosmetic tweaks to the location bar.

## Changes and dropped features

First of all, if you see something in the Settings window, *it works*.  I
tested everything, and fixed a couple of the cosmetic features.

Unfortunately, the differences between Pale Moon and the very old versions of
Firefox for which Old Location Bar was first created has made some functionality
difficult or impossible to recover.

- It is no longer possible to change the search provider for the location
	bar from within this extension.  This functionality depended on a
	browser setting that is no longer used, keyword.URL
- The URL match filter option (search only in history, only in bookmarks, etc.)
	now appears in the main Preferences dialog, so there was no point in
	fixing it here.
- The "rounded corners" cosmetic setting has been removed, as I could not convince
	the location bar to accept such a style command (a number of styling options
	seem to be overriden by -moz-appearance: textfield).
- The "yellow background for secure URLs" cosmetic feature has been removed.
	It depended on the location bar having an attribute that indicated
	whether or not a given page was secure.  The necessary information is no
	longer stored in the location bar itself.

These broken features have been removed from the Settings window, but the
commented-out code is still in the files in case someone has a bright idea
about how to fix them.

The "show favicons only at left" preference now defaults to off, since it
could be argued that it messes with a security feature.

The Japanese and Chinese localizations may still refer to the browser in which
the add-on is installed as "Firefox", because I can read maybe a dozen kanji on
a good day, and half of those are numbers.  I did my best to fix all the other 
languages.

## Status of this Add-On

Effectively, it's in maintenance mode.  Since I use it myself, I'll attempt to keep
it functioning at its current level, but I'm unlikely to add new features, or even 
worry too much about bugs that existed under previous management (I'll fix them if 
they seem to be easy fixes).  

I'm happy to accept merge requests, though.

## History of this Add-On

Old Location Bar was originally created by Invertex ( http://kakkoii-baka.deviantart.com )

Ancient Location Bar was forked from Old Location Bar in May 2021.

## Notes if you're building this thing

While I've placed all the various Javascript, XUL, and CSS files into this repository
without packing them, in order for the extension to work, you must first pack everything
in the chrome subdirectory into a jar file named OldLocationBar.jar, then pack that
into the .xpi file.

Ancient Location Bar is licensed under the Mozilla Public License version 1.1.  This
was the original license and revision specified for Old Location Bar by its creator, 
and I have no intention of changing it.
