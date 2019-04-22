#######################
Understanding Alter NLU
#######################

=======
Intents
=======

Intents are what you expect users to say and what are their intentions. It describes the context of the expression that the user says or in simple terms what the user probably meant to say.

For Example :

		If the user types : 
		*I want to read politcal news*
		
		His intent here is to retrive a bunch of politcal articles.

There are 2 type of intents:

	-	First, which do not map to any keyword, but are simple and direct phrases like an intent named “greet” which will hold training phrases as :: 
									
			“Hey there” or  “Hi”.
									
	-	Second, which can have multiple or single keywords (entities) in the training phrase which we want to extract from the user query as demonstrated in the image below.

		.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/intent-mapping.png   

========
Entities
========

Entities describe the piece of information you would want to extract from the expressions/messages of the user.

Like in the image above, the "price", "product-type" and "brand" are the 3 entities in our console that will be mapped to their respective “Reference Value“ and “Synonyms“ values.


**How Intents and Entities work to produce maximum output with relatively less training data?**

	-	*The intent | sentence ratio. Manage inventory of synonyms with entities*
		
		The primary obstacle in building an intelligent chatbot is interpreting the varied patterns and expressions that a user may adopt when posing a query and training it for all possible approaches.

		Unlike a few other NLP applications for training bots, we try to provide optimum results even when there are fewer training samples. However, as a rule of thumb, the more you train your bot, the better the outcome

		.. note::
		   For good results, the console requires a minimum of 3 training samples per intent. Also, Alter NLU needs only a single synonym training sample for each entity reference value.

		To ensure that the training stats are appropriate, we show alerts and warnings in the reports section of the console.

		For example, if a user wants to buy a laptop with certain specifications, he or she may pose a query like:

			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/query-1.png   

		The same query may be framed differently like:

			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/query-2.png   


		Our console allows you to maintain an inventory of related words such as “laptop” and “PC” in the form of entities, and train it only for a single synonym. This is illustrated below:

			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/synonym-value.png   

		So, all you need to do is add one expression in the intent containing any one of the synonyms and your bot is good to go.

	-	| *Using Natural Language Processing for entity extraction*

		Our engineers have incorporated *Natural Language Processing* (NLP) for entity extraction and this makes the bot intelligent enough to handle sentences that carry split entity synonyms.

		For instance, you have added the entity synonym “mobile cover” and trained your bot accordingly, but the user frames the query by splitting the words apart as follows:

			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/query-3.png   

		With Alter NLU, your bot will be able to extract the correct entity and accurately understand what information the user needs.

=======
Reports
=======

Chatbot training is an ongoing process that should get better at every successive stage. With each improvement, the trainer/developer should have a clearer understanding of the changes made. 

	*The section provides AI based real time ‘Reports’ where we list out the health of the training dataset created by the user, alert if there are issues and recommend how to make it better.*

The console gives you insight on the below with the help of tabular and statistical graphical display:

	-	**Intent Distribution:**
		It represents that number of intents created and the numerical proportions for the number of sentences present in each of the intents(count) and their respective percentages(count percent).

			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/intent-distribution.png   


	-	**Figuring out the intents that require more training sentences:**
		It reports the specific intents that have less number of training sentences than the threshold set i.e 3 per intent. Notifies the user with the name of the intents lacking enough training expressions as compared to the other intents in the bot.

	-	**Listing out the limitations in the entity section:**
		Reports about the name of the entities which have been defined, but the user might not have formed any training sentence with it in the intent section. The other reason could be that the user might have mistakenly deleted the entity from the intent section but forgot to delete the same from the entity section.

	-	**Examines the training dataset to extract the untagged entities:**
		Lists out keywords which have been tagged as an entity in intent but, the same keyword also occurs untagged in the training sentence of another intent.
		Notifies the user that they might have skipped tagging the keyword as an entity in the other intent mentioned.

	-	**Captures repetition of training sentence**
		Informs about the training sentence(s) which the user might have added in multiple intents by mistake. The console alerts this to the user with an error message at the top of the reports section.

			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/report-details.png   

