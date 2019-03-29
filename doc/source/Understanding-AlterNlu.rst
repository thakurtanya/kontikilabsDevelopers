#######################
Understanding Alter NLU
#######################

=======
Intents
=======

Intents are what you expect users to say. It describes the context of the expression that the user says or in simple terms what the user probably meant to say.

There are 2 type of intents:

	-	First, which do not map to any keyword, but are simple and direct phrases like an intent named “greet” which will hold training phrases as 
									
									“Hey there” or  “Hi”.
									
	-	Second, which can have multiple or single keywords(entities) in the training phrase which we want to extract from the user query as explained in Fig. 1.1 below. 

========
Entities
========

Entities describe the piece of information you would want to extract from the expressions/messages of the user.
Like in  Fig. 1.1, the brand_name and processor_gen are the 2 entities in our console that will be mapped to their respective "Reference Value" and "Synonym" values.

=======
Reports
=======

The USP of the Alter NLU console is the inbuilt report section that highlights the improvement and enhancements that should be done in the training dataset to develop an efficient bot. Chatbot training is an ongoing process that should get better at every successive stage. With each improvement, the trainer/developer should have a clearer understanding of the changes made. 

The report section provides an in-depth analysis and alerts for the intents and entities that need more training to enhance the accuracy for an optimal output. 
The console gives you insight on the below with the help of tabular and statistical graphical display:

	-	Intent Distribution
	-	Figuring out the intents that require more training sentences
	-	Listing out the limitations in the entity section
	-	Examines the training dataset to extract the untagged entities
	-	Captures repetition of training sentence
	-	Figuring the training bias by indicating intent name