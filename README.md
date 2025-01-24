## Bookface User Styles for Friendica

If the Friendica server you are on does not offer the Bookface theme modifications you can apply them in your browser. You can only use either the Light or Dark version.

## How To Use

**FIREFOX**

You have two options if you are using the Firefox browser (or any browser based on it):

1. Copy and Paste the code into a "userContent.css" file placed in the "chrome" folder of your profile. You will need to wrap the code with:
 `@-moz-document domain(friendica.world){...}` (change the domain name from "friendica.world" to whichever server you are on).

1. Use the [Stylus Add-On](https://addons.mozilla.org/en-US/firefox/addon/styl-us/) and copy and paste the code into that.

**CHROME**

For Google Chrome (or any Chromium-based broswer) you'll need to use the [Stylus Extension.](https://chromewebstore.google.com/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne) Copy and paste the theme code into that.

**SAFARI**

While Safari does support user content styles like Firefox does, it does **not** recognize document domains, so it would apply the styles to _every_ website! The way around this is to the [Userscripts Extension](https://apps.apple.com/us/app/userscripts/id1463298887) from the App Store, which can also do site-specific stylesheets.

**FRIENDICA**

Next, in Friendica, go to _Settings > Display > Theme_ and make sure it is set to "Frio."

If you are using the "Light" version then go to _Settings > Display > Theme Customization_ and make sure it is set to either "Light" or "Custom."  If you set it to "Custom" you should copy and paste this schemestring for the best appearance:

`{"nav_bg":"#ffffff","nav_icon_color":"#606637","link_color":"#0866ff","background_color":"#f2f4f7","background_image":"","contentbg_transp":"100"}`

If you are using the "Dark" version then go to _Settings > Display > Theme Customization_ and set it to either "Dark" or "Black." There is no way to also use a schemestring with "Bookface Dark."

Enjoy a more modern looking Friendica!

