#####################################
KON-TIKI LABS PLatform : API Document 
#####################################

This document is intended to get you started with your bot content using the KTL platform APIs.
Check the document below to find out how your bot developers can retrieve the platform ‘flakes’, and perform all the necessary CRUD actions with our simple to use APIs.

===============================
**User : Get the User Details**
===============================

-	**User login**
	
	*Generate access token*

	Get your ‘Access Token’ by providing your platform credentials. Access tokens are required to access data or make changes to your platform data via the APIs.
	
	An example of the request and response:

	*Request* ::
			
			-------------------------------------------------------------
			| URL    : http://app.kontikilabs.com:3000/api/users/login  |
			-------------------------------------------------------------
			| HEADER : Content-Type:application/json                    |
			-------------------------------------------------------------
			| METHOD : ``POST``                                         |
			-------------------------------------------------------------

	*Data* ::
			
			
			{"email":"<your_email_id>", "password":"<your_password>", "source":"platform"}

	*Response* ::
			
			
			  STATUS CODE : 200 
				{
				  "id": "<ACCESS_TOKEN>",
				  "created": "2017-08-23T06:28:45.142Z",
				  "userId": "<USER_ID>",
				  "userDetail": {
				    "organisation_id": "<ORGANISATION_ID>",
				    "role": "<USER_ROLE_ID>",
				    "username": "<USER_NAME>",
				    "email": "<EMAIL_ID>",
				    "emailVerified": true,
				    "id": "<USER_ID>",
				    "created": "2017-08-21T06:31:57.547Z",
				    "modified": "2017-08-21T06:32:13.938Z"
				  }
				}

	If the data is invalid, you will get the following response ::


			 STATUS CODE : 401 
			 	{
			 	  "error": {
				    "statusCode": 401,
				    "name": "Error",
				    "message": "login failed",
				    "code": "LOGIN_FAILED"
				  }
			 	}

 The following user roles can be used to determine permissions assigned to the user

 +------------+-----------------------------------------+
 |            |                                         |
 | Role       | Description                             |
 |            |                                         |
 +============+=========================================+
 | customer   | The bot users                           |
 +------------+-----------------------------------------+
 | superadmin | User who owns the organisation account  |
 +------------+-----------------------------------------+

-	**Update user**

	The update API allows for updating user details by filling in the desired value in the input JSON. Below is an example of the request and response:

	*Request* ::
			
			-----------------------------------------------------------------------
			| URL          : http://app.kontikilabs.com:3000/api/users/{user_id}  |
			-----------------------------------------------------------------------
			| HEADER       : Content-Type     : application/json                  |
			|                                                                     | 
			|                KTL-Access-Token : {access_token}                    |
			-----------------------------------------------------------------------
			| METHOD       : ``PATCH``                                            |
			-----------------------------------------------------------------------
			| Request JSON :                                                      |                 
			|     {                                                               |
			|       "organisation_id": "string",                                  |
			|       "bot_id": "string",                                           |
			|       "bot_name": "string",                                         |
			|       "role": "owner",                                              |
			|       "platform": "string",                                         |
			|       "phone_no": "string",                                         |
			|       "username": "string",                                         |
			|       "email": "string",                                            |
			|       "id": "string",                                               |
			|     }                                                               |
			-----------------------------------------------------------------------


	*Data* ::
			
			
		{"phone_no":"<new_phone_number>"}

	.. note::

            *Rather than sending the entire JSON, you can just send the values you want to update*. 

	*Response* ::
			
			
			  STATUS CODE : 200 
				{
				  "organisation_id": "<ORGANISATION_ID>",
				  "role": "<USER_ROLE_ID>",
				  "phone_no": "<NEW_PHONE_NUMBER>",
				  "username": "<USER_NAME>",
				  "email": "<EMAIL_ID>",
				  "emailVerified": true,
				  "id": "<USER_ID>",
				  "created": "2017-08-21T06:31:57.547Z",
				  "modified": "2017-08-21T06:32:13.938Z"
				}

	If the *user_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong User ID 
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <user_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}


-	**Get user info**

	Get the details of the user, such as *role*, *username* etc., by passing the *user_Id*. An example of the request and response: 

	*Request* ::
			
			+---------------------------------------------------------------------+
			| URL          : http://app.kontikilabs.com:3000/api/users/{user_id}  |
			+---------------------------------------------------------------------+
			| HEADER       : Content-Type     : application/json                  |
			|                                                                     | 
			|                KTL-Access-Token : {access_token}                    |
			+---------------------------------------------------------------------+
			| METHOD       : ``GET``                                              |
			+---------------------------------------------------------------------+

	*Response* ::
			
			
			  STATUS CODE : 200 
				{
				  "organisation_id": "<ORGANISATION_ID>",
				  "role": "<USER_ROLE_ID>",
				  "phone_no": "<PHONE_NUMBER>",
				  "username": "<USER_NAME>",
				  "email": "<EMAIL_ID>",
				  "emailVerified": true,
				  "id": "<USER_ID>",
				  "created": "2017-08-21T06:31:57.547Z",
				  "modified": "2017-08-21T06:32:13.938Z"
				}

	If the *user_id* is invalid, you will receive the following response ::


			 STATUS CODE : 404 - Wrong User ID 
			 	{
			 	  "statusCode": 404,
				   "name": "Error",
				   "message": "Unknown \"user\" id \"<user_id>\".",
				   "code": "MODEL_NOT_FOUND"
				  }
			 	}


===================================================
**Organisation : Get what your organisation holds**
===================================================

-	**Organisation details**
	
	Get the details of your organisation with the following request:

	*Request* ::
			
			---------------------------------------------------------------------------------------
			| URL          : http://app.kontikilabs.com:3000/api/organisations/{organisation_id}  |
			---------------------------------------------------------------------------------------
			| HEADER       : Content-Type     : application/json                                  |
			|                                                                                     | 
			|                KTL-Access-Token : {access_token}                                    |
			---------------------------------------------------------------------------------------
			| METHOD       : ``GET``                                                              |
			---------------------------------------------------------------------------------------


	*Response* ::
			
			
			  STATUS CODE : 200 
				{
				  "company_name": "<COMPANY_NAME>",
				  "plan": "premium",
				  "email": "<EMAIL_ID>",
				  "id": "<ORGANISATION_ID>",
				  "created": "2017-08-21T06:31:57.394Z",
				  "modified": "2017-08-21T06:31:57.394Z",
				  "username": "<USER_NAME>"
				}

	If the *organisation_id* is invalid, you will receive the response as follows ::


			 STATUS CODE : 404 - Wrong Organisation ID
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "Unknown \"organisation\" id \"<organisation_id>\".",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}


-	**Organisation users**
	
	Get a list of users in your organisation. Below is an example of the request and response:

	*Request* ::
			
			----------------------------------------------------------------------------------------------
			| URL          : http://app.kontikilabs.com:3000/api/organisations/{organisation_id}/users   |
			----------------------------------------------------------------------------------------------
			| HEADER       : Content-Type     : application/json                                         |
			|                                                                                            | 
			|                KTL-Access-Token : {access_token}                                           |
			----------------------------------------------------------------------------------------------
			| FILTER       : {"limit":1, "skip":0}                                                       |
			|                                                                                            | 
			| limit        : Limits the number of records returned to the specified number(or less)      |
			| skip         : Omits specified number of returned records. Useful to paginate responses    |
			----------------------------------------------------------------------------------------------
			| METHOD       : ``GET``                                                                     |
			----------------------------------------------------------------------------------------------


	*Response* ::
			
			
			  STATUS CODE : 200 
				[
				  {
				    "organisation_id": "<ORGANISATION_ID>",
				    "role": "<USER_ROLE_ID>",
				    "phone_no": "<PHONE_NUMBER>",
				    "username": "<USER_NAME>",
				    "email": "<EMAIL_ID>",
				    "emailVerified": true,
				    "id": "<USER_ID>",
				    "created": "2017-08-21T06:31:57.547Z",
				    "modified": "2017-08-21T06:32:13.938Z"
				  }
				]

	If the *organisation_id* is invalid, you will receive the response as follows ::


			 STATUS CODE : 404 - Wrong Organisation ID
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <organisation_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}

-	**Bots in your organisation**
	
	Get a list of all the bots in your organisation with the following request:

	*Request* ::
			
			------------------------------------------------------------------------------------------
			| URL        : http://app.kontikilabs.com:3000/api/organisations/{organisation_id}/bots  |
			------------------------------------------------------------------------------------------
			| HEADER     : Content-Type     : application/json                                       |
			|                                                                                        | 
			|              KTL-Access-Token : {access_token}                                         |
			-------------------------------------------------------------------------------------------
			| FILTER     : {"limit":1, "skip":0}                                                     |
			|                                                                                        | 
			| limit      : Limits the number of records returned to the specified number(or less).   |
			| skip       : Omits specified number of returned records. Useful to paginate responses. | 
			------------------------------------------------------------------------------------------
			| METHOD     : ``GET``                                                                   |
			------------------------------------------------------------------------------------------


	*Response* ::
			
			
			  STATUS CODE : 200 
				[
				  {
				    "name": "<BOT_NAME_1>",
				    "platform": "<BOT_PLATFORM>",          #Slack or Facebook Messenger
				    "domain": "<BOT_DOMAIN>",
				    "organisation_id": "<ORGANISATION_ID>",
				    "id": "<BOT_ID_1>",
				    "created": "2017-08-21T06:47:01.949Z",
				    "modified": "2017-08-21T06:47:01.949Z"
				  },
				  {
				    "name": "<BOT_NAME_2>",
				    "platform": "<BOT_PLATFORM>",
				    "domain": "<BOT_DOMAIN>",
				    "organisation_id": "<ORGANISATION_ID>",
				    "id": "<BOT_ID_2>",
				    "created": "2017-08-21T07:42:35.399Z",
				    "modified": "2017-08-21T07:42:35.399Z"
				  }
				]

	If the *organisation_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong Organisation ID
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <organisation_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}


-	**Bot users in your organisation**
	
	Get a list of users using the bot by passing the ‘bot_id’ in the where clause:

	*Request* ::
			
			---------------------------------------------------------------------------------------------
			| URL          : http://app.kontikilabs.com:3000/api/organisations/{organisation_id}/users  |
			---------------------------------------------------------------------------------------------
			| HEADER       : Content-Type     : application/json                                        |
			|                                                                                           | 
			|                KTL-Access-Token : {access_token}                                          |
			---------------------------------------------------------------------------------------------
			| FILTER  : {"where": {"bot_id": "<bot_id>"}, "limit":1, "skip":0}                          |                                              
			|                                                                                           | 
			| limit   : Limits the number of records returned to the specified number(or less).         |
			| skip    : Omits specified number of returned records. Useful to paginate responses.       |
			---------------------------------------------------------------------------------------------
			| METHOD       : ``GET``                                                                    |
			---------------------------------------------------------------------------------------------


	*Response* ::
			
			
			  STATUS CODE : 200 
				[
				  {
				    "organisation_id": "<ORGANISATION_ID>",
				    "bot_id": "<BOT_ID>",
				    "role": "<USER_ROLE_ID>",
				    "platform": "<BOT_PLATFORM>",
				    "username": "<USER_NAME>",
				    "email": "<EMAIL_ID>",
				    "emailVerified": true,
				    "id": "<USER_ID>",
				    "created": "2017-07-03T09:00:28.968Z",
				    "modified": "2017-07-03T09:00:29.007Z",
				    "displayName": "<DISPLAY_NAME>",
				    "profilePic": "string",
				    "bot": "<BOT_NAME>",
				    "url": null,
				    "type": null,
				    "quiz_sets": [],
				    "read_stories": [],
				    "context_session": [],
				    "level": 0,
				    "user_id": "<USER_ID>”
				  }
				]

	If the *organisation_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong Organisation ID 
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <organisation_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}

===============================
**Bots : Handle your bot data**
===============================

-	**Get flakes**
	
	Get all the flakes present inside the bot. You can filter flakes according to flake status. Below is an example of the request and response:

	*Request* ::
			
			------------------------------------------------------------------------------------------
			| URL          : http://app.kontikilabs.com:3000/api/bots/{bot_id}/flakes                |
			------------------------------------------------------------------------------------------
			| HEADER       : Content-Type     : application/json                                     |
			|                                                                                        |   
			|                KTL-Access-Token : {access_token}                                       |
			------------------------------------------------------------------------------------------
			| FILTER      : {"where": {"status": "<flake_status>"}, "limit":10, "skip":0}            |
			|                                                                                        | 
			|               Available flake status :                                                 |
			|                                      -draft                                            |
			|                                      -publish                                          |
			|                                      -schedule                                         |
			|                                                                                        | 
			| limit       : Limits the number of records returned to the specified number(or less).  |
			| skip        : Omits specified number of returned records. Useful to paginate responses.|
			------------------------------------------------------------------------------------------
			| METHOD      : ``GET``                                                                  |
			------------------------------------------------------------------------------------------


	*Response* ::
			
			
			  STATUS CODE : 200 
				{
				  "title": "<FLAKE_TITLE>",
				  "description": "<FLAKE_DESCRIPTION>",
				  "image_url": "<FLAKE_IMAGE_URL>",
				  "bullet_points": [
				    {
				      "type": "image",
				      "text": "<BULLET_TEXT>",
				      "button": [{
				        "name":"<QR_BUTTON_NAME>",
				        "action":"<QR_BUTTON_ACTION>"
				      }]
				      "file_url": "<IMAGE_URL>"
				    },
				    {
				      "type": "text",
				      "text": "<BULLET_TEXT>",
				      "button": []
				    },    
				    {
				      "type": "video",
				      "text": "<BULLET_TEXT>",
				      "button": []
				      "file_url": "<VIDEO_URL>"
				    },
				  ],
				  "status": "FLAKE_STATUS",
				  "category": [
				    "<FLAKE_CATEGORY_ID>"
				  ],
				  "bot_id": "<BOT_ID>",
				  "id": "<FLAKE_ID>",
				  "created": "2017-08-27T09:26:08.344Z",
				  "modified": "2017-08-30T19:42:25.117Z",
				  "author_name": "<FLAKE_AUTHOR>",
				  "organisation_id": "<ORGANISATION_ID>",
				  "tags": [
				    "<FLAKE_TAG_ID>"
				  ]
				}

	If the *bot_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong Bot ID 
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <bot_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}


-	**Get flake details**
	
	Get any flake information by passing the *bot_id* and *flake_id*, as in the request below:

	*Request* ::
			
			--------------------------------------------------------------------------------------
			| URL          : http://app.kontikilabs.com:3000/api/bots/{bot_id}/flakes/{flake_id} |
			--------------------------------------------------------------------------------------
			| HEADER       : Content-Type     : application/json                                 |
			|                                                                                    | 
			|                KTL-Access-Token : {access_token}                                   |
			--------------------------------------------------------------------------------------
			| METHOD       : ``GET``                                                             |
			--------------------------------------------------------------------------------------


	*Response* ::
			
			
			  STATUS CODE : 200 
				{
				  "title": "<FLAKE_TITLE>",
				  "description": "<FLAKE_DESC>",
				  "image_url": "<FLAKE_TITLE>",
				  "bullet_points": [
				    {
				      "type": "text",
				      "text": "<BULLET_TEXT>",
				      "button": [
				        {
				          "name": "<QR_BUTTON_NAME>",
				          "action": "<QR_BUTTON_ACTION>"
				        }
				      ]
				    },
				    {
				      "type": "image",
				      "text": "<BULLET_TEXT>",
				      "file_url": "<IMAGE_URL>",
				      "button": []
				    }
				  ],
				  "status": "<FLAKE_STATUS>",
				  "category": [
				     "<CATEGORY_ID>"
				  ],
				  "bot_id": "<BOT_ID>",
				  "id": "<FLAKE_ID>",
				  "created": "2017-09-15T11:56:45.982Z",
				  "modified": "2017-09-15T11:59:03.174Z",
				  "organisation_id": "<ORGANISATION_ID>",
				  "author_name": "<AUTHOR_NAME>",
				  "tags": [
				     "<TAG_ID>"
				   ]
				}

	If the *bot_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong Bot ID 
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <bot_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}

	If the *flake_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong Flake ID 
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "No instance with id <flake_id> found for flakes"
				  }
			 	}


-	**Get tags**
	
	Get the tags associated with your bot using the following request:

	*Request* ::
			
			---------------------------------------------------------------------------------------------
			| URL          : http://app.kontikilabs.com:3000/api/bots/{bot_id}/tags                     |
			---------------------------------------------------------------------------------------------
			| HEADER       : Content-Type     : application/json                                        |
			|                                                                                           | 
			|                KTL-Access-Token : {access_token}                                          |
			---------------------------------------------------------------------------------------------
			| FILTER       : {"limit":1, "skip":0}                                                      |
			|                                                                                           | 
			| limit        : Limits the number of records returned to the specified number(or less).    |
			| skip         : Omits specified number of returned records. Useful to paginate responses.  | 
			---------------------------------------------------------------------------------------------
			| METHOD       : ``GET``                                                                    |
			---------------------------------------------------------------------------------------------


	*Response* ::
			
			
			  STATUS CODE : 200 
				[
				  {
				    "name": "<TAG_NAME>",
				    "slug": "<SLUG>",
				    "type": "<TAG_TYPE>",
				    "bot_id": "<BOT_ID>",
				    "id": "<TAG_ID>",
				    "created": "2017-08-21T06:49:19.105Z",
				    "modified": "2017-08-21T06:49:19.104Z"
				  }
				]

	If the *bot_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong Bot ID 
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <bot_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}


-	**Get categories**
	
	Get all the created bot categories with the following request:

	*Request* ::
			
			------------------------------------------------------------------------------------------
			| URL        : http://app.kontikilabs.com:3000/api/bots/{bot_id}/categories              |
			------------------------------------------------------------------------------------------
			| HEADER     : Content-Type     : application/json                                       |
			|                                                                                        | 
			|              KTL-Access-Token : {access_token}                                         |
			------------------------------------------------------------------------------------------
			| FILTER     : {"limit":1, "skip":0}                                                     |
			|                                                                                        | 
			| limit      : Limits the number of records returned to the specified number(or less).   |
			| skip       : Omits specified number of returned records. Useful to paginate responses. |
			------------------------------------------------------------------------------------------
			| METHOD     : ``GET``                                                                   |
			------------------------------------------------------------------------------------------


	*Response* ::
			
			
			  STATUS CODE : 200 
				[
				  {
				    "name": "<CATEGORY_NAME>",
				    "slug": "<SLUG>",
				    "type": "<CATEGORY_TYPE>",
				    "bot_id": "<BOT_ID>",
				    "id": "<CATEGORY_ID>",
				    "created": "2017-08-21T06:47:21.649Z",
				    "modified": "2017-08-21T06:47:21.649Z"
				  }
				]

	If the *bot_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong Bot ID 
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <bot_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}


-	**Get channels**
	
	Get your bot’s entire channel details by making use of the following GET request:

	*Request* ::
			
			------------------------------------------------------------------------------------------
			| URL        : http://app.kontikilabs.com:3000/api/bots/{bot_id}/channels                |
			------------------------------------------------------------------------------------------
			| HEADER     : Content-Type     : application/json                                       |
			|                                                                                        | 
			|              KTL-Access-Token : {access_token}                                         |
			------------------------------------------------------------------------------------------
			| FILTER     : {"limit":1, "skip":0}                                                     |
			|                                                                                        | 
			| limit      : Limits the number of records returned to the specified number(or less).   |
			| skip       : Omits specified number of returned records. Useful to paginate responses. |
			------------------------------------------------------------------------------------------
			| METHOD     : ``GET``                                                                   |
			------------------------------------------------------------------------------------------

	*Response* ::
			
			
			  STATUS CODE : 200 
				[
				  {
				    "name": "<CHANNEL_NAME>",
				    "keywordSource": [
				      {
				        "keyword": "<KEYWORD_1>",
				        "source": [
				          {
				            "name": "<WEB_SOURCE_NAME_1>",
				            "value": "<WEB_SOURCE_VALUE_1>",
				            "id": "<WEB_SOURCE_ID>",
				            "created": "2017-06-22T12:01:44.099Z",
				            "modified": "2017-06-22T12:01:44.099Z"
				          }
				        ]
				      },
				      {
				        "keyword": "<WEB_SOURCE_NAME_2>",
				        "source": [
				          {
				            "name": "<WEB_SOURCE_NAME_2>",
				            "value": "<WEB_SOURCE_VALUE_2>",
				            "id": "<WEB_SOURCE_ID>",
				            "created": "2017-06-28T16:46:34.542Z",
				            "modified": "2017-06-28T16:46:34.542Z"
				          }
				        ]
				      }
				    ],
				    "category": [
				      "<CHANNEL_NAME>"
				    ],
				    "cron_time": {
				      "hour": <CHANNEL_INTERVAL_TIME>,
				      "minute": 0
				    },
				    "status": "<CHANNEL_STATUS>",
				    "bot_id": "<BOT_ID>",
				    "id": "<CHANNEL_ID>",
				    "created": "2017-08-21T06:47:56.873Z",
				    "modified": "2017-08-21T06:47:56.873Z"
				  }
				]

	If the *bot_id* is invalid, you will get the following response ::


			 STATUS CODE : 404 - Wrong Bot ID 
			 	{
			 	  "error": {
				    "statusCode": 404,
				    "name": "Error",
				    "message": "could not find a model with id <bot_id>",
				    "code": "MODEL_NOT_FOUND"
				  }
			 	}


	
