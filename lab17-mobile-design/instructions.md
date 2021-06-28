# Lab 17: Mobile Design
*Due: Wednesday, June 30, 2021*

NOTE: a lot of this lab assignment is different compared to our other labs.  Instead of being written like a step-by-step recipe, you need to use **Step 2** like a checklist.  Everyone's lab website is different so what exactly you need to do will be unique to everyone.  Some of the suggestions will work as-is, and some of them won't.  You need to do whatever you need to make it work

## Step 1: Copy Lab 16

- Make a copy of your Lab 16 - put it in a folder named **lab17**
- In the **html-top.inc** file, update the TITLE tag to "Lab 17..."

## Step 2: Re-write the Website CSS

You need to make your website "mobile friendly" which, for this lab is: **375 x 667px** (the size of an iPhone 6, 7, or 8 in portrait mode); at this size your website must...

- Have no horizontal scroll bars
- Have all elements fit their containers
- Have no text that is too small to read comfortably, and there must be a lot of contrast between text color and its background
- Show images that are still recognizable for what they are, i.e. not too small
- Have navigation elements that look like buttons and they are finger-sized (easily tap-able)

## Suggestions...

Keep in mind, everyone's design is different.  Exactly what you need to do to make your website mobile-friendly depends on your design choices.

#### Meta Viewport Tag

*Everyone needs to do this...*

- Install the meta META VIEWPORT tag so it appears on every webpage in the correct location
  - Remember *where* to install it so it appears on every webpage!

#### Media Queries

- Open your **styles.css** file, **home.css** file, and **navigation.css** file for editing

- Find your "breakpoints" and then figure out what CSS you need to change using *media queries* to fix the breakage.  

   - Remember: whatever media queries you write must appear *below* the original CSS you're changing
   - When looking for breakpoints, find the first one (only) and work on fixing it before going on to the next breakpoint.

   **Example Media Queries that *might* work on your website (with some customization)...**

   Here are some examples which may or may not work for your lab website  You need to alter these examples as needed for your website:

   - The *horizontal navigation bar* might cause horizontal scroll bars to appear at some point; you would write in your **navigation.css** file the following (and fill-in the blank to specify your breakpoint):

     ```css
     @media (max-width: ___px) {
     	.main-menu ul, .main-menu li { display: block; } 
     }
     ```

     ...this will work regardless if you used inline-block, table-cell, or flex to layout your menu items side-by-side.  (NOTE: if you did not use `.main-menu` you need to use whatever *you* used)

   - You will also need to remove the styles you wrote to put the ARTICLE and ASIDE side-by-side at some point; you would write in your **styles.css** file:

     ```css
     @media (max-width: ___px) {
     	.container { display: block; } /* ...this will un-do CSS Grid on the container */
     } 
     ```

   - You will probably need to remove the styles you wrote to float your FIGURE elements because they do weird things to the text that flows around them at small viewport widths;  you would write in your **styles.css** file:

     ```css
     @media (max-width: ___px) {
          figure {
               float: none;
               margin-left: initial;
          }
     } 
     ```

   - Take a look at your *homepage*.  At small widths you'll probably need to un-do the side-by-side positioning of the elements in your "hero" element; you would write in your **home.css** file something like this:

     ```css
     @media (max-width: ___px) {
          .inner-container { display: block; } /* ...this will un-do CSS Grid on the container */
     }
     ```

#### Images

You may or may not need to do the following, depending on your images and where they're positioned in your webpages:

- Create a class that you can put on your image files to make them "flexible"


```css
.flexible {
    width: 100%;
    max-width: 200px; /* OPTIONAL; not necessarily 200 - use whatever pixel width makes sense for your images ...adjust this as needed */
}
```

- Open for editing all your webpages that have embedded IMG elements 

- Add the `class="flexible"` (or another descriptive name that you choose) *only* to the IMG elements as needed - not necessarily all of them - only the ones where it's needed, if any.

#### Other things

You need to go through each webpage in your website systematically - looking at each webpage at wide and narrow viewport widths.  Whenever anything looks funky, you need to identify what is causing the problem and you need to fix it.  Typically, you'll need to write a media query - that's your best tool in your "tool bag."  Refer to your lecture notes from the previous lecture on Mobile Design.

## Step 3: Check and Upload your Work

- When you are done with your lab website, upload your files to the usual place in your account on the class webserver


- In a web browser (any), go to this address to check your handiwork:<br>**www.csc170.org/accountname/lab17**<br>
  (where “*accountname*” is your account name)

## Step 4: Report your work

- In our Blackboard section, in Lab 17, post a link to your webpage to receive credit for this Lab.