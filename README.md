# Bookface User Styles for Friendica
Version: 1.5.8

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
    --content-bg: var(--nav-gb);
    --comment-bg: var(--background-color);
    --font-color: #313131;
    --font-color-darker: #333333;
    --menu-background-hover-color: color-mix(in oklab, var(--link-color) 15%, white);
    --border-color: #eeeeee;
    --count-color:  #ffffff;
    --count-bg: var(--link-color);
    --attach-file-button: none; /* none or block */
    
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

## CHANGELOG:
* Fixed HR rule in posts [Issue #13]
* Fixed notification profile pics so they are round [Issue #14]
* Fixed Post and Comment background colors [Issue #15]
* Made Post and Comment background colors configurable by CSS variables
* Fixed Post-in-Group/Mention button alignment [Issue #16]
* Fixed double underline on Compose active tabs [Issue #17]
* Fixed double Compose tabs issue on mobile [Issue #18]
* Fixed Accept Contact button [Issue #19]
* Fixed misaligned close button [Issue #20]

1.5 (27 Feb 2025)
* fixed browser "Share to.." button display and sizing [Issue #3]
* fixed wrong sized menu items in action button drop-downs on mobile [related to Issue #3]
* Styled content filter buttons coming from other platforms.
* Attach file button moved to CSS variable
* Profile contacts size adjust for Frio breakpoints
* Fixed Category & Folder tag-buttons [Issue #4]
* Removed text shadow from tags [Issue #5]
* Unstyled Comment button on other people's profiles [Issue #7]
* Hide horizontal rules for cleaner look
* Minor style fixes for .panel-body and .help-block
* Removed box-shadow from .wall-item-comment-wrapper
* Fixed Settings > Channels Panel padding and Submit button alignment
* Redesigned Calculator Add-On [Issue #8]
* Fixed photo album thumbnail size for mobile [Issue #10]
* Fixed context of .panel-body, was only intended only for Settings page
* New Mobile Profiles [Issue #11]
* Added camera icon to user's Recent Photos because no profile photo is shown on it.
* Adjusted mobile drop-down button appearance and position
* Made ul.nav-tabs appearance consistent with secondary toolbar tabs 
* Made ul.nav-tabs turn into buttons on narrow mobile screens
* Box shadow on Compose formatting buttons removed from dark version 

1.4 (12 Feb 2025)
* Limited textarea resize fix to settings pages
* Edited authors/contributors
* Edited README for clarity
* Switched README from plaintext to markdown
* fixed file browser scroll height issue
* fixed too much padding at top of login page
* Added changelog to user styles README

1.3 (11 Feb 2025)
* Added "Auto" version that automatically detects OS light/dark color mode and applies it.
* Color and position of Admin "Save" buttons normalized to rest of settings.
* Normalized Admin "Save/Submit" buttons style and position (including all Add-Ons settings).
* Brand Text positioned and styled to match color scheme
* Advanced Content Filter add-on help table overflow fixed.
* Added "Sign-In" text to button when not signed in because a friend specifically said he couldn't figure out WHERE to sign-in/register.
* User Menu overflow-x is now hidden (who likes horizontal scrollbars?)
* Selected nav on :focus styling fixed.
* Edit Photo image no longer spills out of container on mobile.
* "Submit" photo edits button moved right.
* Fixed photo album thumbnails spilling out of page container.
* Made spacing of photo album thumbnails even.
* Profile photo in second toolbar mini-vcard rounded 
* Landscape on small screen phones hides toolbars and displays limited buttons
* Mobile mode completely revamped for modern app-like behavior
* Support for profile "Cover Photo"
* Added CSS variables to easily localize pseudo-element text labels
* Added CSS variable to separately set engagement count background color (default is still link color)
* CSS line numbers synchronized between light and dark stylesheets for easier maintenance
* Profile photos in Messages are now circular
* Event Card now has roundy buttons
* popover/hovercards borders and arrows restyled
* Tags, Mentions, and Categories buttons restyled larger but less distracting.
* Shared post now has background color of a top-level post.
* New Message button styled for Mobile
* Brand Icon switched from SVG to icon font because SVG masks are broken in Webkit browsers.
* Light and Dark versions now support custom Link Color, with error catching to prevent setting it to the same color as nav or page background.
* Event Response button positions fixed for old Safari Mobile.
* Login screen layout fixed [GitLab issue #2]
* Info screen fixed.
* Fixed overflow dropdown menu hover effect
* Fixed overflow dropdown menu active styling
* "Compose" button on Personal Notes page changed to "New Note"
* Added lock icon to "Personal Notes" header to make it clear they are not public.


1.2 (25 Jan 2025)
* "Save" buttons for "Remote Servers" settings normalized to right.
* "Close" button and open "Compose" button restyled, "Close" enlarged for better touch target.
* Open Compose Page button styled to match roundy buttons.
* "Save Search" buttons styles to match "Compose" and "Mention" buttons.
* Dark version Settings container background color fixed.
* Comment Box background fixed.
* Compose/Comment text style buttons enlarged for better touch targets, styled to match on Compose Modal, Compose Page, and Comment below post.
* Aside Selected Menu item now adopts color scheme.
* All Modal File browsers now styled the same.
* IFRAME container positioned and styled (usually used for embedded video)
* Fixed "Like/Dislike" on photos showing label twice.
* TopBar Second vcard short photo made round.

1.1 (21 Jan 2025)
* Fixes long lists of tags/mentions spilling out of post or profile container, forces them to wrap to multiple rows as necessary.
* Adds spacing to left of multiple settings buttons floated to right.

1.0 (20 Jan 2025)
* Initial release of server-side version
* Accent colors now work (server-side version only)
* Compose Title border radius normalized to rest of inputs.
* Top Bar buttons fixed for small mobile screens.
* Delegate "Save" settings button normalized to right side.
* Form input background colors normalized.

0.4 (18 Jan 2025)
* Adds "superscript" engagement numbers to mobile Action Buttons.
* Settings "Submit" buttons normalized to right-hand placement.
* "Mention" button and "Compose" buttons sizing normalized.
* Compose Modal/Page and Reply now styled.
* File Attachment Button hidden in Compose File Browser.
* Adjustment to Event RSVP buttons for both desktop and mobile.
* Styling and adjustment to Profile Extra links.
* Changed Network Links from "Link:" text to buttons style with chevron.

0.3 (16 Jan 2025)
* Light and Dark mode user stylesheets.
* Light version first adapted to theme template/scheme for server-side.
* Added "superscript" engagement numbers to desktop Action Buttons

0.2 (13 Jan 2025)
* Added labels to Action Buttons.

0.1 (12 Jan 2025)
* Based on original bookface.css user stylesheet (light mode only)

---
Contributors:
Pygoscelis Papua @randompenguin@friendica.world
feb @feb@loma.ml
Phil @phil@loma.ml

License: AGPL 3.0 or Later