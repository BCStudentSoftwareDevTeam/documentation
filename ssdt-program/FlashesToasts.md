---
title: Flashes Toasts  and Custom Validity Tags
description: 
published: true
date: 2025-07-11T13:46:05.356Z
tags: 
editor: markdown
dateCreated: 2025-07-11T13:45:59.347Z
---

# Flashes, Toasts  & Custom Validity Tags
## Flashes & Toasts 
##### **This is a toast:**
![toast_foto.png](/toast_foto.png)
-	Toasts are used only when a page is not reloading (or when there is no Ajax request is sent) 
-	We implemented the Toasts only on Modals, as the appearance has the perfect placement
-	We implemented toasts in the JavaScript files of the specific template. 
-	The base function for the msgToasts looks like this
-	**function msgToast(head, body, duration=3000)**
-	Using msgToasts as an example, we can provide: 
-	**msgToast("Bonner", "Updated Bonner Requirements");**  The first parameter is the head (or the title), and the second parameter is the body or the message you would like to send to the front end. The default duration of the toast that we can alter in the function call, if wanted, is 3 seconds
##### 
**This is a flash:**
 ![flash_foto.png](/flash_foto.png)
-	A flash is a message that will appear if there is an Ajax call  and or a page reload
-	We have implemented flashes for deletion, addition, confirmation, and updating.
-	 The base function for the flash looks like this: 
-	**function msgFlash(flashMessage, status, timeout=2500, afterReload=false) {**
-	Using msgFlash as an example, we can provide: 
-	**msgFlash("Successfully added student interested in minor.", "success", 1300, true)**
The first parameter is the body or the message you would like to send to the front end. The second parameter is the status, which shows the styling of the flash, where we have (danger, info, success, and warning). The default duration of the flash can be altered in the function call, if wanted, but the base timer of the flash is 2.5 seconds. The last parameter of the msgFlash function call determines whether we want the flash to show after (which is true) or before the page reload (which is false). 
-	If you do have the last component in the flash message as true. Then you will have to call msgFlash() without any parameters so that the stored message can be retrieved and displayed on the front end after the page has reloaded. 

### Custom Validity Tags
##### This is a custom validity tag:
  ![custom_validity_foto.png](/custom_validity_foto.png)
-	We use Custom Validity Tags for required fields 
-	They are a browser-based Tag that you can customize 
-	An example of an implementation of a custom Validity Tag is: 
-	  repeatingFields.each(function() {
-	    let value = $(this).val();
-	    if (value === "" || value == null){
-	      this.setCustomValidity("Please fill out the required field"); // do these actions
-	      this.reportValidity();
-	      isEmpty = true;
-	    } else {
-	      this.setCustomValidity("");
-	    }
-	  });
-	  return isEmpty
-	First, we have to create a conditional that will check if a certain field is required.
-	If it is empty, show the Custom validity tag for the specific place provided 
-	Then we clear the custom validity to make sure we are executing the CustomValidity tag correctly. 
-	Else, we do not show a customValidity tag because there is an input. 

Event Listener for Clearing Custom Validation
-	The base function for setting up Event listeners is: 
-	function enableLiveCustomValidityClearing(selectors) {
-	  selectors.forEach(selector => {
-	    $(selector).each(function () {
-	      // Avoid rebinding listeners on already-bound elements
-	      if (!$(this).data("has-clearing-listener")) {
-	        $(this).on("input", function () {
-	          this.setCustomValidity("");
-	        });
-	        $(this).data("has-clearing-listener", true); // flag it
-	 We create this event listener because we do not want the custom validity tag to show up once a person starts writing/ adding an input into the input field. 
-	enableLiveCustomValidityClearing([".repeatingEventsField"]);
-	We call the base function for the specific class we are working with so that the event listener is then applied to the required text field. 


