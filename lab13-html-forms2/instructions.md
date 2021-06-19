# Lab 13: HTML Forms, Part 2
*Due: Monday, June 21, 2021*

For this lab you will integrate the non-working HTML form from Lab 12 into your lab website and power it with a PHP script.

## Step 1: Copy Lab 11

- Make a copy of your Lab 11 files (*not Lab 12!*) and put them in a folder named **lab13**
  - Note: the best way to work with this lab (and all future labs) is in a *localhost* using a WAMP or MAMP server because your labs use PHP Includes

## Step 2: Create a New Webpage for your HTML Form

In this step you will use an existing webpage as a template for a new webpage.

- In your **lab13** folder, make a duplicate copy of any one of your existing webpages - any of them *except* your start.php file - name it: **contact.php**

- Edit the new **contact.php** file:

  - Delete the ARTICLE and ASIDE elements and all their contents
  - The only elements left inside the file should be:

  ```php+HTML
  <?php include "inc/html-top.php"; ?>
  <body>
  <div class="container">
    <header>
  	  <h1...
  	  <div...
    </header>
  <?php include "inc/nav.php"; ?>
    
  </div><!--.container-->
  </body>
  </html>
  ```

  *The dots ("...") next to the h1 and div above indicate there's more there; don't literally use "..."*

- Get your Lab 12 file, **contact.html** and copy-out the FORM element (all of it, from the opening FORM tag to the closing FORM tag) and paste it into the new **contact.php** file, directly under the *nav.php* statement

- Edit your **inc/nav.php** file:
  - Add a new menu item (a list item) that points to the new **contact.php** file
  - Have the text for the link say something like "Contact Us" ...or something like that
  - Save and close the **inc/nav.php** file

## Step 3: Add Styles to the HTML Form

- Edit the **contact.php** file:

  - In the opening FORM tag change the **action="#"** attribute to:<br> `action="form-processor.php"`
  - Add `class="full-width"` to the opening FORM tag

- Edit the **css/styles.css** file:

  - Add a class named **.full-width** to the group selector that sets the grid-column to 1/3 like this...

    ```css
    header, footer, .lead, nav, .full-width {
    	grid-column: 1 / 3;
    }
    ```

- Save and close the **css/styles.css** file

- Edit the **inc/html-top.php** file:

  - Change the TITLE to say "Lab 13..." instead of Lab 11

  - Add a new LINK to a new stylesheet (that you'll create next) like this

    ```css
    <link rel="stylesheet" href="css/forms.css">
    ```

- Save and close the **inc/html-top.php** file

- Create a new file in the **css** folder named **forms.css**

- Edit the new **css/forms.css** file

  - Here you can add whatever styles you want to make your HTML form look like it's a part of your website.  At the bare minimum, try these styles...

  ```css
  form { 
  	margin-top: 30px; /* ...adjust as needed */
  }
  textarea { /* these are suggestions... */
  	width: 100%;
  	height: 100px;
  }
  ```

  ...add more styles as you'd like.

- Save and close the **css/forms.css** file


## Step 4: Create the Form Processor File

- Make another duplicate copy of any one of your existing webpages - any of them *except* start.php or contact.php - name it: **form-processor.php**

- Edit the new **form-processor.php** file:

  - Delete the ARTICLE and ASIDE and all their contents

- Under the *nav.php* statement, add a MAIN element with an attribute: `class="full-width"` and add some content like this:

  ```php+HTML
  <main class="full-width">
    <h2>Thank You <?php echo $name; ?></h2>
    <p>Go back to <a href=".">the home page</a>.</p>
  </main>
  ```

  ...notice the variable `$name` used above.  That assumes you will create a variable like that in your PHP script.  If not, you need to use whatever YOU used.  (E.g. maybe you called it, "fullname" or something like that?)
  
  ...you can also edit the content used above.  Change/add words to make it more sensible for your website - whatever you want.

## Step 5: Add and Edit the Form Processing Script

- Download the ZIP'd file: [form_processing_script.zip](form_processing_script.zip) and extract the text file named, **FORM_PROCESSING_SCRIPT.txt** 
- Copy all the text out of that file (113 lines) and paste it in the TOP of your **form-processor.php** file, *above* the PHP **inc/html-top.php** statement on Line 1
- Fill-in the blanks in the PHP form processor as demonstrated in the last class.
  - Make sure the superglobals match your `name=""` attributes from your HTML form exactly (remember: case sensitive!)
  - Create variable names for the incoming data that make sense; typically you can use the same word(s) you used in the superglobals, for example `$name = $_POST['name'];`
  - Don't forget to add the value attributes for the checkboxes and radio buttons in the HTML form!
- Save and close the **form-processor.php** file

## Step 6: Upload, Test and Report your Work

Remember: even though you may be  running a local webserver (WAMP or MAMP) the PHP `mail()` command *won't* work because you don't have a mail server on your computer.  You can only test your **contact.php** file when it's running on the class web server because it has a mail server on it.

- FTP your **lab13** folder to the class webserver 
- In a web browser test the **contact.php** page:<br> **www.csc170.org/accountname/lab13/contact.php**<br>(where "*accountname*" is your account name)
- After filling out the web form, pressing the submit button should take you to your **form-processor.php** webpage where you'll see the "Thank you " ...with the name you typed in the previous webpage there.
- A few seconds later, you should receive an email with the contents of your labels and web form data
  - If not, check your **lab13** folder for the existence of a file named **error_log**; open it and read it.  It will point you to the location(s) in your form processor where there is a mistake.
- If it's all working as expected, go to our CSC 170 section of Blackboard, and in Lab 13, post a link to the **contact.php** webpage to receive credit for this Lab.
