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

Additional Notes:
- If you want to view the code paste it into a javascript editor like notepad++ and then from the menu bar click (Language > J > Javascript) this will colour code everything to make it more readable
- Can I make a quick way to progress a case when you open it initially?
- Add refresh bookmarklet for the main case screen to click refresh every 60secs?
