################################################
Alter NLU Console Features and Data Manipulation  
################################################

================================================
Interactive UI to build and manage training data
================================================

	.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/alter-nlu-ui.gif   
	   :align: center

**Intent : Create, Modify, Delete intent and intent specific example sentences.**
We give filter functionalities for intent name and intent specific training sentences to help user modify the data quickly.
We also give the search entity functionality in the entity selection dropdown when selecting from the  training sentences.

**Entity : Create, Modify, Delete entity and entity specific reference value and synonyms.**
We give filter functionalities for entity name, reference value and entity specific synonyms to help user modify the data quickly.

	.. note::
		Whenever an entity is tagged in the sentence, it is automatically mapped in the synonyms of the corresponding reference value.

		Also, if you change the ‘Reference Value’ in the entity section the same will be reflected dynamically in the intent section, and vice versa.

==========================================================
Get real time Report of training data if there’s any issue
==========================================================

A dedicated reports page which gives you the insights of all the errors and warnings that might affect the training of the bot or make it perform less efficiently.

-	Intent Distribution in the form of a pie chart.
-	Figuring out the intents that require more training sentences.
-	Listing out the limitations in the entity section.
-	Examines the training dataset to extract the untagged entities.
-	Captures repetition of training sentence.

=================================================================
Download the training dataset in 2 formats - Alter NLU & RASA NLU
=================================================================

The download button will get activated only when user meets the below threshold requirements -

1. Each intent must contain at least 3 unique training sentences.
2. Each entity reference value must have at least one of the synonyms tagged in any one of the intents' training sentences.
3. There should never be multiple intents containing same training sentence(s).
4. The number of total intents must be at least 2 to allow downloading of training data.

Once you have rectified all the errors, you will be able to download the dataset JSON in both — the Alter NLU or the RASA format.

	.. note::
		If you are using RASA NLU, you can quickly create the dataset using Alter NLU Console and Download it in RASA NLU format. We have updated our console for hassle free data creation which is less prone to mistakes.

	.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/download-format.png   

=================
Data Manipulation
=================

To maintain the dataset standards we apply dynamic algorithims to perform data manipulation in an efficient manner. Below is an example to illustrate how we are manipulating your training data for better accuracy.

	.. note::
		Any modification made in the entity section is modified dynamically in the sentences in the intent section, and vice versa.

Let us suppose we have create an entity "brand" which has the below data:

	.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/brand-synonyms.png   

From the image we can make out that the Reference Value - lenovo has synonyms - inspiron, thinkpad etc, while the other entry is "dell" which holds "vostro", "chromebook" etc as synonyms.

Now, in the intent section, I train for the phrase - "I want an Inspiron". And for other similar phrases, I tag the word "Inspiron" with "lenovo" reference value. 

	.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/example-1.png   


Later, while examining my created entities, I realize that I have tagged "Inspiron" which is a variant of dell to lenovo. Therefore, I delete the synonym value from lenovo and add the "Inspiron" synonym to dell reference value. 
Now, our code dynamically judges the modification made and update the "Reference Value" to "dell" in all the sentences present in the intent section.



