##############################
Building an E-commerce Chatbot
##############################

The console is developed to handle multiple chatbot datasets within a single user login i.e you can add training data for any number of chatbots.

Start by creating your account from our `Alter NLU console <https://console.kontikilabs.com>`_

Upon clicking the ‘Sign Up’ button, an email is sent to the ID you provide above. You can log in on the console once you verify your identity via the email.

You can also register and login using social sites credentials of your Facebook or Google account.

Below in the documnet are the steps that will guide you in building your training dataset.

==================
Create the Dataset
==================

Upon successful login, you will be redirected to the "Create Dataset" page.

Get started by creating new dataset, which requires a ``bot name`` and the ``industry/vertical`` that your bot belongs to. Here, we are going to name our bot as - "ecomm-bot" and the domain will be "E-commerce".
Once you click on the ``Add`` button, the dataset gets created and you will be redirected to "Intent Page".

=======================================================
Building no keyword Intents (Intents with no entities):
=======================================================

The intents like “greet” and “exit” are the generic intents every bot should handle. Besides these intents, build other intents you plan to include in your chatbot. Like, I have included “ongoing_offers”. Follow the steps below to create the “ongoing_offers” intent :

-	Create an intent using the “ADD INTENT” option.
-	Next, in "Add New Training Phrase" text area write simple user queries asking about the current sales, vouchers in our e-commerce chatbot. Example - ‘any offers?’, ‘do you have any voucher’, etc.
-	Save the “ongoing_offers” intent using the “SAVE” button on the top right corner. 

This intent will hold all the user queries asking about the current sales, vouchers in our e-commerce chatbot.

Remember to train the dataset with expressions which contain words like — sales, vouchers, etc, as these words will keep the “ongoing_offers” intent unique from other non-keyword intents.

==================
Building Entities:
==================

The e-commerce chatbot should be trained to handle queries like:

User says : I want to buy **apple** **mobile** worth **60K**.

So, I plan to create 3 entities that will extract the:
	-	brand
	-	product-type and
	-	price

from the user query.

-	Create an entity "brand" by using the “ADD ENTITY” option.
-	The "brand" entity will contain "Reference Value” as the main brand name (like apple) as well as synonyms that the user may refer to a particular brand that your chatbot endorses.
-	Similarly cretae other entities, add the ‘Reference Value’ and their synonyms. Like a user can write ‘loui vuitton’ (our Reference Value) as ‘LV’ or ‘Louis Vuitton’ (the synonymns for ‘loui vuitton').
-	Similarly, create values and synonyms for the other fields and finally, save your dataset.

===============================
Building Intents with Entities:
===============================

For queries as stated in the above section, dataset should have an intent that will store all the possible user queries from which the bot should be extracting the entities (like “search-product” in this case). As stated in the image below.

Create an intent with the name "search-product" and go to the training phrase section of the intent and start writing the expected user queries. 
For instance, “I want to buy **apple** **mobile** worth **60K**”. From this text, tag the information you want to extract and work upon.

For the developers ease we have built the console in such a manner that each ‘Selected Value’ in the intent section can be linked to a ‘Reference Value’ of your choice.

Like in the images below, you can see in the intent section:

Selected Value : 60k, 2k both have same ‘Reference Value’ i.e price-range

In the entity section, every price-range example is defined in the same “Reference Value”

.. note::
	If you change the ‘Reference Value’ in the entity section the same will be reflected dynamically in the intent section, and vice versa.

===========================================================
Analysing the loopholes in the dataset : The Report Section
===========================================================

Once you are done building the dataset, move to the Report Section which will analyse your dataset for all intents and entities in real-time and notify the errors and warnings that need to be addressed for the accuracy of the chatbot’s response.

Click on the tool tip icon next to each of the section title for recommendations. Below listed are the key functions that form the Report:

-  Illustrating Intent Distribution in the form of a pie chart.
-  Analysing the Training Data Required by intents and entities to achieve accuracy.
-  Pointing out Possibly Untagged Entities to inform about keywords that have been tagged as an entity in the intent, but the same keyword occurs untagged in the training sentence of another intent.
-  Intent - Sentence conflicts table alerts about the training sentence(s) you may have added in multiple intents by mistake.
-  Handling training bias by gg the name of intents lacking enough training expressions as compared to other intents.

Once you have rectified all the errors, you will be able to download the dataset JSON in both — the Alter NLU or the RASA format.

.. note::
	If you are using RASA NLU, you can quickly create the dataset using Alter NLU Console and Download it in RASA NLU format. We have updated our console for hassle free data creation which is less prone to mistakes.

===============================
Alter NLU Updates : v1.0.0-beta
===============================

**Intent Model**

We have used Convolutional Neural Networks (CNN) based model to capture the intent. Further, the use of custom validation algorithm and matthews correlation coefficient as accuracy metric makes the intent model robust.

.. note::
	The user has to train the sentence for one of the synonyms and the remaining are handled by our console code.

**Entity Model**

In this version we have replaced the previous Flashtext and FuzzyWuzzy based entity extraction method with a CRF based Entity Recognition model.

===============
Build Your Bot:
===============
Go to Git Repository from the link below:

`https://github.com/Kontikilabs/alter-nlu/tree/v1.0.0-beta <https://github.com/Kontikilabs/alter-nlu/tree/v1.0.0-beta>`_

Next, go through the README.MD file and start executing the steps as mentioned.

**Below is an example along with a detailed explanation of the benefits of using this new pipeline.**

**Elaboration of the above chatbot response:**

-	According to the context of the user query, the model successfully recognises the search product intent along with the confidence score.
-	This model handles out-of-vocabulary words to some extent. 
	The term ‘out-of-vocabulary words’ refers to those words which are not present in the training data of the chatbot.
	For example, If you take a look at the example above, the parsed_value “799k” is not present in the training data used to train the “ecomm-bot” whose entity has been recognised accurately as “price”.
-	The CRF model was able to recognise the entity accurately, because it considers the sentence structure of the user query.
-	If you’re familiar with other bot frameworks, then you might not have come across a key like “parsed_value”. The main goal	  to add this key in the response is to assist developers to directly use the “parsed_value” if needed. 
	In the example above, the developer might need the exact value of entities such as “price” that is in the user query for further usage. In this case it’s “799k”.
-	Also, if you’re an existing user of Alter NLU it needs to be pointed out that the “category” key in the response has been renamed to “name”.









