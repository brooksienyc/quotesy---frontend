# Project Proposal
A fun app that will serve quote data. Users can find and save quotes for blogs, books, cards, or any time words of wisdom are required by searching through the catgories or selecting to get a random quote. The main data the user will receive is: author, id, text and category. Bonus: They will be able to save their own as well for fun.

I will be using the Famous Quotes API which provides over 100,000 famous quotes, 100 categories to choose from and 10,000 authors.

With the free API subscription and the random quote option, the user can select <= 1000 quotes. 



## Project name and description
quotesy

## Routes and models
Routes for CRUD operations:
## Read
GET/quotes/random - Retrieves any number of random quotes (up to 1000) that the user requests.

GET/quotes - Retrieves all of the categories of quotes available.

GET/quotes/:category - Retrieves the quotes based on the category the user chooses.

## Create
POST/quotes - Saves an existing quote to the user's list. Bonus: creates a unique new quote made by the user.

## Update
PUT/quotes/:id - Updates a quote saved by the user as a favorite. Bonus: Updates a unique quote created by the user.

## Delete
DELETE/quotes/:id - Deletes a quote saved by the user. Bonus: deletes a unique quote created by the user.


## User Stories
1. As a user, I should be able to query /quotes/:category route to GET all the quotes in that category (the categories will populate the designated area once I click the button to show them).
2. Once the quotes within that category are displaying, I should be able to select whichever quotes I want to add to my 'favorites' by posting to the /quotes route. 
3. As a user, I should be able to delete quotes I created myself or quotes I added to my favorites by deleting with the quotes/:id route which will find the id of that specific quote and delete it.

#### MVP Goals
1. (READ) This app should enable the user to retrieve author, id, text and category data once the user chooses the category of quote they wish to see. Or if they choose the 'random' option of how many random quotes they would like to see.

2. (CREATE) Next, the user shoud have the ability to save their favorite quotes to a data model with a single entity: "favorites" with the following fields:
author,
id, 
text
category.

3. (UPDATE) Now, the user should be able to edit the saved quote, for example, they may want to truncate the text if it is too long and create an excerpt from it and re-save it.

4. (DELETE) Finally, the user should be able to delete the saved quote if they no longer want it in their favorites.

5. To seed the database, I'll use the Famous Quotes API '/quotes/random' endpoint to retrieve a list of quotes and then save these quotes with their data in the database with their fields: author, text, category. For example the model would be as follows:

const favoriteSchema = mongoose.Schema({ 
 quote_id: { type: Schema.Types.ObjectId, ref: "Quote" },
 user_id: { type: Schema.Types.ObjectId, ref: "User" }, // bonus
})


#### Stretch Goals
1. As a user, I would like to create my own account log in for ease of use in the future.
2. As a user, I would like to create my own quotes and/or new categories.
3. As a user, I would like to share my quotes (either created myself or found in the categories with friends via social media, text, etc with a cute interface).
4. As a user, I would like to have a brief summary of each author or a picture to bring life to their words.