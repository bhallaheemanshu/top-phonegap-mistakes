### Current Tripping Points to Cordova/Phonegap ###
Date: 2015-09-25

## 1. No support for iOS9 YET! ##

**PhoneGap Build iOS 9 Support Status**

* Sept 23, 2015
* http://community.phonegap.com/nitobi/topics/phonegap-build-ios-9-support-status
* Top line: iOS 9 is **NOT** officially supported until Cordova-iOS 4.0.0, which the Cordova team is hard at work on. However some issues can be solved with some simple configuration changes. 

> At this point in time, 4 bugs are reported to the Cordova Bug repository. Your issue does not appear in the respository - as of this date.

 * 4 bugs - https://issues.apache.org/jira/browse/CB-9684?jql=text%20~%20%22iOS9%22
 * 1 bug - https://openradar.appspot.com/22186109

  Regardless, of what you are using, as the forum post states, iOS 9 is not officially supported until Cordova-iOS 4.0.0. This means, if you encouter a bug, you must - create a work around, or wait until it is officially supported, _OR_ file a bug report with cordova, _OR_ wait until someone else creates a work around.
  
  Sometimes Phonegap makes announcements on the forum and not the blog.<br />
  For more: [(Official) Messages from Phonegap Build Technical Support in the Forum](http://codesnippets.altervista.org/documentation/phonegap/bookmarks/fromSupport.html)

## 2. Not setting compiler version ##

From the *Phonegap Build* Forum, [Petra Adds](http://community.phonegap.com/nitobi/topics/no-support-for-ios9-yet#reply_16160589):

 > I would add: without announcement, PGB changed the default PGB-version from 3.7.0 to cli-5.2.0. This causes all those who have not set 'phonegap-version' in config.xml to be confronted with the sudden need of splashscreen and whitelist plugins and additional whitelisting specifications in config and html.

 > Also, several plugins seem not to build correctly with cli-5.2.0, causing log file error messages about "Class ***.java".

 FWIW: *Phonegap Build* [admitted to as much in this tweet](https://twitter.com/jessemonroy650/status/648313365505310720)

**QUICK FIX*** Add this to your `config.xml`<br />
`<preference name="phonegap-version" value="3.7.0" />`

From [Top Mistakes by Developers new to Cordova/Phonegap](https://github.com/jessemonroy650/top-phonegap-mistakes/blob/master/new-to-Phonegap.md) you have hit:

 * \#6 **Not setting the "phonegap version" for your compiler**
 * \#7 **Not setting "version" for you plugins**
 * \#10 **Not adding the new "white-list" and "white-list plugin" parameters in config.xml.**

For #6 & #7

 > With the CLI version, if you do not assign a version for your platform OR in ''Phonegap Build'' if you do not set the phonegap-version in config.xml, YOU WILL GET THE LATEST VERSION. If you are lucky, your program just works as expected. If you are not lucky, you'll get a set of cascading errors.

 > Luckily for all of us, Holly Schinsky has written a nice blog post to explain it all:

 > *Cordova/PhoneGap Version Confusion*<br />
 > http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/

For #10

 > This relatively * NEW * requirement means &ndash; to access ANY website or resources on the web, you MUST use the whitelist and the whitelist plugin. This requirement goes into affect, if you are using cordova-android@4.0.0 or better; including cli-5.1.1. If however, your version is before 4.0.0, let's say 3.5.0 or 3.7.0, then you will *not* have to add the *white-list* requirement.

 > To be clear, the "whitelist" has been around for a bit, but the plugin and requirement is very new. As you would expect, when the "whitelist" was added, the defacto open-access feature was deprecated. Or said another way, the defacto open-access feature was planned and scheduled to be eliminated. This change marks a step in removal of the open-access feature.

 > In addition, the Content Security Policy (CSP) has caught numerous developers - because it was soooo poorly publicized. Depending you your use and the version of Phonegap you are using, the CSP needs to go in every single HTML page you used, just like you have to wait for 'deviceready'. The documentation is confusing for some, please read it carefully. The documentation is buried in the bottom of many of the latest documentation pages.

 <b>Related Links</b>
 > Phonegap Build Forum: [Notes for upgrading to cli-5.1.1 on PGB](http://community.phonegap.com/nitobi/topics/notes-for-upgrading-to-cli-5-1-1-on-pgb) and now required Whitelist

 > * [Cordova Whitelist Guide](https://cordova.apache.org/docs/en/4.0.0/guide_appdev_whitelist_index.md.html)
 > * [Phonegap Whitelist Guide](http://docs.phonegap.com/en/4.0.0/guide_appdev_whitelist_index.md.html#Whitelist%20Guide)
 > * [Phonegap Build Whitelist Guide](http://docs.build.phonegap.com/en_US/configuring_access_elements.md.html#Access%20Elements)
