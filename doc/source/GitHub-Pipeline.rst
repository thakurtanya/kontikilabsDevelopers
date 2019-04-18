
##############################
Alter NLU GitHub Repo Pipeline
##############################

========
Rest API 
========
Rest API supported for both the below training and parsing queries.

-	REST API training ::

		http://<ip_address>:5001/train
		Method : POST
		Accept / Content_type : application/json
		Data : training_data file from Kontiki Platform.

		curl -H "Content-Type: application/json" --data @<file path> http://localhost:5001/train

-	Rest API parse query ::
	
		http://<ip_address>:5001/parse
		Method : POST
		Accept / Content_type : application/json
		Data : {"text": "<your_query>"}

======================================
v1.0.0-beta : The Engineering Involved
======================================

**Intent Model**

We have used Convolutional Neural Networks (CNN) based model to capture the intent. Further, the use of custom validation algorithm and matthews correlation coefficient as accuracy metric makes the intent model robust.

.. note::
	The user has to train the sentence for one of the synonyms and the remaining are handled by our console code.

**Entity Model**

In this version we have replaced the previous Flashtext and FuzzyWuzzy based entity extraction method with a CRF based Entity Recognition model.

=========================================
Elaboration of the above chatbot response
=========================================

Below is an example along with a detailed explanation of the benefits of using this new pipeline.

	.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/example-2.png   

-	According to the context of the user query, the model successfully recognises the search product intent along with the confidence score.
-	This model handles out-of-vocabulary words to some extent. 
	The term ‘out-of-vocabulary words’ refers to those words which are not present in the training data of the chatbot.
	For example, If you take a look at the example above, the parsed_value “799k” is not present in the training data used to train the “ecomm-bot” whose entity has been recognised accurately as “price”.
-	The CRF model was able to recognise the entity accurately, because it considers the sentence structure of the user query.
-	If you’re familiar with other bot frameworks, then you might not have come across a key like “parsed_value”. The main goal	  to add this key in the response is to assist developers to directly use the “parsed_value” if needed. 
	In the example above, the developer might need the exact value of entities such as “price” that is in the user query for further usage. In this case it’s “799k”.
-	Also, if you’re an existing user of Alter NLU it needs to be pointed out that the “category” key in the response has been renamed to “name”.


