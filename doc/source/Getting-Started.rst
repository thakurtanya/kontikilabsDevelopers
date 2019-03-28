################################################
Building Chatbot Tarining Dataset with Alter NLU
################################################

The console is developed to handle multiple chatbot datasets within a single user login i.e you can add training data for any number of chatbots.

Start by creating your account from our `Alter NLU console <https://console.kontikilabs.com>`_

Upon clicking the ‘Sign Up’ button, an email is sent to the ID you provide above. You can log in on the console once you verify your identity via the email.

You can also sign in using your Facebook or Google account.

==================
Create the Dataset
==================

Upon successful login, you will be redirected to "Create Dataset" page.

Get started by creating new dataset, which requires a ‘bot name’ and the industry/vertical that your bot belongs to. Once you click on the "Add" button, the dataset gets created and the you will be redirected to "Intent Page".

=================
Create the Intent
=================

Create an intent that will capture what an end user wants to say. For example, you can build an intent “greet” using the “ADD INTENT” option.

-	Next, the "Add New Training Phrase" text area will contain simple greeting text that the user may write to start the bot conversation. Example - ‘Hey There’, ‘Hello’, etc.
-	Save the “greet” intent using the “SAVE” button on the top right corner. You can build more such relevant intents that may contain no entities, such as exit intent, etc.
-	Build an intent that will hold entities (explained in the ‘Create Entities’ section), and you can name it search_product intent.
-	In the training phrase section of the search_product intents, start writing the expected user queries. For instance, “I want a Dell laptop”. From this text, tag the information you want to extract and work upon.

========================
Create Entities
========================
-	To enable the bot to trigger the brand name (Dell) of the laptop, create an entity like, “brand_name” using the “ADD ENTITY” option.
-	The brand_name entity will contain “reference value” as the main brand name (like Dell) as well as synonyms that the user may refer to a particular brand that your chatbot endorses.
-	Tag the built entities in the intent they are meant to be handled. For instance, tagging Dell as a brand name in the training phrase section of the search_product intent.
-	You can also form reference values for an entity directly via intents. For this, you simply have to select the keyword and assign it to an entity that will dynamically come in the form of a list in the auto entity search option.
-	If by mistake you map a wrong keyword to an entity, you can delete it and map a new one anytime.
-	Finally, save your dataset.

==========================================
Analyse your Dataset with Reports
==========================================
-	This section highlights the training data that requires improvement and enhancements. It is programmed to analyse and present real-time changes required in the dataset in an easy-to-understand tabular and graphical display. If your training dataset needs work, it will be highlighted in the relevant reports. Click on the tool tip icon next to each of the section title for recommendations. Below listed are the key functions that form the Report:

	-  Illustrating Intent Distribution in the form of a pie chart.
	-  Analysing the Training Data Required by intents and entities to achieve accuracy.
	-  Pointing out Possibly Untagged Entities to inform about keywords that have been tagged as an entity in the intent, but the same keyword occurs untagged in the training sentence of another intent.
	-  Intent - Sentence conflicts table alerts about the training sentence(s) you may have added in multiple intents by mistake.
	-  Handling training bias by gg the name of intents lacking enough training expressions as compared to other intents.

=========================
Download Dataset
=========================
-	The download option will be enabled only when the health of the training dataset is good for training models. It must include the pointers listed below:

	-	Each intent must contain at least 3 unique training sentences.
	-	Each entity reference value must have at least one of the synonyms tagged under any of the training sentences.
	-	Avoid creating multiple intents containing same training sentence(s).
	-	Always create minimum of 2 intents to enable download option for your training dataset.

-	JSON format is provided for downloading your dataset.


====================
Use Git Repo
====================
-	To build your own Chatbot and integrate with Alter NLU, clone the code and follow the instructions mentioned in the ‘Readme.md’ file in the `Git repository <https://github.com/Kontikilabs/alter-nlu>`_

