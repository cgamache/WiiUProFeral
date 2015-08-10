Wii U Pro Controller Configuration for Batman Arkham Asylum OSX
===============================================================

Feral games does a good job of including support for any type of game pad. One controller they don't support out-of-the-box is the Wii U Pro Controller. 
But, with a little hackery, you can use this wonderful controller inside Batman: Arkham Asylum, and possibly other Feral-ported games.

As of this moment, it will require some effort on your part to download, patch, and compile [wjoy](https://code.google.com/p/wjoy/). You will also have to
allow unsigned kext's (kernel extensions) to be loaded by OSX, potentially allowing both desirable (wjoy's kext) and undesirable unsigned kext's (malware etc.) to be loaded. So, this isn't for the feint-of-heart. 

I'm not advising or advocating loading unsigned kext's as a good idea, and you make these changes at your own risk.
-------------------------------------------------------------------------------------------------------------------

Now that that's out of the way... On to the recipe:

I'm assuming you have installed XCode and can at least Google your way to cloning and compiling the source code:

1. Clone wjoy from https://github.com/alxn1/wjoy/ ... I'm working from commit 0d47c07. Later revisions might have patches built-in.
2. Apply changes to WiimoteAutoWrapper.m ... the VendorID and ProductID are important, but those values were selected by me arbitrarily. I have no guarantee that they won't collide 
horribly with some other manufacturer's official VendorID and ProductID. (Any insight on proper ID selection would be welcome.) 
3. Place WiiUPro.plist in "/Applications/Batman Arkham Asylum.app/Contents/Resources/InputDevices/Customer/" (path is valid as of v1.1)
4. Follow instructions from [Stack Exchange](http://apple.stackexchange.com/questions/163059/how-can-i-disable-kext-signing-in-mac-os-x-10-10-yosemite) ... Essentially "sudo nvram boot-args=kext-dev-mode=1"
5. Reboot
6. Compile and run wjoy
7. Pair Wii U Pro Controller
8. Start Batman: Arkham Asylum

It is my hope that one day Feral will distribute this gamepad config, wjoy will include these fixes, and that it will not require kext developer mode to work properly. A pair-and-play solution.

To that end-- the developer of wjoy, Alexander Serkov,  is in need of a developer's certificate. You can help him afford a certificate by donating to him via [PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=K9LWNA6E5RS28).

Good luck, and happy gaming!

P.S. I have confirmed that the plist also works with Batman Arkham City (GOTY).


