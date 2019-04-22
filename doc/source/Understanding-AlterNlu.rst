###############################
Understanding Alter NLU Console
###############################

=======
Intents
=======

Intents are what you expect users to say and what are their intentions. It depicts the gist of the expression that the user says or in simple terms what the user probably meant to say.

For Example :

		If the user types : 
		*I want to buy apple mobile worth 60k*
		
		Here the user intent to buy the specified product with the mentioned specifications. We can infer the intent of the user query as "search-product", which is a user-defined term.

There can be 2 varieties of intents:

	-	First, which do not contain any entities (explained below), but are simple and direct queries. For example “greet”, "exit" and other light conversational intents :: 
									
			“Hey there” or  “Hi”.
									
	-	Second, which can contain multiple or single entities in the training query which we want to extract from the user query as demonstrated in the image below.

		.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/intent-mapping.png   

========
Entities
========

Entities describe the piece of information you would want to extract from the expressions/messages of the user. 

Entities can consist of single or multiple words. For example "mobile" and "mobile cover" are 2 different entities.

Like in the image above, the "price", "product-type" and "brand" are the 3 entities in our Alter NLU console that will be tagged to their respective “Reference Value“ and “Synonyms“ values.

		.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/syn-1.png   

**Reference Value**

It is the convenient representation of the whole set of synonyms (explained below). It can be in the form of an ``unique_id``, ``abbreviations``, ``initials``, ``shortforms``, etc. according to the developers convinence.  

For example, in the last synonym set "Dolce & Gabbana" in the image above is conveniently refered as "D_G".

**Synonyms**

A set of words or phrases having similar meaning, mapped against each reference value

**Selected Value**

It is the part of the sentence we highlight to tag against a particular entity. Each Selected Value in the Alter NLU console has a different color code based on the entity tagged.

=======
Reports
=======

Chatbot training is an ongoing process that should get better at every successive stage. With each improvement, the trainer/developer should have a clearer understanding of the changes made. 

	*The section provides NLP based real time ‘Reports’ where we list out the health of the training dataset created by the user, alert if there are issues and recommend how to make it better.*

The console gives you insight on the below with the help of tabular and statistical graphical display:

	-	**Intent Distribution:**
		It represents that number of intents created and the numerical proportions for the number of relevant sentences present in each of the intents and their respective percentages.

		.. note::
		   The relevant sentences are the sentence which contributes towards building better NLU model.

		
		.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/intent-distribution-1.png   


	-	**Figuring out the intents that require more training sentences:**
		It reports the specific intents that have less number of training sentences than the threshold set i.e 3 relevant sentence per intent. Also, it notifies the user with the name of the intents lacking enough training queries in comparison to the other intents in the bot.
		
			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/report-1.png   

	-	**Examines the training dataset to extract the untagged entities:**
		Lists out keywords which have been tagged as an entity in intent but, the same keyword also occurs untagged in the training sentence of another intent.
		It also notifies the user that they might have skipped tagging the keyword as an entity in the other intent mentioned.

			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/untagged-entities.png   

	-	**Listing out the limitations in the entity section:**
		Reports about the name of the entities which have been defined, but the user might not have formed any training queries with it in the intent section. The other reason could be that the user might have mistakenly deleted the entity from the intent section but forgot to delete the same from the entity section.

	-	**Captures repetition of training sentence:**
		Informs about the training sentence(s) which the user might have added in multiple intents by mistake. The console alerts this to the user with an error message at the top of the reports section.

			.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/report-2.png   

		.. note::
		   For good results, the console requires a minimum of 3 relevant training queries per intent. Also, Alter NLU console needs only a single synonym tagged for each entity reference value in training queries of the intent section.
		   So, all you need to do is add 1 training query in the intent section containing any one of the synonyms per reference value and your bot is good to go.


For instance, I only need to train for 1 user query containing the sysnonym for "D_G" like :
*I want a Dolce & Gabbana bag*
and rest will be handled automatically.	