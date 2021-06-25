# Lab 16: Menu Highlighter Plugin
*Due: Wednesday, June 30, 2021 (beware: overlaps with Lab 15 and Lab 17)*

In a previous lab, you factored-out your NAV element from your HTML documents and put it in a PHP Include file which broke the *current menu highlighter* feature.  In this lab, you will use a JavaScript solution to programmatically put it back using a jQuery-powered Plugin.

You will also fix a problem with the CSS files you've been adding to your website by having them installed only on the pages where they're needed, using PHP *Variables* and PHP *Echo* statements.

## Step 1: Install the Menu Highlighter Plugin

- Make a copy of your **lab15** folder.  Call it **lab16**
- In the **lab16** folder, create a folder named **js**
- [Download the **menu-highlighter.js** file (in a ZIP file)](menu-highlighter.zip), extract (unzip) the JS file and put it in the **js** folder 

Note:  The **menu-highlighter.js** file will automatically insert the "is-current" class on the appropriate menu item in the navigation.  But you have to install the **menu-highlighter.js** file on every page to make it work.  But instead of doing that on every page…

## Step 2: Create a new *include* file

- Create a new *include* file in the **inc** folder named **scripts.php** 
- In the **scripts.php** file, install jQuery (because the menu highlighter plugin uses jQuery) and then install the plugin
- Then in the appropriate place on each webpage use a *PHP Include* to insert the **scripts.php** file

*Note that on the **index** page, the jQuery installation already exists.  **You must never install the same library twice on the same page!**  So…*

- In the **index** file, REMOVE the SCRIPT tag that installs jQuery.  And then insert the PHP include that points to the **scripts.php** file in its place, *above* the other JS `<script>` tags for **SSS** and **jQuery UI**

## Part 3: Optimize the CSS Links using PHP Variables and PHP Echo statements

*NOTE: the specific instructions for what and how to edit your files are in the lecture video*

- Create a PHP variable (like **$customCSS**) in a PHP block at the top of each webpage

*Remember: you can merge consecutive PHP statements together into one PHP block. Make sure you use the correct format (...multiple lines)*

- Open your **html-top.php** include file.  Look for CSS links that are unique to some pages. Cut (delete) those custom CSS links from the **html-top.php** file and put them in the webpages where they're needed by assigning them to the $customCSS variable in the appropriate webpages where they're needed only.

*Remember to beware quotes inside quotes!  Alternate double and single.*

- Back in the **html-top.php** file, in the place where you removed the custom CSS links, add an *echo* statement to pull them back in when needed


## Part 4: Check and Upload your Work

When you look at your Lab 16 website in your browser as it's being served from your localhost (or the class web server):

- All the Include statements should work on each webpage -- each page should look normal (as if the PHP includes didn't exist)
- The plugins on the homepage (SSS, and the jQuery UI accordion) should still work
- The current menu highlighter should work again

…if not, you have some debugging to do.  Good luck!  Figure it out.

Then use your FTP software to access your account on **csc170.org** and upload your files:

- In a web browser (any), go to this address to check your handiwork: 
		`www.csc170.org/accountname/lab16`
	(where “*accountname*” is your account name)

## Part 5:  Report your work

In our Blackboard section, in Lab 16, post a link to your website to receive credit for this Lab.