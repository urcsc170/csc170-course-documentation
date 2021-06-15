# Lab 11: PHP Includes
*Due: Friday, June 18, 2021*

For this lab, you will take your existing website from your lab assignments and factor out some of the duplicate code, and place the duplicate code in *Server-Side Includes* using PHP.

## Step 1: Setup

*Note: this lab assumes you've been following along with the instructions correctly and you have a **start.html** file <u>and</u> your other HTML files in your **lab09** folder*

- Make a copy of your lab09 folder (*not* lab10) and name the new folder **lab11**

## Step 2: Change the files from HTML to PHP

- Change the file extensions of all the HTML files from **.html** to **.php**

Reminder: after you change the file extensions you can no longer view your web pages by simply double-clicking on the HTML files.  From here on out you are working *blind* unless you're using a **locahost**.

## Step 3: Setup the new "include" files

- Inside the **lab11** folder create a new folder named **inc**
- In the **inc** folder create two new plain text files with these names:<br>**html-top.php**<br>**nav.php**
- Open all the **.php** files (the files that used to be .html) in your code editor
- Also open the two new **.php** files from the **inc** folder in your code editor

The rest of this lab requires you to juggle a lot of open files while copying and pasting code between them. It's easy to make mistakes and mess thing up. Go slowly!

## Step 4: Replace the header HTML with a PHP Include

- Pick any one of your **.php** files EXCEPT the **start.php** file.  Copy all the code from the **doctype down to the closing head tag** and paste it into the file: **html-top.php**
  - *(Don't use your start.php file because you removed the link to the "navigation.css" file in Lab 9!)*

- Edit the code in the **html-top.php** file – update the lab number: "**Lab 9 - ...**" to "**Lab 11 - ...**"
- In ALL five PHP files (that's the four webpages, plus start.php) replace the top part (the doctype down to the closing HEAD tag) and insert a PHP Include statement that points to the **html-top.php** file 

*Refer to your notes from the last lecture regarding the syntax you need to use for the "PHP Include" statement. to point to html-top.php*

## Step 5: Replace the menu HTML with a PHP "include"

Note: doing this next step will break the "is-current" menu highlighter. That's okay. We'll fix it in a later lab assignment.

- In any of your **.php** files except the **start.php** file, copy your entire **nav** then paste it into the file: **nav.php**
  - *(You can't use your start.php file because it doesn't have a NAV element.  You removed it in Lab 9!)*

- Edit the code in the **nav.php** file: 
  - Replace every instance of **.html** with **.php**
  - Remove the `class="is-current"`
- In ALL five PHP files replace the entire NAV element with a PHP Include statement that points to the **nav.php** file 
- Although the *start.html* file didn't have a NAV element, **add the PHP Include for the nav.php file** between the HEADER and the SECTION (the section element with the class="lead").  We'll need it there for the future labs.

## Step 6: Upload your Work

When you are done with your webpage, close everything and use an FTP tool to access your account on **csc170.org** and upload your files:

- In a web browser (any), go to this address to check your handiwork:<br> **www.csc170.org/accountname/lab11/start.php**<br>(where "*accountname*" is your account name)
- If there's something wrong with your website, you need to fix it in your local files, then re-upload them to the web server and check again.

## Step 7: Report your work

- In our Blackboard section, in Lab 11, post a link to your webpage to receive credit for this Lab.