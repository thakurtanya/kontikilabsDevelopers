
################
Alter NLU Engine
################

============
Installation
============
Go to this `GitHub <https://github.com/Kontikilabs/alter-nlu/tree/v1.0.0-beta>`_ Repo and follow the steps in the "Setting Up" section of the README.MD file.

========
Rest API 
========
Rest API supported for both the below training and parsing queries.

-	REST API training ::

		http://<ip_address>:5001/train
		Method : POST
		Accept : application/json
		Content_type : application/json
		Data : Content of Training Data JSON file downloaded from Alter NLU Console

or ::

		curl -H "Content-Type: application/json" --data @<training_data_json_file_path> http://localhost:5001/train

-	Rest API parse query ::
	
		http://<ip_address>:5001/parse
		Method : POST
		Accept : application/json
		Content_type : application/json
		Data : {"text": "<user_query>"}

======================================
v1.0.0-beta : The Engineering Involved
======================================

**Intent Model**

We have used **Convolutional Neural Networks (CNN)** based model to capture the intent. Further, the use of **custom validation algorithm** and **matthews correlation coefficient** as accuracy metric makes the intent model robust.

**Entity Model**

In this version we have replaced the previous Flashtext and FuzzyWuzzy based entity extraction method with a **CRF based Entity Recognition model**.

================================
Alter NLU Engine Response Format
================================

Below is an example along with a detailed explanation of the response.

	.. image:: https://raw.githubusercontent.com/thakurtanya/kontikilabsDevelopers/master/images/example-two.png   

-	According to the context of the user query, the model successfully recognises the search product intent along with the confidence score.

-	This model handles *out-of-vocabulary* words to some extent. 
	The term *‘out-of-vocabulary words’* refers to those words which are not present in the training data of the chatbot.
	For instance, 
	You trained in ALter NLU for the sentence - 
	
	*I want to purchase apple mobile worth 60k*
	
	Now, take a look at the input JSON, formed based on the user query in the imange above. 
	Even though the **parsed_value**, “1049k” may not be present in your training dataset, the output recognises the entity accurately as “price”.

-	The **CRF model** helps is recognising the entity accurately, because it considers the sentence structure of the user query.

-	The main goal of the **“parsed_value”** key in the response is to assist developers to directly use the key where needed. 
	In the example above, the developer might need the exact value of entities such as “price” that is in the user query for further usage. In this case it’s “1049k”.

-	Also, if you’re an existing user of Alter NLU it needs to be pointed out that the “category” key in the response has been renamed to “name”.


