# Bookface User Styles for Friendica
Version: 1.3.1

If the Friendica server you are on does not offer the Bookface theme modifications you can apply them in your browser. You can only use either the Light or Dark version.

## INSTALLATION

**FIREFOX**

You have two options if you are using the Firefox browser (or any browser based on it):

1. Type `about:support` into the address bar.
2. Find “Profile Folder” and open that location
3. Create a folder named "chrome" there if one doesn’t already exist (it probably doesn’t)
4. Create a file in that folder named “userContent.css”
5. Add an entry to that file like this:
>>>>
	@-moz-document domain(friendica.world){
        
	}
>>>>
(change “_friendica.world_” to whatever instance you are on)

6. Copy and Paste the entire contents of the _bookface_light_userstyles.css_ or _bookface_dark_userstyles.css_ **inside** the {…} 
7. Restart Firefox and go to your Friendica instance and enjoy a modern Friendica experience.

Alternatively:

Install and enable the [Stylus Add-On](https://addons.mozilla.org/en-US/firefox/addon/styl-us/) for Firefox then copy and paste the code from either _bookface_light_userstyles.css_ or _bookface_dark_userstyles.css_ into that.

**CHROME**

For Google Chrome (or any Chromium-based broswer) you'll need to use the [Stylus Extension.](https://chromewebstore.google.com/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne) Copy and paste the theme code into that.

**SAFARI**

While Safari does support user content styles like Firefox does, it does **not** recognize document domains, so it would apply the styles to _every_ website! The way around this is to the [Userscripts Extension](https://apps.apple.com/us/app/userscripts/id1463298887) from the App Store, which can also do site-specific stylesheets.

**FRIENDICA**

Next, in Friendica, go to _Settings > Display > Theme_ and make sure it is set to "Frio."

If you are using the "Light" version then go to _Settings > Display > Theme Customization_ and make sure it is set to either "Light" or "Custom."  If you set it to "Custom" you should copy and paste this schemestring for the best appearance:

`{"nav_bg":"#ffffff","nav_icon_color":"#65686C","link_color":"#0066ff","background_color":"#f2f4f7","background_image":"","contentbg_transp":"100"}`

If you are using the "Dark" version then go to _Settings > Display > Theme Customization_ and set it to either "Dark" or "Black." There is no way to also use a schemestring with "Bookface Dark."

Enjoy a more modern looking Friendica!

## CUSTOMIZATION

The "Light" version can be used with Frio > Light or Frio > Custom. The "Dark" version can only be used with Frio > Dark or Frio > Black. Either "Light" or "Dark" versions can be used with Frio "Accent Colors" but you will need to edit the stylesheet(s) so they are using the same Accent Color:

* Blue:	#0066FF;
* Red:	#b50404;
* Purple:	#94439b;
* Green:	#218f39;
* Pink:	#d900a9;

_(Note: the Blue Accent Color is actually `#33a2e0`, but is mostly overridden with the richer blue color above. However there are some places you'll still see the lighter blue color)._

For your convenience all of the colors and pseudo-element labels are defined in CSS variables at the top of the stylesheet:

    --global-font-family: "Open Sans", Arial, sans-serif, Noto Color Emoji;
    --nav-bg: #ffffff;
    --link-color: #0066ff;  /* match Accent Color here */
    --nav-icon-color: #65686C;
    --background-color: #f2f4f7;
    --font-color: #313131;
    --font-color-darker: #333333;
    --menu-background-hover-color: color-mix(in oklab, var(--link-color) 15%, white);
    --border-color: #eeeeee;
    --count-color:  #ffffff;
    --count-bg: var(--link-color);
    
    /* LOCALIZE pseudo-element text below */
    --sign-in-text: 'Sign-In';
    --compose-text: 'Compose';
    --save-search-text: 'Save Search';
    --follow-tag-text: 'Follow Tag';
    --comment-button-text: 'Comment';
    --share-button-text: 'Share';
    --quote-button-text: 'Quote';
    --like-button-text: 'Like';
    --dislike-button-text: 'Dislike';
    --more-button-text: 'More';
    --attendyes-button-text: 'Going';
    --attendno-button-text: 'Can\'t Go';
    --attendmaybe-button-text: 'Maybe';
    --add-photo-button-text: 'Add Photos';
    --follow-button-text: 'Follow';
    --save-button-text: 'Save';

## GENERAL NOTES

There is no "Auto" version of the user content stylesheets because there is no way to automatically switch the underlying Frio scheme from "Light" to "Dark/Black" to match the user's preferred color scheme as set on their operating system.

## CONTRIBUTING

To make maintenance easier the line numbers between the "Light" and "Dark" stylesheets have been synchronized. So if you make a change in one file you can find the same line in the other and make the change there too, if needed, or add comment lines to keep the line numbers the same.

These are client-side user content stylesheets which means pretty much *everything* needs `!important` added to the end or it won't work. We are overriding almost all of the "Frio" theme with "Bookface."

In some places fallbacks are included to accommodate older browsers or mobile devices that do not understand more modern code. In general the target for this scheme are browsers released within the last couple of years.

Just because it looks right or works in your preferred browser or device doesn't mean it will work for everyone. **Try to thoroughly *test* your edits** in desktop and mobile Chromium-based, Mozilla-based, and Webkit-based browsers before submitting a pull-request.

---
Contributors:
Pygoscelis Papua @randompenguin@friendica.world
feb @feb@loma.ml
Phil @phil@loma.ml

License: AGPL 3.0 or Later