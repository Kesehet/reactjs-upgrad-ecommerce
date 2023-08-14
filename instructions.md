# Starter Code and Configuration Guidelines

The starter code is the code snippet on which you must create the frontend using React of the **upGrad Eshop** application. This will help you follow the proper configuration guidelines that are required for developing this application.

- Use **create-react-app** to bootstrap a react project which will act as the starter code for your application.

At all points in time, you need to make sure that your web app is configured properly. Keeping the configuration guidelines in mind, you need to ensure that whenever you make any changes, you adhere to the guidelines mentioned below.

1. Always keep the following folders and the corresponding files inside them in the root directory of your application.
   - ‘node_modules’ folder (containing the list of all the packages)
   - ‘public’ folder
     - ‘index.html’ file
     - ‘manifest.json’ file
   - ‘src’ folder
     - ‘assets’ folder
     - ‘common’ folder
     - ‘components’ folder
     - ‘index.css’ file
     - ‘index.js’ file
   - ‘.gitignore’ file
   - ‘package-lock.json’ file
   - ‘package.json’ file
   - ‘README.md’ file

Remember to not disturb the names of these folders and files, and their locations inside the application. If you do, then it would be cumbersome for the graders to evaluate your code based on the given rubrics. Also, take special care to change only the required content of these folders and files. If you fail to do so, then your application may fail to run successfully, and this would also lead to your application being evaluated incorrectly.

2. Place all the common elements, components, stylesheets, scripts, etc., inside the ‘common’ folder.

3. Place all the resource files that you need to use in the application inside the ‘assets’ folder.

4. Create all your React components inside the ‘components’  folder. For each component, you need to first create a folder by the name of that component. Inside this folder, you need to create one JSX file and one stylesheet corresponding to that component.

For example, if you are creating the home component, then you can create a folder named ‘home’ inside the ‘components’ folder. Inside this folder, you can create two files, ‘Home.js’ and ‘Home.css’, which are, respectively, the JSX and stylesheet files corresponding to the home component of the application. It should look like this.
- ‘components’ folder
  - ‘home’ folder
    - ‘Home.js’ file
    - ‘Home.css’ file
	



### **Project Statement for the Navigation Bar**

1. **Introduction**:
   - The navigation bar is the first step in building the application.
   - It appears on the top of every page of the application.

2. **Features of the Navigation Bar**:
   - Contains the upGrad Eshop logo.
   - For users not logged in:
     - Links to log in and signup pages.
   - For logged-in users:
     - Search bar.
     - Link to the home page.
     - Button to log out.
     - If logged in as an admin, a link to the ‘Add Products’ page is included.

3. **Guidelines for the Navigation Bar**:
   - Use `@material-ui/icons/ShoppingCart` for the logo.
   - Use `react-router` Route for routing to login and signup pages.
   - Use `@material-ui/core/AppBar` for the AppBar.
   - API endpoints for signing in and signing up are `/auth` and `/users` respectively.
   - On successful sign-in, redirect the user to the `products` page.
   - Use the `/products` API endpoint for product search.

4. **Visual Representations**:
   - Navigation bar without login: ![image3](https://images.upgrad.com/637c43ac-bcfb-401f-88e8-66b180d37d94-image3.png)
   - Navigation bar after logging in as a normal user: ![image13](https://images.upgrad.com/d4388adb-e2eb-48ff-a60f-8786df986dff-image13.png)
   - Navigation Bar after logging in as an admin: ![image 3](https://images.upgrad.com/3ab38ff8-67bc-426d-8cc8-1976f2dcbb90-image3.png)
   - Search bar: ![image 20](https://images.upgrad.com/5a775f1d-9760-480b-aebc-525e5d9de9d4-image20.png)
   - Sign-in page: ![image16](https://images.upgrad.com/1d2788f1-435c-4b9f-8704-3bbbef14dcf1-image16.png)
   - Sign-up page: ![image 21](https://images.upgrad.com/e2c07dba-98b7-4864-af11-2c75f28aa312-image21.png)
   - Sign-up form: ![image 11](https://images.upgrad.com/7279a935-1132-48b4-b040-49232af87b37-image11.png)


# Project Statement for Contents of Products Page

The second step is to create the main contents of the products page.

**Guidelines for the Products Page:**
- In case a user is not logged in, they should not be able to proceed to the products page. The user should be redirected to the login page.
- Use `@material-ui/core/Card` to display the products.

**Card display for a non-admin user**

![Fig 1](https://images.upgrad.com/8bf75c19-e51f-4597-b258-0a3548eabf99-Screenshot 2023-08-01 at 11.22.45 AM.png)

**Card display for an admin user**

![Fig 2](https://images.upgrad.com/0e63ae82-1c64-4837-a584-4640dc33312f-Screenshot 2023-08-01 at 11.24.06 AM.png)

- Use `@material-ui/lab/ToggleButton` to create the product category tabs.
- These categories should be fetched using the endpoint: `/products/categories`.

![Fig 3](https://images.upgrad.com/7ff479c9-8ed5-4c47-adcd-b5eb5c81581a-Screenshot 2023-08-01 at 11.24.35 AM.png)

- The category tabs should be present on all the pages of the application.
- The items should be sorted according to the following options:
  - **Default:** The products should be displayed in the same order as received from the backend.
  - **Price high to low:** The products should be displayed in the decreasing order of price. This means that the product with the highest price should be displayed first.
  - **Price low to high:** The products should be displayed in the increasing order of price. This means that the product with the lowest price should be displayed first.
  - **Newest:** The products should be displayed in the order of addition or modification, with the latest added or modified product displayed first.

![Fig 4](https://images.upgrad.com/c1eebd40-9d41-4807-add5-bf6c395064cc-Screenshot 2023-08-01 at 11.24.42 AM.png)

- To display all the products, the API endpoint: `/products`, which you created inside `ProductController` in your backend project, must be used to display all the products.
- To display all the categories, the API endpoint: `/products/categories`, which you created inside `ProductController` in your backend project, must be used to log the user into the application.

**Note: You can also compare each of your web pages with the screenshots given below.**

**Default view of the products page for a non-admin user**

![Fig 5](https://images.upgrad.com/db68816d-f2f2-4dfc-9ec7-e12f9d2f7e3d-Screenshot 2023-08-01 at 11.24.49 AM.png)

**Default view of the products page for an admin.**

![Fig 6](https://images.upgrad.com/281aa70b-538a-4904-b9ed-60b7dd25a3ae-Screenshot 2023-08-01 at 11.24.56 AM.png)

**Products page with a category filter, apparel**

![Fig 7](https://images.upgrad.com/588a7378-54d5-4ded-982b-ca1d2636d818-Screenshot 2023-08-01 at 11.25.01 AM.png)



# Project Statement for the Product Details Page

Once the user clicks the **Buy** button on any product on the Products page, they should be redirected to the product details page of that product.

**Guidelines for Product Details page**:

- To display the details of a product, the following API endpoint: `/products/{id}`, which you created inside *ProductController* in your backend project, must be used to get the product details.
- The user should be able to input the quantity for a product on the details page.
- Ensure the product image is properly bounded. In case the image is not available, alternate text should be displayed for accessibility purposes.

*Note: You can also compare each of your web pages with the screenshots given below.*

Product Details Page:

![Fig 1](https://images.upgrad.com/959ccbaf-d4dd-4802-b413-39de2494eb01-Screenshot%202023-08-01%20at%2011.32.52%20AM.png)

**Report an error**



# Project Statement for Placing the Order

Once the user clicks on the **Place Order** button on the product details page, the user should be redirected to the orders page. The Create Order page should have a stepper menu.

**Guidelines for the Create Order page**:

- Use `@material-ui/core/Stepper` to create the stepper menu.
- On confirming the order, the following message should be displayed:
  
  'Your order is confirmed.'
  
- To create an order, the API endpoint: `/orders`, which you created inside *OrderController* in your backend project, must create an order.
- To add the address, the API endpoint: `/addresses`, which you created inside *ShippingAddressController* in your backend project, should add the address.

*Note: You can also compare each of your web pages with the screenshots given below.*

Step 1: Product Details

![Fig 1](https://images.upgrad.com/56b10a8f-c0c1-449a-931a-ca1769020f0c-Screenshot%202023-08-01%20at%2011.32.52%20AM.png)

Step 2: Address Details

- In case an address does not exist, the address form can be filled in to save a new address. Then the saved address can be selected in the dropdown.
- If a user tries to go to the confirm order page without selecting the address, an error message should be displayed on the screen - *Please select address!*

![Fig 2](https://images.upgrad.com/ee87cac1-ef76-418f-b5d5-a8b646c41398-Screenshot%202023-08-01%20at%2011.34.19%20AM.png)
![Fig 3](https://images.upgrad.com/7e933d50-9214-4b77-9c52-e2c911440fff-Screenshot%202023-08-01%20at%2011.34.26%20AM.png)
![Fig 4](https://images.upgrad.com/fca0d3fa-d154-4c31-a076-b53dc7e8bba5-Screenshot%202023-08-01%20at%2011.34.32%20AM.png)

Step 3: Order Details

- In the confirm order screen, if the user clicks on **Confirm Order**, the order should be placed using the `" /orders"` endpoint created in the *OrderController* in the backend.
- After the order is placed, users should be redirected to the Products page, with a message - *Order placed successfully!*

![Fig 5](https://images.upgrad.com/31d54b4e-b9e0-4baf-86ca-4c7ef51862f9-Screenshot%202023-08-01%20at%2011.34.39%20AM.png)
![Fig 6](https://images.upgrad.com/1677843e-a3eb-4c06-9936-8788c47e9ba2-Screenshot%202023-08-01%20at%2011.34.44%20AM.png)

**Report an error**




# Project Statement for the Admin User

An admin can manage the products in an application.

### Changes in the user interface for an Admin:

1. Add Product link in AppBar
   ![Fig 1](https://images.upgrad.com/be5ede4c-7458-45fb-a105-46efa22e8863-Screenshot%202023-08-01%20at%2011.41.43%20AM.png)
   
2. Modify/Delete icons in the product card
   ![Fig 2](https://images.upgrad.com/633e2bf7-965b-48ca-8d87-e9fb964f9f8b-Screenshot%202023-08-01%20at%2011.41.53%20AM.png)

### Guidelines for the Admin User functionalities:

- On clicking the delete icon in the product card, a dialog to confirm deletion should appear.
- On confirming deletion, display a message **‘Product <name> deleted successfully’**.
- On successful modification, display a message **‘Product <name> modified successfully’**.
- On successful addition of a product using the **Add Product** form, display a message **‘Product <name> added successfully’**.
- To display all the products in the **Manage Products** page, the API endpoint: `/products`, which you created inside *ProductController* in your backend project, must be used to display all the products.
- To add a product, the API endpoint: `/products`, which you created inside *ProductController* in your backend project, should add the product.
- To edit a product, the API endpoint: `/products/{id}`, which you created inside *ProductController* in your backend project, should edit the product.
- To delete a product, the API endpoint: `/products/{id}`, which you created inside *ProductController* in your backend project, should delete the product.

*Note: You can also compare each of your web pages with the screenshots given below.*

### Deleting a product:
![Fig 3](https://images.upgrad.com/e5245136-8b01-4cdb-98f9-a9f78d44f00d-Screenshot%202023-08-01%20at%2011.42.01%20AM.png)
![Fig 4](https://images.upgrad.com/dd0b1803-00ff-4d8a-bde2-17f72c961965-Screenshot%202023-08-01%20at%2011.42.08%20AM.png)

### Modifying a product:
![Fig 5](https://images.upgrad.com/4f6706f5-6b6d-4e17-82f1-16e21eba3eb1-Screenshot%202023-08-01%20at%2011.42.14%20AM.png)
![Fig 6](https://images.upgrad.com/4afb8523-d784-4b2d-8918-e8be538b538c-Screenshot%202023-08-01%20at%2011.42.22%20AM.png)

### Adding a product:

- The category is [Creatable Select](https://react-select.com/creatable). A user can choose pre-existing categories or add a new category.
![Fig 7](https://images.upgrad.com/c40a6997-c272-4889-8488-41d6eb8877ce-Screenshot%202023-08-01%20at%2011.42.30%20AM.png)
![Fig 8](https://images.upgrad.com/44854529-01c8-44e3-9657-86af201f2c79-Screenshot%202023-08-01%20at%2011.42.37%20AM.png)
![Fig 9](https://images.upgrad.com/9ba8141a-bae7-4ad4-948a-31e9bc2dc688-Screenshot%202023-08-01%20at%2011.42.45%20AM.png)

**Report an error**






| Criteria                                 | Meets Specifications                                                                                       | Does Not Meet Specifications                                                                                      |
|------------------------------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| Code Functionality                       |                                                                                                            |                                                                                                                    |
| Appearance of Header                     |                                                                                                            |                                                                                                                    |
| 1. The background of the header has...    | 1. The background of the header is not of the colour #3f51b5.                                           |                                                                                                                    |
| 2. The logo is positioned properly...    | 2. The logo is not present and/or...                                                                       | 2. The logo is not positioned properly and/or...                                                                  |
| 3. The search box is positioned properly... | 3. The search box is not present and/or...                                                                 | 3. It does not look like the one as shown...                                                                    |
| 4. The Login and Sign up links are...      | 4. The Login and Sign up links are positioned properly...                                               | 4. The Login and Sign up links do not look like...                                                               |
| Functionality of Search Box               |                                                                                                            |                                                                                                                    |
| The search box performs the functionality... | The search box does not perform the functionality...                                                   | It is not integrated with the backend API...                                                                      |
| Functionality of Login and Sign up Links  |                                                                                                            |                                                                                                                    |
| On click of the Login link, a Sign...     | The Sign in or Sign up page does not appear on clicking...                                               |                                                                                                                    |
| Appearance of Sign in and Sign up Pages   |                                                                                                            |                                                                                                                    |
| 1. The Sign in page displays a form...    | 1. The Sign in page does not contain the forms...                                                        |                                                                                                                    |
| 2. The Sign up page displays a form...    | 2. The Sign up page does not contain the forms...                                                        |                                                                                                                    |
| Functionality of Sign up Form             |                                                                                                            |                                                                                                                    |
| 1. The form validation works properly...  | 1. The signup form is not present and/or...                                                               |                                                                                                                    |
| 2. When the Sign up button is clicked...  | 2. The Sign up button is not present and/or...                                                            |                                                                                                                    |
| 3. Successful or failed signup is handled... | 3. Successful or failed signup is not handled properly...                                                 |                                                                                                                    |
| Functionality of Sign In Form             |                                                                                                            |                                                                                                                    |
| 1. The form validation works properly...  | 1. The login form is not present and/or...                                                                |                                                                                                                    |
| 2. When the Sign in button is clicked...  | 2. The Sign in button is not present and/or...                                                            |                                                                                                                    |
| 3. Successful or failed login is handled... | 3. Successful or failed login is not handled properly...                                                  |                                                                                                                    |
| Appearance of the Product Categories      |                                                                                                            |                                                                                                                    |
| The categories are listed in the same...  | The categories are missing and/or are not displayed properly...                                            |                                                                                                                    |
| Functionality of the Product Categories   |                                                                                                            |                                                                                                                    |
| 1. All the products are displayed when...  | 1. The All button is missing and/or...                                                                    |                                                                                                                    |
| 2. On click of a category, only the...     | 2. The categories aren't clickable and/or...                                                               |                                                                                                                    |
| 3. An API call is made to fetch the...     | 3. The API call is missing or is not made...                                                              |                                                                                                                    |
| Appearance of Sort Menu                   |                                                                                                            |                                                                                                                    |
| The Sort menu is the same as mentioned... | The Sort menu is missing and/or is not the same...                                                         |                                                                                                                    |
| Functionality of the Sort Menu             |                                                                                                            |                                                                                                                    |
| 1. The sort menu has the four sorting...   | 1. The Sort menu has fewer or more sorting options.                                                        |                                                                                                                    |
| 2. The sorting options function...         | 2. The sorting options do not work correctly...                                                            |                                                                                                                    |
| Appearance of the Products                 | The products are displayed as per the project statement.                                                  | There are no products displayed and/or...                                                                         |
| Appearance of the Product Details Page     |                                                                                                            |                                                                                                                    |
| 1. The product details are mentioned...    | 1. The product details are missing and/or...                                                               |                                                                                                                    |
| 2. An API call is made to fetch a specific... | 2. The API call is missing or is not made...                                                               |                                                                                                                    |
| Functionality of the Product Details Page  |                                                                                                            |                                                                                                                    |
| 1. A user routes to the product details... | 1. There is no hyperlink for the product details...                                                        |                                                                                                                    |
| 2. There is a 'Place Order' button on...   | 2. There is no button on the product details...                                                             |                                                                                                                    |
| Appearance of the Create Order Page        |                                                                                                            |                                                                                                                    |
| 1. There is a stepper menu that has...     | 1. The stepper is not present or has...                                                                     |                                                                                                                    |
| 2. The first step displays the item...     | 2. The first step is not present and/or...                                                                 |                                                                                                                    |
| 3. The second step adds the address...      | 3. The second step is not present and/or...                                                                |                                                                                                                    |
| 4. The third step is to review the order... | 4. The third step is not present and/or...                                                                 |                                                                                                                    |
| Functionality of the First Step            |                                                                                                            |                                                                                                                    |
| 1. Only the product that is chosen...      | 1. The product chosen by the user isn't displayed...                                                       |                                                                                                                    |
| 2. On click on the Next button, the...     | 2. The Next button is not present and/or...                                                                |                                                                                                                    |
| Functionality of the Second Step           |                                                                                                            |                                                                                                                    |
| 1. There is a form to capture user address... | 1. There is no form present to capture...                                                                  |                                                                                                                    |
| 2. All the fields and validations...        | 2. The fields are missing and/or the validations...                                                         |                                                                                                                    |
| 3. An API call is made to add the address... | 3. The API call is missing or is not made...                                                               |                                                                                                                    |
| 4. On click on the Next or back button...  | 4. The next or back buttons are not present...                                                             |                                                                                                                    |
| Functionality of the Third Step            |                                                                                                            |                                                                                                                    |
| 1. The product that the user wants to...    | 1. The product chosen by the user isn't displayed...                                                       |                                                                                                                    |
| 2. The address that the user has added...  | 2. The address that the user choose isn't...                                                               |                                                                                                                    |
| 3. On clicking the Place order button...   | 3. The Place Order or back buttons are not...                                                              |                                                                                                                    |
| Appearance of the Manage Products Page     |                                                                                                            |                                                                                                                    |
| When the Admin user logs in, the "Add...    | 1. The link is missing and/or is not...                                                                    |                                                                                                                    |
| The modify and delete icons are present... | 2. There are no buttons to edit and/or...                                                                  |                                                                                                                    |
| Functionality of the Manage Products Page  |                                                                                                            |                                                                                                                    |
| On click of the Add Product link, the...   | 1. The page is not present or is visible...                                                                |                                                                                                                    |
| When the edit icon is clicked, the...       | 2. The page is not present or is visible...                                                                |                                                                                                                    |
| When the delete icon is clicked, a...      | 3. The modal box is not present.                                                                          |                                                                                                                    |
| Appearance and functionality of Add...     |                                                                                                            |                                                                                                                    |
| The page contains a form.                  | 1. The form is not created.                                                                                |                                                                                                                    |
| All the fields and validations are...      | 2. The fields are missing and/or the validations...                                                         |                                                                                                                    |
| An API call is made to add the product...  | 3. The API call is missing or is not made...                                                               |                                                                                                                    |
| The added product is displayed on...       | 4. The added product is not displayed on the UI.                                                            |                                                                                                                    |
| Appearance and functionality of Delete...  |                                                                                                            |                                                                                                                    |
| The modal has details as per the project... | 1. The modal is not created or has missing...                                                               |                                                                                                                    |
| The buttons in the modal function...       | 2. The button are missing or do not...                                                                      |                                                                                                                    |
| An API call is made to delete the...        | 3. The API call is missing or is not made...                                                               |                                                                                                                    |
| The deleted product is not displayed...     | 4. The deleted product is still displayed on...                                                             |                                                                                                                    |
| Appearance and functionality of Modify...  |                                                                                                            |                                                                                                                    |
| The page contains a form.                  | 1. The form is not created.                                                                                |                                                                                                                    |
| All the fields have prefilled values...     | 2. The fields with prefilled values are...                                                                  |                                                                                                                    |
| An API call is made to modify the...        | 3. The API call is missing or is not made...                                                               |                                                                                                                    |
| The modified product is displayed on...     | 4. The modified product is not displayed on...                                                             |                                                                                                                    |
| Adherence to Coding Guidelines             |                                                                                                            |                                                                                                                    |
| Best Coding Practices                      |                                                                                                            |                                                                                                                    |
| 1. All the features are implemented...      | 1. All the features are not implemented...                                                                 |                                                                                                                    |
| 2. The web application is configured...     | 2. The web application does not follow...                                                                  |                                                                                                                    |
| 3. The code is well documented and...       | 3. The code is not well documented and...                                                                   |                                                                                                                    |
| 4. The code is committed from time...       | 4 Incremental commits are not made with...                                                                 |                                                                                                                    |








