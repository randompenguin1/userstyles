# Bookface User Styles for Friendica
Version: 1.8.0

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

	/* Fonts and Colors */
    --global-font-family: "Open Sans", Arial, sans-serif, Noto Color Emoji;
    --nav-bg: #ffffff;
    --link-color: #0066ff;
    --nav-icon-color: #65686c;
    --background-color: #f2f4f7;
    --content-bg: var(--nav-bg);
    --comment-bg: var(--background-color);
    --font-color: #313131;
    --font-color-lighter: #444444; 
    --font-color-darker: #333333;
    --menu-background-hover-color: #cee9f7;
    --border-color: #eeeeee;
    --count-color:  #ffffff;
    --count-bg: var(--link-color);
    --shadowglow: rgba(0,0,0,.3);	
    --dimbright:  rgba(0,0,0,.1);	
    
    /* Theme Features */
	--attach-file-button: none; /* none or block */
	--show-tooltips: block; /* none or block */ 
	--show-navbar-labels: none; /*none or block */ 
    
    /* LOCALIZE pseudo-element text below */
    --navbar-network-text: 'Network';
    --navbar-profile-text: 'Home';
    --navbar-community-text: 'News Feed';
    --navbar-messages-text: 'Messages';
    --navbar-calendar-text: 'Calendar';
    --navbar-contact-text: 'Friends';
    --navbar-notices-text: 'Notices';
    --sign-in-text: 'Sign-In';
    --compose-text: 'Compose';
    --new-note-text: 'New Note';
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
	--new-message-text: 'New Message';
	--calendar-today-text: 'Today';  

### COVER PHOTOS

From Bookface 1.3 it supports adding a "Cover Photo" to profiles. There are two places you can add the Cover Photo, depending on whether you want it used on all of your profile section pages or if you want it to appear on ONLY your actual profile page.

Note that this feature ONLY works is recent, modern browsers!  Every *current* and *supported* desktop and mobile version should be able to show it, but nothing *unsupoorted* nor released before 2022 will (see caniuse.com entry for "has()" for specific verssions).

#### ON ALL PROFILE PAGES

1. Go to _Settings > Profile > Personal_

2. In the "Description" box add something like:

`[class=coverphoto][img=https://friendica.server/photo/1649cc674810612350.png]Cover photo description alt-text here[/img][/class]`

3. Submit your changes.

For people who are not using the Bookface scheme they will simply see a thumbnail of your Cover Photo in the sidebar with your Profile Description. For people who ARE using the Bookface scheme they will see your Cover Photo on your Profile, Conversations, etc. pages that have a sidebar.

#### ON JUST YOUR PROFILE PAGE

1. Go to _Settings > Profile > Custom Profile Fields_

2. Enter nothing in the "Label" field.

3. Enter something like this in the "Value" field:

`[class=coverphoto][img=https://friendica.server/photo/1649cc674810612350.png]Cover photo description alt-text here[/img][/class]`

4. Check the Permissions for the field. If for some reason you only want people in certain Circles to see your Cover Photo you can set that here.

5. Submit your changes.

People who are not using the Bookface scheme will see a thumbnail of your Cover Photo in your Profile details. The Cover Photo will only appear on your Profile page.

#### Multiple Cover Photos

Technically you can have one Cover Photo for our actual Profile page by putting it in a Custom Field and another one in the Profile Description that will be shown on the other profile pages.  But if you want to get really creative you can also have multiple images per Cover Photo.

While not really recommended you can place up to four images in the Cover Photo container and Bookface will show them as a collage of stripes.  For example:

`[class=coverphoto][img=https://friendica.server/photo/1649cc674810612350.png]Cover photo 1 description alt-text here[/img][img=https://friendica.server/photo/1649cc677034958382350.png]Cover photo 2 description alt-text here[/img][img=https://friendica.server/photo/1649c038920505603674810612350.png]Cover photo 3 description alt-text here[/img][img=https://friendica.server/photo/3464771649cc674810612350.png]Cover photo 4 description alt-text here[/img][/class]`

Extras spaces are okay, but just make sure there are no carriage returns or other elements inside `[class]..[/class]` or it will mis-count the images and size them wrong. Also keep in mind people not using Bookface will see three thumbnail images on your profile, only Bookface users will see the striped collage.

### POSTBOXES

Starting with Bookface version 1.6 now Friendica will have Postboxes too! Styling similar to the Facebook solid color and gradient backgrounds have been added to the Bookface stylesheets.

**Right now Postbox is exclusively available for people using the Bookface scheme in the Friendica webapp, either on desktop or mobile.**

When a Postbox post is shared to another platform like Mastodon, Sharkey, Disapora, Hubzilla, etc., the Postbox styling does not go with it. The same is true for anyone viewing the post in a third-party app, because none of them support Postbox styling, at least not yet.

There are two Friendica add-ons server administrators can install to add global support for Postbox styling. The "[Postbox](https://gitlab.com/randompenguin/postbox)" add-on simply adds a stylesheet to the `<head>` element. It provides no interface for creating Postboxes, but users can still create them manually with BBcode. The other is the "[Zen Postbox](https://gitlab.com/randompenguin/zen_postbox)" add-on which not only adds the stylesheet to the `<head>` it also adds a Jot Plugin button to the message composer with a menu of all the available Postbox styles.

#### How to Use Postboxes

To make use of a Friendica Postbox simply wrap the text inside a Postbox Class BBcode like this:

`[class=postbox-red]This is the wrapped text[/class]`

#### Available Color Options

In the `[class]` opener add `postbox-` plus any one of the color names after the "=" sign.

Old names are in parenthesis next to the new names to which they've been mapped.

**Solid Color Backgrounds:**

- .postbox-black
- .postbox-cornflowerblue (.postbox-blue)
- .postbox-darkblue (.postbox-ocean)
- .postbox-darkgray
- .postbox-darkorange (.postbox-orange)
- .postbox-darkred
- .postbox-darkslateblue
- .postbox-forestgreen (.postbox-forest)
- .postbox-gold
- .postbox-goldenrod
- .postbox-honeydew
- .postbox-hotpink
- .postbox-lavender
- .postbox-lightpink
- .postbox-lightyellow
- .postbox-limegreen (.postbox-green)
- .postbox-lightsalmon (.postbox-salmon)
- .postbox-mediumaquamarine
- .postbox-mediumslateblue
- .postbox-mediumvioletred
- .postbox-mintcream
- .postbox-olivedrab
- .postbox-palegreen
- .postbox-peachpuff
- .postbox-pink
- .postbox-purple
- .postbox-red
- .postbox-seagreen
- .postbox-sienna
- .postbox-skyblue
- .postbox-thistle
- .postbox-violet
- .postbox-whitesmoke
- .postbox-yellowgreen


**Gradient Backgrounds:**

- .postbox-aurora
- .postbox-bluegray
- .postbox-graygrey (.postbox-darkgray)
- .postbox-grayblack
- .postbox-greengray
- .postbox-lavendergray
- .postbox-minty
- .postbox-mintgray
- .postbox-rainbow
- .postbox-redblue
- .postbox-sherbet (.postbox-sherbert)
- .postbox-spectrum
- .postbox-strawberrycream
- .postbox-sunset
- .postbox-tealblue
- .postbox-tealgray
- .postbox-violets
- .postbox-violetblue

**Pattern Backgrounds:**

- .postbox-blueprint
- .postbox-birds
- .postbox-checkered
- .postbox-cubes
- .postbox-lemonlime
- .postbox-gingham
- .postbox-grid
- .postbox-hearts
- .postbox-honeycomb
- .postbox-notebook
- .postbox-plaid
- .postbox-polkadots
- .postbox-shadedots
- .postbox-shadowbox
- .postbox-stars
- .postbox-warpgrid
- .postbox-wavy

(There are also some _Animated Backgrounds_ but they are only available if either the "Postbox" or "Zen Postbox" add-on is installed and activated on the server)

#### Content Restrictions

Friendica's Postbox is a bit more forgiving as it allows for more than text-only content. However it does not work with most of the Friendica formatting due to the way BBcode is parsed.

**BBcodes you CANNOT put inside a Postbox:**

- [class], which means you can’t nest Postboxes
- [hr]
- [h1],[h2],[h3], etc…
- [table],[tr],[th],[td]
- [list],[ul],[ol]
- [quote]
- [abstract]
- [spoiler]
- [map]
- [code]

**BBcodes that do not work as intended inside a Postbox:**

- [pre]
- [noparse]
- [nobb]

The text will show but will be styled and centered.

**BBcodes that DO WORK inside a Postbox:**

- [b], [i], [u], [o], [s] _(bold has no visible effect)_
- [url]
- [img]
- [audio]
- [video]

Plus any plain text, including emoji

If you are using Markdown formatting what you can and can’t put in a Postbox is similar, with the exception that (because of how Markdown is parsed into BBcode) you can’t have both a URL and an image in the same Postbox. You can however put inline code in a Postbox with Markdown where BBcode cannot.


## GENERAL NOTES

There is no "Auto" version of the user content stylesheets because there is no way to automatically switch the underlying Frio scheme from "Light" to "Dark/Black" to match the user's preferred color scheme as set on their operating system.

## CONTRIBUTING

To make maintenance easier the line numbers between the "Light" and "Dark" stylesheets have been synchronized. So if you make a change in one file you can find the same line in the other and make the change there too, if needed, or add comment lines to keep the line numbers the same.

These are client-side user content stylesheets which means pretty much *everything* needs `!important` added to the end or it won't work. We are overriding almost all of the "Frio" theme with "Bookface."

In some places fallbacks are included to accommodate older browsers or mobile devices that do not understand more modern code. In general the target for this scheme are browsers released within the last couple of years.

Just because it looks right or works in your preferred browser or device doesn't mean it will work for everyone. **Try to thoroughly *test* your edits** in desktop and mobile Chromium-based, Mozilla-based, and Webkit-based browsers before submitting a pull-request.

## CHANGELOG:
1.8 (12 July 2025)
* * All stylesheets now have lighter font color variable.
* Added customization for drop-shadows and outer glows.
* Button rollover effects now consistent for different types of buttons.
* Added customization of color for rollover effect.
* Added customization to show/hide bootstrap tooltips.
* Added customization to show/hide main navigation buttons labels and customize each label (Note: navbar labels do not work on tablets in portrait mode, there isn't room for all of them, they do work for phones in portrait because there are fewer buttons shown).
* Added customization to change Calendar "Today" icon to text label and customize the label.
* Body now has a default font color.
* Button-link and anchor-button now adopt link color
* Muted text now uses lighter font color.
* Nav Tabs no longer have a border color (but nav tabs list items do)
* Nav Tab link colors are now consistent.
* Drop-down menus now all adopt same drop-shadow/outer-glow
* Drop-down menus now have a max-width. Any overflow text is truncated. This prevents menu from growing so wide it spills off the screen of mobile devices.
* Forms now use color variables.
* User Menus now have icons for the first few items (this has been added to the 2025 Release Candidate, but Bookface brings it to Friendica 2024.12 as well).
* Jot/Compose modal tabs appearance now consistent with second topbar tabs.
* General containers now use box-shadow instead of border for outline.
* Common Contacts photos are now round.
* Light Mode admin page submit buttons styling typo fixed.
* Profile extra links buttons restyled (were limited to 50% width of aside, text sometimes didn't fit, made those consistent width and stacked).
* Popover Hovercard styling now consistent between Light and Dark modes
* Thread font color hover effect fixed.
* Position of "More" drop-down menu on Event posts with engagement fixed.
* Modal "Close" button rollover effect fixed.
* Fixed typo in styling for #profile-jot-wrapper
* Verified checkmark on Profile URL restyled.
* Responses restyled to only show counts and reveal popover list of who responded on mouseover/touch.
* Tag Cloud colors now set by CSS variables.
* Message Preview media list now styled.
* Action Button Labels now adopt global font family variable.
* Fixed Auto selected menu color in light mode

1.7 (06 May 2025)
* Fixed "New Message" button not being very obvious [Issue #24]
* Fixed Profile Pics and Cover Photos not working in old iOS browsers [Issue #26]
* Moved Postbox styles to end of stylesheet
* Minified Postbox CSS
* Added Postbox v1.1 styles
* Styled Item Responses (part of Issue #25)
* Action buttons (except Comment and Quote) you've interacted with before now adopt accent color [Issue #25]
* Fix for disabled Action Buttons
* Fixed a breaking typo and repositioned some code to sync stylesheet line numbers.
* Fix(?) for slow-loading secondary toolbar in Safari
* Fix for expanded engagement list link color.

1.6 (25 Mar 2025)
* Fixed HR rule in posts [Issue #13]
* Fixed notification profile pics so they are round [Issue #14]
* Fixed Post and Comment background colors [Issue #15]
* Made Post and Comment background colors configurable by CSS variables
* Fixed Post-in-Group/Mention button alignment [Issue #16]
* Fixed double underline on Compose active tabs [Issue #17]
* Fixed double Compose tabs issue on mobile [Issue #18]
* Fixed Accept Contact button [Issue #19]
* Fixed misaligned close button [Issue #20]
* Cleanup of Compose mobile drop-down button and menu
* Fixed unstyled Photo Edit Submit button 
* Intro action button apperance fixed [Issue #19]
* Fixed misalignment of Cancel/Submit request buttons [Issue #22]
* Additional fix for "Post in Group" button label spacing [Issue #16]
* Made Delegation/Account Switch Profile Photos round.
* Styled profile account type box.
* Fixed mobile spacing issue on Contacts and Scheduled Posts pages 
* Fixed "More..." dropdown menu rollover text color for Dark Mode 
* Fixed little vcard text color 
* Fixed hovercard width wider than narrow phone screen.
* Added support for new Postbox feature.
* Jot Plugins toolbar alignment fix.
* Fix for post status overlapping network link/icon [Issue #23]

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