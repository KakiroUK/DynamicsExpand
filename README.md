### INSTALL INSTRUCTIONS
**Dynamics case notes formatting script**
1. [Create bookmark](#create-bookmark) in browser of choice. Doesnt matter if the bookmark is blank or to an existing page as you will edit it.
2. Then rename the bookmark name to something like "DynaFix: Notes"
3. In the URL/location field remove the current value and copy and paste the below line:  
```
javascript:(function (){document.getElementsByTagName('head')[0].appendChild(document.createElement('script')).src='https://js.kakiro.online/DynaFix.js?%27+Math.random();}());
```
5. Now when viewing a case in Dynamics that has quite a few notes to read, click the bookmark link and give it a couple of seconds to do its magic. Voila!
6. Don't like the note colours? [Change colours](#change-note-colours)

**Quick open case using case ref eg INC111111**
1. [Create bookmark](#create-bookmark) in browser
2. Then rename the bookmark name to something like "DynaFix: Open Case"
3. In the URL/location field remove the current value and copy and paste the below line:  
```
javascript:(function (){document.getElementsByTagName('head')[0].appendChild(document.createElement('script')).src='https://js.kakiro.online/DynaOpen.js?%27+Math.random();}());
```
5. Now when on Dynamics you can click "DynaFix: Open Case" and type the INC111111 reference number to open that case regardless of status or view you are in

**Script Updates
The script files above are references to hosted versions of the script so any version upgrades will automatically be applied

**DynaFix Notes Version History**

v1.16.01
- Added fixes for the incident DynaFart. The one where they reverted loads of changes they made to fix an issue
- Loads secure and private notes direct from the web api
- FIX Wordwrap and linebreaks in note divs

v1.15.04
- Client portal access is now restricted to selected Teams
- Disabled client portal link on request from Management (working on bringing this back with some additional security)
- Formatting changes. Moved the Case Ref, Company and case title out of the window title bar and moved it below also added contact name. The are now selectable so can copy and paste.
- Each element of the above text has a different colour to help differentiate them.
- FIX the original case view now scrolls to top after DynaFix is run
- FIX an issue with attachments being in a never ending loop causing browser stability issues
- FIX an issue with attachments not creating the correct url. This appeared to be due to the case title changing.
- Added DynaFix Notes title to popup window with version number

v1.14.08
- Added client portal links to case screen next to contact and from the notes popup
- Added functionality to the above client portal link so it forwards you to the case category in the client area
- Some style changes to the Filter and Client Portal bar
- FIX Prevent notes popup being moved out of view completely
- FIX Multiple contacts with same name on same account but one some without ANS portal access
- Show Error if unable to generate client portal link

v1.13
- Changed scripts to load an external .js file from web host to ensure going forward everyone is using the same latest version
- Added support for customising note colours from bookmark script

v1.12.03
- Made note colours easily configurable by adding them as variables at top of page
- Checks to see if other engineers have case open and displays an alert
- Added in failsafe for attaching files limit 100
- Added filter field at top of notes popup
- Fix with multiple clicking bookmark  on same case adding extra text to note title
- Added some base encoding to sensitive text

v1.11
- Changed note colours so they arent so in your face (seperated as a new branch)

v1.10
- Buggy experimental code that didnt work don't use

v1.09
- Added from the popup note screen uploaded attachments are now clickable to open them rather than using "Glass 2 Files" tab
- FIX Added some pretext " - " before "Created on" to note title so its format is cleaner
- FIX Some if statements checking if an element existed werent working
- Removed the funtionality that moves the on hold section to top of page as theres a bug with it that needs sorting

v1.08
- Description at end of notes now styled
- FIX emails from us sometimes missing the email body because they appear in an iframe and contents aren't copied over
- FIX Removed some more icons
- FIX Notes popup div gets focus and allows keyboard scrolling
- Move created on line to end of Note Type to reduce screen realestate of notes

v1.07
- Fix for emails from us being wrongly colour coded
- Removed html tags from email updates to make those notes more readable
- Color of notes popup title bar changed

v1.06
- Added case note title ie Secure Update, Private Update, Glass as BOLD

v1.05
- Added red colour for private cases
- Fixed colour for customer emailing us being blue instead of grey
- Changed all text to white and made ANS responses dark grey so it works well for either Dark mode or Classic themed Dynamics

v1.04
- Move "On hold" section above "Work in Progress"

v1.03
- Remove icons just above note as it just extra padding
- Remove View less below notes as in this popup div its not needed
- Notes popup div now inline with messenger chat bubbles format as in blue for you (ANS) and default dark grey to Customer

v1.02
- Fix for firefox
- Added some border colors to divs so the popup div is more easily viewable on Dynamics white color theme

V1 Features
- Automatically clicks "load more" to get all notes on screen at same time
- Automatically clicks "expand all" so you can see the full case notes
- Scrolls to top once finishing all the auto clicks
- Removes all notes from ANS support as these are usually just useless/duplicate information when wanting to read notes
- Uses the "Search Articles" div that appears on every case and instead makes this a popup div thats draggable and has close button. This div now displays all the notes over the case screen which is below for easy reference.
- Close button changes color when hovering
- Popup div title bar allows dragging
- After 100 seconds of clicking "load more"'s then it aborts the script this is a failsafe to stop it running forever
- Added Case title, ref no and customer name to popup title bar
- Added Description to end of notes so it appears in chronological order

### Change Note Colours
Don't like the note colours? https://www.w3schools.com/colors/colors_picker.asp choose your colour and copy either hex code, rgb or colour name if it exists in between the "" for custom colours below, then paste it into the bookmark for "DynaFix: Notes"
```
javascript:(function (){document.getElementsByTagName('head')[0].appendChild(document.createElement('script')).src='https://js.kakiro.online/DynaFix.js?%27+Math.random();
var custom_CUSTOMER_COLOUR = "#424242";
var custom_SUPPORT_COLOUR = "rgb(24, 119, 242)";
var custom_PRIVATE_COLOUR = "FireBrick";
}());
```
### Create Bookmark
Chrome instructions:
1. Press ctrl+shift+b if your bookmark bar is not already showing.
2. Right click anywhere in empty space of the bookmark bar at the top under the address bar, click "Add page"
3. Change the name (this can be of your choosing)
4. Paste the contents of the script file above into the URL field
5. Click Save

KNOWN BUGS
- In rare occasions the note popup title bar is not draggable however if you click the bookmark again it fixes it
- Also some rare occasions the "Load More" at the bottom of page might not complete them all again clicking bookmark again should solve

FEATURES TO ADD
- Load case notes direct from web api?
- Add Secure/Private notes from DynaFix div
- Case list by updated date?
- Client Portal - Check subcatgeory of ticket and move you to the correct location in client portal?
- Client Portal - Check description/private note for i-******** and change text to link
- Ecloud VPC - Check private note for instanceid text then get IP, username, password and add it to private note. This would need VPC API access.
- Client Portal - Extra link to login with primary contact instead of current contact?
- Remove email warning and make sure email content text is white also Example INC634090
- Hide undeliverable messages
- Check if URL alert and where it resolves and give it as info in case
- Turn ANS Case ref's into links in descr and notes ie inc123456 becomes a link to the case
- Add additional jquery script location for redundancy
- Sometimes open case bookmark doesnt work and think its due to Dynamics timing out check to see if I can get an error to display
- Add quick way to delete filter eg x button
- Add a copy button next to Ref, company and contact
- Beautify alert that someone else has this case open already
- Add filter BUTTONS to filter on types of notes
- Convert this into a chrome extension so it loads automatically when viewing cases or alternatively displays a button on case view page that when you click does the same as the bookmarklet

Additional Notes:
- If you want to view the code paste it into a javascript editor like notepad++ and then from the menu bar click (Language > J > Javascript) this will colour code everything to make it more readable
- Can I make a quick way to progress a case when you open it initially?
- Add refresh bookmarklet for the main case screen to click refresh every 60secs?
