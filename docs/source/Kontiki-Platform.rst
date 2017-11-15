##########################################################
Bot Building With Kon-Tiki Labs : The Kontiki Platform
##########################################################

.. image:: https://s3-ap-southeast-1.amazonaws.com/ktlplatform-assets/lafK8qhq-a.png
   :target: http://app.kontikilabs.com/login
   :height: 438px
   :width: 735px
   :alt: Developers

Build delightful conversations for your bot with `The Kontiki Platform <http://app.kontikilabs.com>`_, that will let your author add:

   -  Real time articles
   -  QR buttons
   -  Videos 
   -  Gifs, images
   -  Text, etc.

in a chat like format, thus making their work easy.

===============
Getting started
===============

Start by creating your organisation account from our `Kontiki Platform <http://app.kontikilabs.com>`_

image

Upon clicking the ‘Create Account’ button, an email is sent to the ID you provide above. You can log in on the platform once you verify your identity via the email.

.. note::

   Once logged in, for security reasons we take some time to approve accounts. You will be verified via an email when your account is approved by our team.

=====================================
Single CMS platform for multiple bots
=====================================

Upon successful login, you will be redirected to the ‘Bot’ page from where you can add multiple bots by clicking on the '**Add new bot**' option. 

image

Once you click on the ‘**Add new bot**’ option, a popup appears, asking for the following details:
      
   +-------------------+-----------------------------------------+
   |**Name of the bot**| Give your bot a user-friendly name.     |
   |                   |                                         |
   |                   | Make your bot available to your users by|
   |**Platform**       | choosing the desired platform bot users | 
   |                   |                                         |
   |**Domain**         | The type of content that the bot will   |
   |                   | hold.                                   |
   +-------------------+-----------------------------------------+

image

When you click on the save button, you are redirected to the bot Dashboard. 

================================
Dashboard : Your bot at-a-glance
================================

image

The Dashboard gives you a glimpse of everything on the Kontiki platform. The functionality of each individual feature in the Dashboard is explained further on in this document.

=========================================
Channels : Fetch real time content object
=========================================

Bots need to hold vast quantities of content for your users. They need to satisfy user demands for multiple types of content.

Keeping this in mind, our platform offers the ‘**Channel**’ feature.

With channels, you can make your writer's job easy since all they have to do is add a ‘**keyword**‘ and the desired flakes are created automatically from renowned web sources like Google and Event Registry.

Follow the document below to see how channels work.

-  **Add New Channel**

   image

   Click on the ‘Add New Channel’ option and a popup appears:

   image


   Fill in all the required fields:

         +----------------+---------------------------------------------------+
         |                |                                                   |
         |**Channel Name**|An apt name for the channel.                       |
         |                |                                                   |
         +----------------+---------------------------------------------------+
         |                |                                                   |
         |**Category**    |The group that your channel falls under.           |
         |                |                                                   |
         +----------------+---------------------------------------------------+
         |                |                                                   |
         |**Keyword**     |Enter words that indicate what content you want to |
         |                |retrieve content from the web. You can add multiple|
         |                |keywords by clicking on the ‘Add Keyword’ option.  |
         |                |                                                   |
         |                |                                                   |
         +----------------+---------------------------------------------------+
         |                |                                                   |
         |**Websource**   |The source from where bot content will be Retrieved|
         |                |At present, 2 web sources are integrated           |
         |                |                                                   |
         |                |-  Event Registry                                  |
         |                |-  Google News                                     |
         |                |                                                   |
         +----------------+---------------------------------------------------+


   Click on the ‘**Next**’ option to view the following:


   image

   **‘Set Interval Duration’**, will run your channel automatically after the set time interval to retrieve content from the web source. 
   
   If you set interval duration to ‘1’, then new content will be added to your **drafted flakes** every one hour.
   
   Click on ‘Submit’ to create your channel.

   image

   Each time you run the channel manually with the ‘**Run**’ button, new flakes are retrieved from the web source and added to the draft flake section.

   .. note::

      All channel content retrieved is automatically saved as draft flakes.



-  **Disable A Channel**

   You can, at any time, ‘Disable’ or edit channel details by clicking on the ‘Edit button’.

   Once you disable the channel, no more content will be added to the drafts.

   Image

========================================
Flakes : Your content object for the bot
========================================

In addition to retrieving content from web sources, your writers can also use the Kontiki platform to create and manage bot content. 

**Flakes represent pieces of information that your user will see when they interact with the bot. Think of flakes as containers - with a title, description and cover image. When a user interacts with a flake inside a bot, its contents are used by the bot in a conversational manner.**

The flake comprises your bot’s ‘**content object**’. The platform holds 3 types of flakes, which also indicate your content object status:

      +--------------------+-------------------------------------------------+
      |                    |                                                 |
      |**Draft Flakes**    |Add your raw flake here.                         |
      |                    |                                                 |
      |**Published Flakes**|Publish the flake to make it available on the bot|
      |                    |                                                 |
      |**Scheduled Flakes**|Plan your content by setting an interval         |
      |                    |                                                 |
      +--------------------+-------------------------------------------------+

The custom content object goes into draft flakes first. Once a flake is drafted, the writer can change its status to ‘publish’ or they can ‘schedule’ it.


   Image

   a) *Draft flake*

      Enter into the ‘**Draft Flake**’ option to create your first bot content object.

      Upon clicking on the ‘**Add Flake**’ button, a popup appears, asking you to fill in the following 2 mandatory fields for your content object:

         +---------------+--------------------------------------------+
         |               |                                            |
         |**Title**      |Choose a short title for your content object|
         |               |                                            |
         +---------------+--------------------------------------------+
         |               |                                            |
         |**Description**|Summarize your object content here.         |
         |               |                                            |
         +---------------+--------------------------------------------+

      Upon clicking the ‘**Submit**’ button, your content object will be saved as a draft with a unique ‘**flake ID**’, which is displayed in the ‘**ID**’ field of each flake.

      -  Inside the Draft Flake:

         A flake stores information like :

         +---------------+----------------------------------------------------------------------+
         |               |                                                                      |
         |**Author**     |The user who creates the flake.                                       |
         |               |                                                                      |
         |               |                                                                      |
         |**Source URL** |The content object URL. This plays a crucial role in case of channels.|
         |               |                                                                      |
         |               |                                                                      |
         |**Category**   |The bracket in which your content falls.                              |
         |               |                                                                      |
         |               |                                                                      |
         |**Tags**       |Labels for your content.                                              |
         |               |                                                                      |
         |               |                                                                      |
         |**Image**      |A featured image that represents your content object.                 |
         |               |                                                                      |
         +---------------+----------------------------------------------------------------------+

         .. note::

            If you edit any of the above, you will need to save the changes by clicking on the ‘**Red Floating Button**’ and choosing the desired flake status.

      -  The Content Object:

         The ‘**points**’ section of the draft flake is where your content goes.

         The moment you click on the ‘**Add points**’ placeholder, ‘**Take a note**’ text area appears where you start building your conversation.

         Click on the ‘**Add**’ button to save your conversation.

         Image

         You can **add multiple QR** buttons with the text, using the ‘➕’ icon, displayed below the conversation you added above. On clicking on the icon a popup is prompted, requesting the following details:

            +----------+-------------------------------------------------------------------+
            |          |                                                                   |
            |**Name**  |The text you want to display to the user.                          |
            |          |                                                                   |
            |          |                                                                   |
            |**Action**|Differentiate QR buttons with the activity name they are built for.|
            |          |                                                                   |
            +----------+-------------------------------------------------------------------+


         Image : Image

      -  Drag & Drop:

         Reshuffle your already written content points by dragging and dropping them at the place you want.

         Using drag and drop, you can also add a new content point in between existing points as follows:
         
            -  Append a new point at the end.
            -  Drag it from the ‘**vertical dots**’ present at the left side of the points.
            -  Drop it in between the points you want to display in your new chat bubble.
            -  And, your flake is automatically saved.


      - Editing Content:

         You can alter the following in your flake content by clicking on the point you want to edit:
         -  The text of the points
         -  Videos, images or other graphics
         
         Once you are done with the editing, click on the ‘save’ button to display your changes on the bot. 
       
         To **update the QR button text**, click on the button you want to edit, a popup is prompted, fill in your new text in the ‘name’ field, and click on the update button to save the changes.

      -  Deleteing Content:

         Click on the point, followed by the ‘trash can’ icon to delete the point from the conversation.

      -  Categories:

         Organize your flakes by adding apt categories. This helps you form a group of flakes sharing a particular kind of information. 
         
         To **create a category**, click on the ‘➕’ icon. A popup is prompted, requesting the following details:
            
            +---------+-----------------------------------------+
            |         |                                         |
            |**Type** |The class to which your category belongs.|
            |         |                                         |
            |         |                                         |
            |**Value**|The value of your category.              |
            |         |                                         |
            +---------+-----------------------------------------+
         
         Click on the save button to store the actions.

         To **add category** to the draft, start typing the category initials you created above and the value is detected automatically with the help of the ‘Auto search’ feature.

         Image

         You can view the list of categories your bot holds, in the left navigation bar of the platform.

      -  Tags:

         Label your flakes with apt words that capture the gist of the content. To create tags, follow the same steps as for creating a ‘category’.



      -  Filters, Search, & Settings:

         -  Filter : Narrow down the display of your flakes with the ‘category’ or ‘channel’ filters.

         Image

         -  Search : Save time and use the search bar to locate flakes.

         -  Settings : View your bot and organisation details by clicking on the ‘settings’ icon ‘⚙’.


   b) *Publish flake*

      Mouseover on the red floating button on the right hand corner of your screen.

      Out of the 3 options provided, click on the ‘Publish’ icon and your flake content will be made available to your bot users.

      Image

   c) *Schedule flake*

      Image

      With schedule status you can add an interval to the flake. 

      Once you ‘save’ the set date and time, the flake status automatically changes to ‘published’, making the content available to users at the scheduled time.

      .. note::

            Click on the red floating button to select the desired status (publish, draft, schedule) whenever you change anything except the points 
            (i.e Description, Tags, Titles, Category) in the flake. 

=======
Log out
=======

   You can logout from the platform at any time by clicking on the profile icon on the right hand corner of your screen.
























