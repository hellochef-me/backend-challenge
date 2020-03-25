# Software Engineering Challenge (Backend)

## Introduction

At HelloChef we spend all day figuring out how to get the freshest ingredients to our customers. As a software engineer, you have to build software to streamline our operation and fulfilment functions. Your task here is to decide how much of each ingredient we need to buy on a weekly basis. 

## Requirements

1. We value a **clean**, **simple**, working solution.
2. The application must be run in Docker, candidate must provide `docker-composer.yml` and `start.sh` bash script at the root of the project, which should setup all relevant services/applications.
3. We prefer PHP (Laravel/Lumen), but the solution can also be written in Symfony.
4. Candidates must submit the project as a git repository (github.com, bitbucket.com, gitlab.com). The repository must avoid containing the words `hellochef` and `challenge`.
6. The solution must be production ready.

## Problem Statement

1. Must be a RESTful HTTP API listening to port `8080` (or you can use another port instead and describe in the README)
2. The API must implement 6 endpoints as described below
    - One endpoint to create an ingredient
        - To create an ingredient you must supply `name`, `measure`, `supplier`
        - The API responds with an object of the ingredient
        - The measure is a unit of measure such as `g`, `kg`, `pieces`. Depending on whether it is 200grams of sugar or perhaps 8 potatoes. 

		-	One endpoint to list ingredients
			-	This should list all ingredients and should be paginated. 

		- One endpoint to create a recipe
			- To create a recipe you must supply `name`, `description` and an array of ingredients and the amount of the ingredient required 
			- The description is a free text field to describe the recipe steps. 
			- The ingredients array includes an amount of each ingredient required and maps back to the measure required for that ingredient from the ingredients endpoint. 
	
		- One endpoint to list recipes
			- This should list all recipes and should be paginated. 

		- One endpoint to create a box for a user
			- A box is an order from a customer which includes up to 4 recipes
			- To create a box you must supply a `delivery_date` which is any date in the future along with an array of recipe IDs (up to 4) that the user would like to receive. 
			- The endpoint should return failures for invalid recipe IDs or delivery_dates in the past or within the next 48 hours. 
			- The API should respond with an object of the box. 

		- One endpoint to view the ingredients required to be ordered by the company
			-	Upon supplying an `order_date` the API must response with the ingredients and amount of each ingredient which should be ordered to fulfill all orders for the 7 days from the `order_date`.   

3. The request input should be validated before processing. The server should return proper error responses in case validation fails.
4. A database must be used (at HelloChef we typically use MySQL). Database installation and initialization must be done in `start.sh`
5. All responses must be in json format for success and failure responses.
6. Relations between models can be made however they make sense. If extra tables are needed please make them. 
7. Tables should have migrations

## Bonus Tasks
1. Having unit/integration tests is a strong bonus.
2. Add seeders
3. Add filters for ingredient supplier, box delivery_date


Questions? We love to answer: techchallenge@hellochef.me
