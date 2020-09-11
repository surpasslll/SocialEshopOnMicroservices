﻿## Statement of goals
Nowadays, many social apps will match you with others based on some quiz. But we think these quizzes can hardly be used to predict one's appetite in making friends. So we are thinking about using the transaction history data to match people up. 

## Functional Description
1. E-commerce
   	- Backend logic: 
	1. Identification module
		- Database: 
            1. Normal user: ID|UserName|Password|Email|Address|Phone|Payment
            2. Bussiness user: ID|UserName|Password|Email|Address|Phone|Company
            3. Admin user: ID|UserName|Password
		- Security:
  		    - Using spring default security architecture
  		    - OATH 2(login with 3rd party service account)
        - Permission:
    		- Normal user's account permission
    			- Social permission: follow user, unfollow user, blacklist, chat
    			- Buyer’s permission: browse the catalog, make the payment, request item, buy item
    		- Bussiness user's account permission
        		- Seller's permission: add item information, delete item information, publish item information, edit item information
    		- Admin user's account permission
        		- Certification: certify bussiness account application
    			- Item Admin(could change items outside the business org): delete Item
     	- Function:
			1. Provide authentication and verification for users 
	- API design:
		- URL: http://localhost/profile
		- GET /profile -> Get all profile list
		- POST /profile ->  Create a new profile
		- GET /profile/001 -> Get the profile with user ID 001
		- PUT /profile/001 -> Admend the profile with user 001
		- DELETE /profile/001 -> Delete the profile with user ID 001
		- GET /profile/001/all -> Get all the information in the profile with user ID 001
  			 
    1. Basket module
        - Database:
			ID|Owner_ID|Item_ID|Count
		- Function:
			1. CRUD 
			2. empty all
			3. Buy item

	2. Ordering module
		- Database:
			ID|Owner_ID|Item_ID|Count|Order_time|Price
		- Function:
			1. CR 

    4. Catalog module
		- Database:
			ID|Bussiness_User_ID|Name|Type|Price|Count|Discount|Description
		- Function:
			1. CRUD
			2. add item to basket 
   
   - FrontEnd logic:
	1. Login\Signup page:
		call function in Identification service
	3. Profile page:
		call function in Baskets,Ordering services

2. Social
	4. Recommend possible followers to users based on their purchase, view history; focus on some specific item(like books, CD)

## Frameworks & Tools

## User Interface

## System diagram

## Milestones

