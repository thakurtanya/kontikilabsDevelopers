##############################################
Alter NLU Features and other Data Manipulation 
##############################################

================================================
Interactive UI to build and manage training data
================================================

**Intent : Create, Modify, Delete intent and intent specific example sentences.**

We give filter functionalities for intent name and intent specific training sentences to help user modify the data quickly.
We also give the search entity functionality in the entity selection dropdown when selecting from the  training sentences.

**Entity : Create, Modify, Delete entity and entity specific reference value and synonyms.**

We give filter functionalities for entity name, reference value and entity specific synonyms to help user modify the data quickly.

	.. note::
		Whenever an entity is tagged in the sentence, it is automatically mapped in the synonyms of the corresponding entity.

		Also,

		If you change the ‘Reference Value’ in the entity section the same will be reflected dynamically in the intent section, and vice versa.

==========================================================
Get real time Report of training data if there’s any issue
==========================================================

A dedicated reports page which gives you the insights of all the errors and warnings that might affect the training of the bot or make it perform less efficiently.

-	**Intent Distribution:**
	It represents that number of intents created as shown in fig 1.3. It also represents the numerical proportions for the number of sentences present in each of the intents(count) and their respective percentages(count percent).

-	**Figuring out the intents that require more training sentences:**
	It reports the specific intents that have less number of training sentences than the threshold set i.e 3 per intent. Notifies the user with the name of the intents lacking enough training expressions as compared to the other intents in the bot.

-	**Listing out the limitations in the entity section:**
	Reports about the name of the entities which have been defined, but the user might not have formed any training sentence with it in the intent section. The other reason could be that the user might have mistakenly deleted the entity from the intent section but forgot to delete the same from the entity section.

-	**Examines the training dataset to extract the untagged entities:**
	Lists out keywords which have been tagged as an entity in intent but, the same keyword also occurs untagged in the training sentence of another intent.
	Notifies the user that they might have skipped tagging the keyword as an entity in the other intent mentioned.

-	**Captures repetition of training sentence**
	Informs about the training sentence(s) which the user might have added in multiple intents by mistake. The console alerts this to the user with an error message at the top of the reports section.

=============================================================
Download the training dataset in 2 formats - Alter NLU & RASA
=============================================================

The download button will get activated only when user meets the below threshold requirements -

1. Each intent must contain at least 3 unique training sentences.
2. Each entity reference value must have at least one of the synonyms tagged in any one of the intents' training sentences.
3. There should never be multiple intents containing same training sentence(s).
4. The number of total intents must be at least 2 to allow downloading of training data.

Once you have rectified all the errors, you will be able to download the dataset JSON in both — the Alter NLU or the RASA format.

	.. note::
		If you are using RASA NLU, you can quickly create the dataset using Alter NLU Console and Download it in RASA NLU format. We have updated our console for hassle free data creation which is less prone to mistakes.

========
Rest API
========
Supported for both training and parsing.

=====================
Continuous deployment
=====================

New model on updated data will be automatically available to parse once training completed.

=====================
The Data Manipulation
=====================

To maintain the dataset standards we apply dynamic algorithims to perform data manipulation in an efficient manner. Below is an example to illustrate how we are manipulating your training data for better accuracy.

Let us suppose we have create an entity "brand" which has the below data: image below.

					
From the image we can make out that the Reference Value - lenovo has synonyms - inspiron etc, while the other entry is "dell" and its synonyms.

Now, in the intent section, I train for the phrase - "I want an Inspiron". And for other similar phrases, I tag the word "Inspiron" with "Lenovo" reference value. Later, while examining my created entities, I realize that I have tagged "Inspiron" which is a variant of dell to Lenovo. Therefore, I delete the synonym value from lenovo and add the "Inspiron" synonym to dell reference value. 
Our code dynamically judges the modification made and update the value in the intent portion. -check-



