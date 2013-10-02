<b>(Note: the following installation instructions are a work-in-progress.)</b>

![image](http://hackshackers.com/wp-content/uploads/logos/chapters/nyc_side.gif)
# Encryption and Operational Security for Journalists

**Very important caveat**: These tools MAY NOT be 100% effective. The latest information we have is that they are likely to help protect your communications, but governments including the U.S. have made progress in breaking or circumventing some cryptographic technologies.

If you or your source is truly a high-value target of a government, protecting yourself will require far more effort. To get an idea of what people do when they are *really* serious about security, please read this post first: http://grugq.github.io/blog/2013/06/13/ignorance-is-strength/

Now that you have seen what you *might* need to do in the future, let's move on to what you should download in the meantime. 

Goal | Platform | Tool Name | Difficulty | Website
---- | -------- | --------- | ---------- | -------
More anonymous Web browsing | Both | Tor Browser Bundle | * * | [torproject.org][tor] ([downloads](https://www.torproject.org/projects/torbrowser.html.en))
Secure IM | Mac | Adium | * * | [adium.im][adium]
Secure IM | Windows | Pidgin + OTR | * * * | [pidgin.im](http://pidgin.im/)<br>&<br>[cypherpunks.ca/otr](http://www.cypherpunks.ca/otr/)
Encrypted email + text | Windows | GPG4Win | * * * * * | [gpg4win.org](http://www.gpg4win.org/) 
Encrypted email + text | Mac | GPG Tools | * * * * * | [gpgtools.org][gpgtools]
Sending encrypted email | Both | Thunderbird + Enigmail | * * * * * | [mozilla.org/thunderbird][thunderbird]<br>&<br>[enigmail.net][enigmail]
*Protecting files on your computer* | *Both* | *TrueCrypt* | * * * | [*truecrypt.org*][truecrypt]
*More secure file deletion* | *Both* | *CCleaner* | * * | *[piriform.com/ccleaner](http://www.piriform.com/mac/ccleaner) (Windows)<br>[piriform.com/mac/ccleaner](http://www.piriform.com/mac/ccleaner) (Mac)*
*Encrypted group chat* | *Both* | *CryptoCat* | * | *[crypto.cat][cryptocat]*

[tor]: https://www.torproject.org/
[adium]: https://adium.im/
[gpgtools]: https://gpgtools.org/
[thunderbird]: https://www.mozilla.org/en-US/thunderbird/
[enigmail]: https://www.enigmail.net/
[truecrypt]: http://www.truecrypt.org/
[cryptocat]: https://crypto.cat/

---

## Tor Browser Bundle

* **Website**: https://www.torproject.org/
* **Download**: We're using "development" versions here due to possible weaknesses in previous versions ([https://goo.gl/3wdfM4](http://arstechnica.com/security/2013/09/majority-of-tor-crypto-keys-could-be-broken-by-nsa-researcher-says/)).
  * https://www.torproject.org/projects/torbrowser.html.en
  * Windows [tor-browser-2.4.17-beta-1_en-US.exe][tor_win] ([https://goo.gl/taYC27][tor_win])
  * Mac OS X: [TorBrowser-2.4.17-beta-1-osx-i386-en-US.zip][tor_mac] ([https://goo.gl/Dw5uto][tor_mac])

[tor_win]: https://www.torproject.org/dist/torbrowser/tor-browser-2.4.17-beta-1_en-US.exe
[tor_mac]: https://www.torproject.org/dist/torbrowser/osx/TorBrowser-2.4.17-beta-1-osx-i386-en-US.zip

### Installation

**Windows**

1. Download the [tor-browser-2.4.17-beta-1_en-US.exe][tor_win] file. Make sure you choose to "Download" it rather than "Run", since where you put the file matters. Save it to your Downloads folder or your Desktop.
2. Once it’s fully downloaded, double-click the file. It will show a prompt asking you where to extract the files to — you shouldn’t need to touch this. Simply click "Extract." You'll see a "Tor Browser" folder appear next to the file you downloaded.
3. Delete the `tor-browser-2.4.17-beta-1_en-US.exe` file you originally downloaded.

**Mac OS X**

1. Download the [TorBrowser-2.4.17-beta-1-osx-i386-en-US.zip][tor_mac] file.
2. Once it’s fully downloaded, double-click the file to unpack it. You'll see a `TorBrowser_en-US` app appear next to the .zip file you double-clicked.
3. Move the `TorBrowser_en-US` app to your Applications folder.
4. Delete the `TorBrowser-2.4.17-beta-1-osx-i386-en-US.zip` file you originally downloaded.

### Using

1. Open the Tor Browser application.
  * **Windows**: Go to the "Tor Browser" folder you extracted, and open the `Start Tor Browser` program inside it.
  * **Mac**: Open `TorBrowser` in your Applications.
      * Mountain Lion users: you might get an error that the app “can’t be opened because it is from an unidentified developer”. If this happens, right-click on the app (or hold down “Control” on your keyboard and then click on the app) to show a menu on the file. Then hold down the "Option (Alt)" button on your keyboard and click the “Open” option in the menu. You will be asked if you are “sure you want to open [the app].” Once you click “Open,” you won’t need to go through these steps again for this app.
2. You will see a “Vidalia Control Panel” pop up. You can ignore it and simply wait as the Tor software starts to connect to the network. This may take a few minutes.
3. Once Tor is ready, the browser will automatically appear. It should also load a page that tests whether you are connected to Tor or not.

   To further test out the Tor browser connection, you can try to access the following site in the Tor browser: http://tigas3l7uusztiqu.onion/  
   This is simply a copy of my personal website, hosted at a ".onion" address. These addresses are only accessible via Tor, so this is a fairly bulletproof method for testing out your copy of Tor.

   If everything works as expected, then you’re browsing with Tor!

4. When you are done using Tor, you can close down the browser normally — but make sure you also press "Exit" on the Vidalia window, too.

### Details & Gotchas

Tor works by relaying your traffic through three other computers, each of which can only see the traffic that it recevies and the traffic that it relays back out. (Traffic is encrypted three times: the traffic you send out can only be decrypted by the first machine you send it to. The message it decrypts gives it instructions to send the rest of the data to the second computer. The second computer is the only one that can decrypt the traffic at that point. ...And so on. "Tor" stands for "The Onion Router", due to the layered way that this works.)

Tor only tunnels the raw traffic from your browser — it does not sanitize any of the information you actually send. So, if you are logging into websites under your real identity while using Tor, you are likely still leaking this to the website you are visiting — and you are likely leaking it to the final node in the Tor circuit.

Because Tor relies on volunteers providing computers to act as relays, the anonymity that Tor provides has limitations — if an adversary controls a large portion of Tor nodes, they can analyze and correlate Tor traffic.

---

## Adium (Mac OS X)

* **Website**: https://adium.im/
* **Download**: [Adium_1.5.7.dmg][adium_dl] ([https://goo.gl/vWOuCZ][adium_dl])

[adium_dl]: http://sourceforge.net/projects/adium/files/Adium_1.5.7.dmg/download

### Installation

1. Download the [Adium_1.5.7.dmg][adium_dl] file.
2. Once it’s fully downloaded, double-click the file to mount it. The window should automatically appear.
3. Copy the `Adium` app from inside to your Applications folder.
4. Eject the "Adium 1.5.7" mount on your desktop, then delete the `Adium_1.5.7.dmg` file you originally downloaded.

### First-time usage

Adium supports using chat accounts of all types, including AOL Instant Messenger, Facebook Chat, and Google Talk. You can use these accounts with Adium and use OTR encryption just fine. But this still gives metadata to the service: AIM/Facebook/Google still knows who you are talking to and how often. (They just don’t have the content of your messages now.)

Instead of using an existing account, we’ll go about setting up a separate “secure” account at `jabber.ccc.de`. This is a chat service provided by the Chaos Computer Club — a German hacker/activism group known for open data and privacy advocacy — and is used by many in the security community.

1. The first time you open Adium, a "Welcome to Adium!" window will open. Ignore it and close the window.
2. In the top-left of your screen, open the "Adium" menu and go to "Preferences."
3. In the "Accounts" tab, press the "+" (plus sign) button and choose "XMPP (Jabber)".
4. Pick a username you want (stick to letters/numbers/underscores) and add "@jabber.ccc.de" to the end of it. Enter this in the "Jabber ID" field.
   * i.e.: <i>mtigas</i>@jabber.ccc.de, <i>test12345</i>@jabber.ccc.de, etc.
5. Enter a password for this account. (Ideally you won't use the same password as on other sites.)
6. Click "Register New Account."
7. Enter `jabber.ccc.de` in the Server field. (Leave Port set to `5222`.) Click "Request New Account."
8. You'll get a message that your account was successfully registered. (If not, repeat steps 4-7 again, but with a different account name.)
9. Before leaving this menu, go to the "Privacy" tab and change the Encryption option to "Force encryption and refuse plaintext".
10. Press OK. Adium should connect your account automatically. You can now close the settings window.
   * If you get a "Verify Certificate" warning, click "Show Certificate", check the "Always trust "jabber.ccc.de" when connecting to "jabber.ccc.de", and then press "Continue".

### Usage

Adium should automatically connect to `jabber.ccc.de` and log you in when you open it.

**To add someone to your buddy list:**

1. Go to Contact (at the top of your screen) and hit "Add Contact".
2. Change Contact Type to "XMPP".
3. Type their username in the Jabber ID field.
   * You can test this out by trying to add me: **mtigas@jabber.ccc.de**
4. You can type their real name in under Alias since usernames aren’t always intuitive.
5. Press "Add".

When someone adds you to their buddy list, you will see an Authorization Request pop up. Press "Authorize & Add" to accept them and to add them to your own buddy list.

**When instant messaging somebody:**

The first time you talk to somebody with OTR encryption, you will need to verify that the user you are chatting with is actually the person they say they are.

Adium should prompt you for an OTR Fingerprint Verification. Note the "purported fingerprint" for your buddy. Using some other communication method (phone, etc.), verify this key. Then hit "Accept". If you can't verifiy it right now, you can hit "Verify Later" and simply chat with the person, but this does not prevent someone from pretending to be the buddy you want to talk to.

### For more security

You can set Adium to tunnel your `jabber.ccc.de` connection over Tor. This routes your connection over Tor so that the Chaos Computer Club servers cannot identify you by IP address.

1. In the top-left of your screen, open the "Adium" menu and go to "Preferences."
2. In the "Accounts" tab, click on your `jabber.ccc.de` account and then press "Edit".
3. Under the "Proxy" tab, check the "Connect using proxy" box and use the following settings. Leave "Username" and "Password" blank.
   * Type: "SOCKS5"
   * Server: 127.0.0.1
   * Port: 9150
4. Under the "Options" tab, set the Connect Server to `okj7xc6j2szr2y75.onion`.
5. Press "OK".
6. Launch Tor Browser Bundle (as above). Wait for the browser to finish connecting and for the Tor browser to show up.
7. Uncheck the checkbox for your `jabber.ccc.de` account and then re-check it.

From now on, you will need to launch Tor Browser Bundle and wait for it to connect before launching Adium. Connecting to `jabber.ccc.de` will be very slow when you first open Adium, but your chat connections will be tunneled such that your IP address cannot be inferred by the chat server.

---

## Pidgin (Windows)

* **Website**: https://pidgin.im/ & http://www.cypherpunks.ca/otr/
* **Download**: [pidgin-2.10.7.exe][pidgin_dl] ([https://goo.gl/lcBqn4][pidgin_dl]) & [pidgin-otr-4.0.0-1.exe][otr_dl] ([https://goo.gl/FiqBJi][otr_dl])

[pidgin_dl]: http://sourceforge.net/projects/pidgin/files/Pidgin/2.10.7/pidgin-2.10.7.exe/download
[otr_dl]: http://www.cypherpunks.ca/otr/binaries/windows/pidgin-otr-4.0.0-1.exe

### Installation

TODO

### First-time usage

Pidgin supports using chat accounts of all types, including AOL Instant Messenger, Facebook Chat, and Google Talk. You can use these accounts with Pidgin and use OTR encryption just fine. But this still gives metadata to the service: AIM/Facebook/Google still knows who you are talking to and how often. (They just don’t have the content of your messages now.)

Instead of using an existing account, we’ll go about setting up a separate “secure” account at `jabber.ccc.de`. This is a chat service provided by the Chaos Computer Club — a German hacker/activism group known for open data and privacy advocacy — and is used by many in the security community.

### Usage

Pidgin should automatically connect to `jabber.ccc.de` and log you in when you open it.

**To add someone to your buddy list:**

TODO


**When instant messaging somebody:**

TODO

### For more security

You can set Pidgin to tunnel your `jabber.ccc.de` connection over Tor.

TODO

---

## Thunderbird + Enigmail

* **Website**:
* **Download**:

TODO / DRAFT. Below instructions are early draft-quality at this point.

### Installation

#### 1: Install GPG4Win (Windows) or GPGTools (Mac OS X)
* GPG4Win: Download the full GPG4Win package and then install it as you would a normal program.
* GPGTools: Download the GPGTools/GPGSuite package and open it. Double-click the "pkg" file inside it to install the toolkit.

#### 2: Install Thunderbird

#### 3: Set up your e-mail account

Open up Thunderbird and set up your Gmail account (or whichever e-mail account you want to use). Thunderbird should prompt you and walk you through it when it starts up (if you haven't already set up an account). If you have issues, see <a href="https://support.mozillamessaging.com/en-US/kb/thunderbird-and-gmail">their documentation</a>.

#### 4: Install Enigmail into Thunderbird

* In the top menu, go to Tools->Add Ons.
* Click on the "Extensions" tab.
* At the top of that window, there will be a "gear" icon to the left of the search box. Click it and choose "Install Add-on From File..." 
* Go to the "enigmail-1.5.2-tb+sm.xpi" file you downloaded and choose that to install it.
* The add-on screen will say that Thunderbird should restart before it’s active, so let it do that.

Now that Thunderbird’s open again, if you’re still in the "Add-ons Manager" tab, close that to go back to your inbox.

#### 5: Generate a GPG key

In the top menu, you'll now see "OpenPGP". Click that and go to "Key Management".

This Key Management screen should be empty unless you already generated a GPG key in another program. To generate a key:

* While in "Key Management" screen, click on "Generate" in the top menu and then "New Key Pair".
* Choose the e-mail address you set up and make sure "Use generated key for the selected identity" is checked.
* Type in a password to protect this key. Leave "Comment" blank. (This is a note that shows up next to your name. If you make multiple keys or if you have an alias or nickname that everyone uses, you can put that info here.)
* Under "Advanced" tab, change "Key size" to 4096.
* Generate the key.
* When it asks you if you want to make a Revocation Certificate, just skip that step for now.

In "Key Management", you'll see a listing for your name & email address. It should be in bold, which means that it’s a key containing the "private" portion of the key.

#### 6: Upload the GPG key somewhere

(NOTE: Skip this step if your e-mail address is sensitive & should not be published in any public directories.)

The "public" part of the GPG key is the part that other people need so that they can send you encrypted mails. You can either upload this to your website or to a "key server" (which is basically an e-mail directory that shows if there are GPG keys available for a given e-mail address). These instructions are for uploading to a key server, since that's usually the easiest way to go.

In the "Key Management" window, right-click on the entry for your name/e-mail. Click "Upload keys to keyserver". Type "pgp.mit.edu" in as the keyserver and press OK to upload. (There shouldn't be any confirmation prompt. An "uploading" screen should appear and then it should just go away.)

You can test if it worked by going to http://pgp.mit.edu/ and searching for your name or e-mail address.

#### 7: How to send an encrypted e-mail to someone.

If you're e-mailing someone who already has a PGP key -- basically, anybody who has done the above steps -- you can start sending them encrypted messages and they can start sending you encrypted messages.

In the "Key Management" window, click on "Keyserver" at the top menu and click "Search for Keys".

* You can look for someone's e-mail address in here. Test it out on mine: `mike AT tig DOT as` (change words to punctuation to make it a real e-mail address)
* Sometimes someone has multiple keys (since old ones sometimes expire or are lost). Mine is 6E0E9923.
* This ID is very important to verify with people, since nothing stops a person from generating a fake "Mike Tigas <...>" key and uploading it to a server. (They won't be able to send e-mail from my Gmail account, but they can make it confusing & hard for people to find my correct key.) This is why my business cards & website & Twitter bio all mention my key ID.
* Click the checkbox" next to my 6E0E9923 entry and press OK to download it from the keyserver.
* Some output will appear. Click OK.
* Now, there will be an entry for me in your Key Management window. It will not be bold, because you only have the "public" portion of the key.

Now that you have the public key for me, you can test sending an encrypted message.Close the Key Management window and write a message in Thunderbird.

* Address it to me: `mike AT tig DOT as` (of course, turn this into a real e-mail address)
* Write whatever message you'd like.
* Click on "OpenPGP" in the message window and you'll get some options. You'll want to sign and encrypt the message. (PGP/MIME is useful if you are sending attachments, but it only works with people who have Enigmail, and not with people who use PGP in other ways. So I try to avoid it.)
* In the bottom-right corner, you'll see a pencil and a key icon -- which represent signing & encrypting. You can use these  instead of opening the OpenPGP menu, too. (Make sure to look at these before sending any message — I've heard that Enigmail sometimes turns off encryption randomly, so it's good habit to make sure to explicitly check this every time you need to send a message.)
* Send the message. Thunderbird will ask you for the password you used when you set up the GPG key (back in step 5).

#### 8: Receiving encrypted mail from others

The other person will have to basically do the things in step 7, but with your e-mail address instead.

When you receive a message, Thunderbird will ask you for the password you used for the GPG key, so that it can unlock it and decrypt that message.

#### 9: Sharing the key with other people

Since you uploaded your key in step 6, you'll need to tell people where to find it and make sure you publish this information in several places so that there's some level of verification. A good way to do this is:

* search for your name at pgp.mit.edu
* find the entry for you and click the link where the ID is (not the "Name <email>" part).
* link to this page on your blog or e-mail people a link to this page.

This isn't the only way to do this.

If you skipped step 6, you'll want to directly share your key and sidestep the whole directory system. You can use the Key Management window and press "Export Keys to File" or "Send Public Keys by Email". Make sure you export the Public Key only. Sharing this file or sending this message will let the recipient add the key to their own computer. (From the Key Management window: File->Import Keys from File, or if received from an e-mail and copied it: Edit->Import Keys from Clipboard.)

When exporting your Public Key to a file, you can upload this file to your blog or somewhere and link to it from a place where folks would be able to find.

Now you basically have a system where people who know about PGP can e-mail you securely:

1. They can find you in a keyserver and use that key to e-mail you
2. They can find your key on your website (or if you have e-mailed them that link directly) and have seen that your key ID matches in several places.
