# Hello Chef - Backend Assignment

## Brief

At Hello Chef, we spend all day figuring out how to get the freshest ingredients to our customers. As a software engineer, you have to build software to streamline our operation and fulfilment functions. Your task here is to decide how much of each ingredient we need to buy on a weekly basis.

## Requirements

1. We value a **clean**, **simple**, working solution.
2. The application must be run in Docker, candidate must provide `docker-composer.yml` and `start.sh` bash script at the root of the project, which should setup all relevant services/applications.
3. We prefer PHP (Laravel/Lumen), but the solution can also be written in Symfony.
4. The solution must be production ready.

## Instructions

1. Must be a RESTful HTTP API listening to port `8080` (or you can use another port instead and describe in the README).

2. The API must implement 6 endpoints as described below:
    1. Create an ingredient
        - To create an ingredient you must supply `name`, `measure`, `supplier`
        - The API responds with an object of the ingredient
        - The measure is a unit of measure such as `g`, `kg`, `pieces`. Depending on whether it is 200grams of sugar or perhaps 8 potatoes.

	2. List ingredients
		- This should list all ingredients and should be paginated.

	3. Create a recipe
		- To create a recipe you must supply `name`, `description` and an array of ingredients and the amount of the ingredient required
		- The description is a free text field to describe the recipe steps.
		- The ingredients array includes an amount of each ingredient required and maps back to the measure required for that ingredient from the ingredients endpoint.

	4. List recipes
		- This should list all recipes and should be paginated.

	5. Create a box for a user
		- A box is an order from a customer which includes up to 4 recipes
		- To create a box you must supply a `delivery_date` which is any date in the future along with an array of recipe IDs (up to 4) that the user would like to receive.
		- The endpoint should return failures for invalid recipe IDs or delivery_dates in the past or within the next 48 hours.
		- The API should respond with an object of the box.

	6. View the ingredients required to be ordered by the company
		-	Upon supplying an `order_date` the API must response with the ingredients and amount of each ingredient which should be ordered to fulfill all orders for the 7 days from the `order_date`.

3. The request input should be validated before processing. The server should return proper error responses in case validation fails.

4. A database must be used (at HelloChef we typically use MySQL). Database installation and initialization must be done in `start.sh`

5. All responses must be in JSON format for success and failure responses.

6. Relations between models can be made however they make sense. If extra tables are needed please make them.

7. Tables should have migrations.

## Bonus Tasks

1. Having unit/integration tests is a strong bonus.
2. Add seeders.
3. Add filters for ingredient supplier, box delivery_date.

## Submission & Presentation

1. Please create a public GitHub / BitBucket repository for your project.
2. Your repository must have a detailed README.md with instructions on how to set up & run your code locally.
3. It must not contain the words “hellochef” or “challenge”.
4. We would like you to present your work no later than 7 days from the day you receive your assignment.
5. Accordingly, please send us the link to your repository at least 1 day prior to the presentation meeting for a review.
6. The presentation would be done in these steps:
    - Run your code locally
    - Give us a UI and features walkthrough
    - Explain your code
    - Run tests, if any

---

> Have questions? We would love to answer. Mail us at techchallenge@hellochef.me
