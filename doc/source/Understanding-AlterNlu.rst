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
									
	-	Second, which can have multiple or single keywords(entities) in the training phrase which we want to extract from the user query as explained in Fig. 1.1 below. 

========
Entities
========

Entities describe the piece of information you would want to extract from the expressions/messages of the user.
Like in  Fig. 1.1, the “brand_name“ and “processor_gen“ are the 2 entities in our console that will be mapped to their respective “Reference Value“ and “Synonyms“ values.


	**How Intents and Entities work to produce maximum output with relatively less training data?**

	-	*The intent | sentence ratio. Manage inventory of synonyms with entities*
		
		The major obstacle in building an intelligent Chatbot is, interpreting various patterns and styles user can opt for to ask a query, and train them for all the possible approaches.

		Unlike a few other NLP softwares for training bots, we try to provide optimum results when there are less training samples. Although, the more you train, the better is the outcome.

		For good results, the Alter NLU console requires a minimum of 3 training sample per intent. Also, Alter NLU needs only a single synonym training sample for each entity reference value.

		.. note::
		   Maximize output with relatively less training data

		To ensure that the training stats are appropriate, we show alerts and warnings in the report section of the console.

		For example, if a user wants to buy a laptop with different specifications, he/she can request a query like ::

										I want to buy a laptop with 7th Gen processor.

		But the same query can be asked in a different style like ::

										Get me a PC embedded with a Seven Generation Processor.

		In Alter NLU you can maintain an inventory of similar words like, laptop and PC, in the form of entities, and train it only for a single synonym. 

		
	-	*Using Natural Language Processing for entity extraction*

		Our engineers have incorporated Natural Language Processing (NLP) for entity extraction which makes the bot intelligent to handle sentences that carry split entity synonyms.

		For example : 
		If you have added an entity synonym “mobile cover” and trained it accordingly, but the user uses it in the query as 2 different words like ::

										need cover for my mobile

		The bot will be able to extract the correct entity and understand what the user wants to ask.

=======
Reports
=======

Chatbot training is an ongoing process that should get better at every successive stage. With each improvement, the trainer/developer should have a clearer understanding of the changes made. 

	*The section provides AI based real time ‘Reports’ where we list out the health of the training dataset created by the user, alert if there are issues and recommend how to make it better.*

The console gives you insight on the below with the help of tabular and statistical graphical display:

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


