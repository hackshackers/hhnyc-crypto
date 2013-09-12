# Encryption and Operational Security for Journalists

(**Note**: the following installation instructions are a work-in-progress.)

**Very important caveat**: These tools MAY NOT be 100% effective. The latest information we have is that they are likely to help protect your communications, but governments including the U.S. have made progress in breaking or circumventing some cryptographic technologies.

If you or your source is truly a high-value target of a government, protecting yourself will require far more effort. To get an idea of what people do when they are *really* serious about security, please read this post first: http://grugq.github.io/blog/2013/06/13/ignorance-is-strength/

Now that you have seen what you *might* need to do in the future, let's move on to what you should download in the meantime. 

Goal |	Platform	| Tool Name | Difficulty | Where To Find It
---- | ---------- | --------- | ---------- | ----------------
More anonymous Web + IM	| Both | Tor browser bundle | * * | https://www.torproject.org/ 
Secure IM | Mac | Adium | * * | https://adium.im/
Secure IM | Windows | Pidgin + OTR | * * * | http://pidgin.im/ + http://www.cypherpunks.ca/otr/
Encrypted email + text | Windows | GPG4Win | * * * * * | http://www.gpg4win.org/ 
Encrypted email + text | Mac | GPG Tools | * * * * * | https://gpgtools.org/
Sending encrypted email | Both | Thunderbird + Enigmail | * * * * * | https://www.mozilla.org/en-US/thunderbird/ + https://www.enigmail.net/download/index.php
*Protecting files on your computer* | *Both* | *TrueCrypt* | * * | *http://www.truecrypt.org/downloads*
*More secure file deletion* | *Both* | *CCleaner* | * * | *http://www.piriform.com/ccleaner (Windows) / http://www.piriform.com/mac/ccleaner (Mac)*
*Encrypted group chat, for use in safe environments* | *Both* | *CrytpoCat* | * | *https://crypto.cat/*

---

## Tor

* **Website**: https://www.torproject.org/
* **Download**: We're using "development" versions here due to possible weaknesses in previous versions ([https://goo.gl/3wdfM4](http://arstechnica.com/security/2013/09/majority-of-tor-crypto-keys-could-be-broken-by-nsa-researcher-says/)).
  * https://www.torproject.org/projects/torbrowser.html.en
  * Windows [https://goo.gl/taYC27](https://www.torproject.org/dist/torbrowser/tor-browser-2.4.17-beta-1_en-US.exe)
  * Mac OS X: [https://goo.gl/Dw5uto](https://www.torproject.org/dist/torbrowser/osx/TorBrowser-2.4.17-beta-1-osx-i386-en-US.zip)

1. Download the file for the operating system you are using.
2. Double-click the file to unpack it. On Mac OS X you'll see a `TorBrowser_en-US.app` file appear next to the .zip file you double-clicked. [Windows: TK]
3. Open the TorBrowser application you just unpacked.
   * If you are using Mac OS X Mountain Lion, you might get an error that the app “can’t be opened because it is from an unidentified developer. If this happens, right-click on the app (or hold down “Control” on your keyboard and then click on the app) to show a menu on the file. Then hold down the "Option (Alt)" button on your keyboard and click the “Open” option in the menu. You will be asked if you are “sure you want to open [the app].” Once you click “Open,” you won’t need to go through these steps again for this app.
4. You will see a “Vidalia Control Panel” pop up. You can ignore it as the Tor software starts to connect to the network. This may take a few minutes.
5. Once Tor is ready, the browser will automatically appear.
