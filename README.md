# E-commerce_Back_End

  ![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)

  ## Description
  
  Contains back end code for an e-commerce website allowing the front end to retrieve, store, update and delete information about products through api calls to endpoints specified below. Information includes category names and tag names, as well as how much is in stock, pricing, and product names. All information is stored safely on multiple tables in a mysql database on the server. 

  [Click this link for walkthrough video displaying back end functionality](https://drive.google.com/file/d/13dGPVpxy5Pu6jpWC5XpS89ffemWgD9mY/view)
  
  ## Table of Contents
    
  * [Installation](#installation)

  * [Usage](#usage)

  * [License](#license)

  * [Credits](#credits)

  * [Questions](#questions)
  
  ## Installation

  ### Requirements:
  * Node  
  * MySQL

  Given that users have mysql it is necessary to create a database. To accomplish this utilize the cli and navigate the root directory of the repo and initiate the mysql shell. Once inside the mysql shell run the command:

  ```
  source db/schema.sql
  ```

  Next, it is necessary to create a .env file in order to connect to the proper database. Simply create the variables DB_NAME, DB_USER, and DB_PW and set them to the value of 'ecommerce_db' your mysql username, and your mysql password respectively. After the connection is prepareed run the command to seed the database with premade data (you can also seed it through api calls):

  ```
  npm run seed
  ```  

  Lastly, users must also run the following command from the root directory of the repo in the cli to install all dependencies:

  ```
  npm i
  ```
  
  ## Usage
  
  In order to initiate the server run the following command from the root directory of the repo:

  ```
  npm run start
  ```

  The repo just contains back end functionality. It allows calls to the following endpoints:

  ### Tags
  * /api/tags
    1. Supports GET call to recieve all tags.
    2. Supports POST call to create a new tag. Requires request body to contain json object with following format:
    ```
    {
	    "tag_name":"post example"
    }
    ```
  * /api/tags/:id
    1. Supports GET call to recieve a single tag (No request needed beyond the id number parameter).
    2. Supports PUT call to update a tag. Requires request body to contain json object with following format:
    ```
    {
	    "tag_name":"put example"
    }
    ```
    3. Supports DELETE call to permanently delete a tag (No request needed beyond the id number parameter).
  ### Categories
  * /api/categories
    1. Supports GET call to recieve all categories.
    2. Supports POST call to create a new category. Requires request body to contain json object with following format:
    ```
    {
	    "category_name":"post example"
    }
    ```
  * /api/categories/:id
    1. Supports GET call call to recieve a single category (No request needed beyond the id number parameter).
    2. Supports PUT call to update a category. Requires request body to contain json object with following format:
    ```
    {
	    "category_name":"put example"
    }
    ```
    3. Supports DELETE call to permanently delete a category (No request needed beyond the id number parameter). It is important to note that categories cannot be deleted while there are still products listed under that category. All subsequent products must first be deleted before the category can be deleted.
  ### Products
  * /api/products
    1. Supports GET call to recieve all products.
    2. Supports POST call to create a new product. Requires request body to contain json object with following format:
    ```
    {
      "product_name": "Keyboard",
      "price": 200.00,
      "stock": 3,
      "category_id": 6,
      "tagIds": [9]
    }
    ```
  * /api/products/:id
    1. Supports GET call to recieve a single product (No request needed beyond the id number parameter).
    2. Supports PUT call to update any information of a specific product. Requires request body to contain json object containing any information you want to update (Can be a single key value pair if that's all you wish to update):
    ```
     {
      "product_name": "Blue Keyboard",
      "price": 150,
      "stock": 15,
      "category_id": 7,
      "tagIds": [9, 3]
    }
    ```
    3. Supports DELETE call to permanently delete a product (No request needed beyond the id number parameter).

  ## License

  This project is licensed under the MIT license.

  ## Credits

  * [Node](https://nodejs.org/en/) The application utilizes Node for the ability to run javascript from the cli as well as the ability to utilize 3rd party packages credited below.

  * [MySQL](https://www.mysql.com/) The application utilizes MySQL in order to implement persistent data.

  * [mysql2 Node package](https://www.npmjs.com/package/mysql2) The application utilizes the mysql2 package in order for javascript to easily interact with MySQL databases stored on a users local device.
 
  * [sequelize Node package](https://www.npmjs.com/package/sequelize) The application utilizes sequelize to easily create and link tables in the database and easily alter the tables dynamically.

  ## Questions

  If you have any questions about the repo, open an issue or contact me directly at ddsmm.managlia@gmail.com. You can find more of my work at [dmanaglia](https://www.github.com/dmanaglia).
  
