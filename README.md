# Documentation For Sunroof Coffee

<details><summary>For Users</summary>

## Features

### Events Page

- User enters name, email, and message into form fields.
- When the user presses the submit button, a notification appears at the top of the screen indicating if it was successful or not.

### Reset Password Page

- User enters new password and confirms it.
- When the user presses the "Reset Password" button, text or a notification appears to indicate if it was successful or if there was an error in the input.

### Login Page

- User enters username and password into form fields.
- When the user presses the "Login" button with incorrect credentials, a notification appears indicating the username or password is incorrect if unsuccessful.
- When the user presses the "Login" button with proper credentials, the user gets redirected to the CIMS Page.

### CIMS Page

#### Menu Items

- User can press the edit or delete button for each item, or they can press the add button.
- When the user presses the "Add Menu Item" button, a popup appears prompting them to enter a Title, Type, Description, and Price. If the "Add Item" button is pressed and all fields are completed then the item gets added to the database and the table. If the "Add Item", button is pressed but not all fields are completed, a notification appears indicating that all fields are mandatory.
- When the user presses the edit menu item button (indicated by an edit icon), a popup appears with the fields of Title, Type, Description, and Price of the given item. If the user makes an edit and presses "Save Changes" then the updates get sent to the backend and update on the table.
- When the user presses the delete menu item button (indicated by a delete icon), a popup appears confirming that the user wants to delete the item. If the "Delete" button is pressed on this popup, the item gets deleted from the database and from the table.

#### Menu Types

- User can press the edit or delete button for each type, or they can press the add button.
- When the user presses the "Add Menu Type" button, a popup appears prompting them to enter a Type and pick a color. If the "Submit" button is pressed and all fields are completed then the item gets added to the database and the table. If the "Submit", button is pressed but not all fields are completed, a notification appears indicating that all fields are mandatory.
- When the user presses the edit menu type button (indicated by an edit icon), a popup appears with the fields of Type and Color (shown by the color picker) of the given item. If the user makes an edit and presses "Submit" then the updates get sent to the backend and update on the table.
- When the user presses the delete menu type button (indicated by a delete icon), a popup appears confirming that the user wants to delete the type. If the "Delete" button is pressed on this popup, the type gets deleted from the database and from the table.

### Mobile Ordering Page

- User can press the "Add" button on any menu item
- When the "Add" button is pressed, a popup appears indicating the options that the user has for that item.
- If the user presses the "Add to Order" button and not all required fields are completed, a notification appears indicating and text indicating this appears next to all required, empty fields.
- If the user presses the "Add to Order" button and all required fields are completed, the popup disappears and the item with all modifications gets sent to the cart.

### Cart Page

- Users can press the "Continue Shopping", one of the tip options, delete, or the checkout button.
- The "Continue Shopping" button sends the user back to the mobile ordering page.
- The delete button deletes that specific menu item.
- The tip option changes the designated amount of money that the user can tip. This gets reflected on the order summary.
- The checkout button creates a popup where the user can input their name and any notes for the order. The user can then press the "Place Order" button that will send them to the pay page.

### Pay Page

- User can press the google pay, enter their card information and press pay, or enter their gift card number pay with gift card button.
- If the user presses the google pay button, the external google pay popup appears for the user to complete.
- If the user fills out their credit card information and presses pay, a backend call is made. Based on the success of the payment, the page prompts the user accordingly.
- If the user fills out their gift card information and presses pay, a backend call is made. Based on the success of the payment, the page prompts the user accordingly.

</details>
<details>
<summary>For Developers</summary>

# How to Modify/Extend Software

## Making Changes

- Changes can be made using a code editor once the repo has been cloned to your personal device. Test thoroughly, document changes, and submit for review and integration.

- Components
  -- Navigate to Sunroof-Coffee/frontend/src/assets/components
  -- Add the desired CSS and TSX files to create/update/delete desired components

- Pages
  -- Navigate to Sunroof-Coffee/frontend/src/assets/pages
  -- Add the desired CSS and TSX files to create/update/delete desired pages
  -- Adjust the routing if necessary for all pages in Sunroof-Coffee/frontend/src/assets/routing

- Page Routing
  -- The website router can be found in Sunroof-Coffee/frontend/src/App.tsx
  -- Inside App.tsx, routes include the login, cims and reset password paths as well as the other routes found in Sunroof-Coffee/frontend/src/assets/routing that utilize the Navbar and Footer
  -- Sunroof-Coffee/frontend/src/assets/routing also contain the Navbar and Footer components

- Images
  -- Add new .jpg files in Sunroof-Coffee/frontend/src/assets

**Must use Square Sandbox Credentials in env variables, these can be retrieved from square developer account**

## Compiler, Languages, Build Management, Dependencies, Automated Builds

- **Compiler/Languages**: MongoDB, Express.js, React, Node.js

- **Build Management**: Frontend: Vite, Backend: Node.js

- **Dependencies**: Refer to `package.json` files in `Sunroof-Coffee`, `Sunroof-Coffee/frontend`, and `Sunroof-Coffee/backend`.

- **Automated Builds**:

  - `install-server`: `cd backend && npm install`

  - `start-server`: `cd backend && node app.js`

  - `install-frontend`: `cd frontend && npm install`

  - `build-frontend`: `cd frontend && npm run build`

  - `start-frontend`: `cd frontend && npm run dev`

## Backlog / Bug Lists

- Backlogs/Bug Lists are managed on [Jira](https://sunroof-coffee.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog).

- Email dev@sunroofcoffee.com or patrick.swiger@att.net for creds and access

- No major issues regarding migrating to better resources or versions.

## Styling

- Use camel case for functions and variable names.

- Use Prettier for code formatting

- Use kebab case for endpoints.

## Automated Testing

- Utilizes Jest and SuperTest.

- Navigate to the backend directory: `Sunroof-Coffee/backend`.

- Run the following command: `npm test`.

- Utilizes a separate test database named TestDB, which mimics the current one.

- Test file location: `Sunroof-Coffee/backend/test/menu.test.js`.

## Cloud Deployment

The three tiers of the application are hosted as follows:

- Database: MongoDB Atlas Cloud Hosting free tier (m0). The backend is connected to the database through the connection string in the environment variables.
- Backend: AWS EC2 instance. The actual backend is ran as a systemd job to allow it to accept requests even if no active terminal is open. Several scripts were written and stored in the EC2 that allow easy updating from the git repository. They are detailed in the following section.
- Frontend: AWS Amplify instance. This instance automatically rebuilds and deploys upon new commits to main. Environment variables contain the api connection string.

# How to Install

To run the site locally on your machine, you must recreate the entire tech stack. This includes the frontend, backend, and database.

## Required Software

- MongoDB, version 6.0.2 or latest
- MongoDB Compass, version 1.43.2 or latest
- Node JS, version 18.14.2 or latest
- NPM, version 9.5.0 or latest
- An IDE or text editor

## Deploying the application locally

1. Clone the provided repository at the desired location, and open the directory in your editor
2. In mongodb compass, add the 4 different data types to your local mongodb instance, and copy and paste the connection string/URI to the "MONGODB_URI" variable in the .env file in the backend directory
3. Run the following commands from the root of the repo:

- npm run install-server
- npm run install-frontend

4. Create a split terminal. Navigate the first one to the backend, and run the following command:

- npm run dev

5. Navigate the second to the frontend directory and run the following command:

- npm run dev.

6. Ensure that the port in the backend deploys onto is port 5000. If not, edit the PORT variable in backend/.env
7. Ensure the variable VITE_API_CONNECTION in frontend/.env points to port 5000.

## External Resources Used

- Square for payment handling in mobile ordering
- AWS EC2 for cloud hosting of backend
- AWS Amplify instance for serverless hosting of frontend
- MongoDB Atlas for cloud hosting of database

# Backend functions and endpoints

### Send Event Email

Send an email for an event.

#### Endpoint

`POST /send-email`

#### Request Body

- `firstName` (string): First name of the recipient.
- `lastName` (string): Last name of the recipient.
- `email` (string): Email address of the recipient.
- `message` (string): Message to include in the email.

#### Responses

- 200 OK: Email sent successfully.
- 400 Bad Request: If there is an issue sending the email.

#### Example Request

jsonCopy code

`{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com",
  "message": "Join us for our event!"
}`

#### Links

The response is sent to the Events Page. The Events Page displays a notification on screen indicating the success of the response.

---

### Send Forgot Password Email

Send an email for resetting a forgotten password.

#### Endpoint

`POST /forgot-password`

#### Responses

- 200 OK: Email sent successfully.
- 400 Bad Request: If there is an issue sending the email.

#### Links

The response is sent to the Login Page. The Login Page displays a notification on screen indicating the success of the response.

---

### Reset Password Attempt

Verify and validate a reset password token.

#### Endpoint

`POST /reset-password-attempt`

#### Request Body

- `token` (string): The reset password token.

#### Responses

- 200 OK: Token is valid.
- 400 Bad Request: If the token is missing, invalid, or expired.

#### Links

The user will be prompted that the password is being reset and that they will be redirected when it is done.

---

### Update Admin Password

Update the password for an admin account.

#### Endpoint

`POST /update-admin`

#### Request Body

- `username` (string): The username of the admin account.
- `password` (string): The new password for the admin account.

#### Responses

- 200 OK: Update successful.
- 400 Bad Request: If the username is invalid.
- 500 Internal Server Error: If there is an error updating the password.

#### Links

The response is sent to the Reset Password Page. The Reset Password Page displays a notification on screen indicating the success of the response.

---

### Login Attempt

Attempt to log in with a username and password.

#### Endpoint

`POST /login-attempt`

#### Request Body

- `username` (string): The username to log in with.
- `password` (string): The password to log in with.

#### Responses

- 200 OK: Login successful.
- 400 Bad Request: If the credentials are invalid.
- 500 Internal Server Error: If there is an error logging in.

#### Links

The response is sent to the Login Page. The Login Page displays a notification on screen indicating the success of the response.

## API Endpoint: Get Menu Items

- **URL:** `/menuItems`
- **Method:** `GET`
- **Description:** Retrieves all menu items from the database.
- **Authorization:** Not required.

### Request

- **Parameters:** None
- **Headers:** None

### Response

- **Status:** `200 OK`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:**

```json
{
  "message": [
    // Array of menu items retrieved from the database
  ]
}
```

## API Endpoint: Get Featured Menu Items

- **URL:** `/featured`
- **Method:** `GET`
- **Description:** Retrieves featured menu items from the database based on their type ID.
- **Authorization:** Not required.

### Request

- **Parameters:** None
- **Headers:** None

### Response

- **Status:** `200 OK`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:**

```json
{
  "featured": [
    // Array of featured menu items retrieved from the database
  ]
}
```

## CRUD Menu Item API Calls

### Endpoint: Create Menu Item

- **URL:** `/create-menu-item`
- **Method:** `POST`
- **Description:** Creates a new menu item.
- **Authorization:** Required.

#### Request Body

- `type` (string): Type of the menu item.
- `typeId` (string): Type ID of the menu item.
- `description` (string): Description of the menu item.
- `title` (string): Title of the menu item.
- `price` (number): Price of the menu item.
- `image` (string): Image URL of the menu item.
- `mobileOrdering` (boolean): Flag indicating mobile ordering availability.

#### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:** JSON object containing the created menu item.

#### Error Response

- **Status Code:** `400`
- **Content:** Indicates that an error occurred during menu item creation.

### Endpoint: Update Menu Item

- **URL:** `/update-menu-item`
- **Method:** `POST`
- **Description:** Updates an existing menu item.
- **Authorization:** Required.

#### Request Body

- `id` (string): ID of the menu item to be updated.
- `type` (string): Type of the menu item.
- `typeId` (string): Type ID of the menu item.
- `description` (string): Description of the menu item.
- `title` (string): Title of the menu item.
- `price` (number): Price of the menu item.
- `image` (string): Image URL of the menu item.
- `mobileOrdering` (boolean): Flag indicating mobile ordering availability.

#### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:** JSON object containing the updated menu item.

#### Error Response

- **Status Code:** `400`
- **Content:** Indicates that an error occurred during menu item update or menu item not found.

### Endpoint: Delete Menu Item

- **URL:** `/delete-menu-item`
- **Method:** `POST`
- **Description:** Deletes a menu item.
- **Authorization:** Required.

#### Request Body

- `id` (string): ID of the menu item to be deleted.

#### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:** JSON object containing the deleted menu item.

#### Error Response

- **Status Code:** `400`
- **Content:** Indicates that an error occurred during menu item deletion or menu item not found.

## Express Middleware: Serve Static Files

- **Description:** Serves static files from the specified directory.
- **Middleware:** `express.static(__dirname + "/public")`
- **Directory:** `/public`

## Environment Configuration

- **Environment Variable:** `SQ_ENVIRONMENT`
- **Description:** Specifies the environment for Square API requests.
- **Supported Values:** `production`, `sandbox`

## Square API Configuration

- **Base URL (Production):** `https://connect.squareup.com`
- **Base URL (Sandbox):** `https://connect.squareupsandbox.com`
- **Client Configuration:** Configures Square default client based on the environment.
- **OAuth API Instance:** Configures Square OAuth API instance for authorization.

## OAuth Scopes

- **Description:** Defines the scopes required for OAuth authorization.
- **Scopes:**
  - `ITEMS_READ`
  - `MERCHANT_PROFILE_READ`
  - `PAYMENTS_WRITE_ADDITIONAL_RECIPIENTS`
  - `PAYMENTS_WRITE`
  - `PAYMENTS_READ`
  - `ORDERS_WRITE`
  - `ORDERS_READ`

## Endpoint: Request OAuth Token

- **URL:** `/request_token`
- **Method:** `GET`
- **Description:** Serves the link for merchants to authorize the application.
- **Cookies:** Sets the `Auth_State` cookie for protection against cross-site request forgery.
- **Response:** Renders an authorization link for merchants to click.

## Endpoint: Refresh OAuth Token

- **URL:** `/refresh_token`
- **Method:** `GET`
- **Description:** Refreshes OAuth token using the refresh token obtained during authorization.
- **Response:** Sends a success message upon successful token refresh.

## Endpoint: OAuth Callback

- **URL:** `/callback`
- **Method:** `GET`
- **Description:** Handles Square's redirect to the application's redirect URL after authorization.
- **Parameters:**
  - `state`: The Auth State set in `/request_token`.
  - `response_type`: The type of response; should be "code".
  - `code`: The authorization code returned after authorization.
- **Response:** Renders appropriate messages based on the authorization result.

## Endpoint: Create Order

- **URL:** `/create-order`
- **Method:** `POST`
- **Description:** Creates a new order with the specified items and details.
- **Authorization:** Required.

### Request

- **Body Parameters:**
  - `name` (string): Recipient's name for the order.
  - `notes` (string): Additional notes for the order.
  - `items` (JSON array): Array of items to be included in the order.
    - `itemQuantity` (number): Quantity of the item.
    - `variationID` (string): ID of the item variation.
    - `modifiers` (array): Array of modifiers for the item.
      - `catalogObjectId` (string): ID of the modifier.

### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `text/plain`

#### Success Response

- **Status Code:** `200`
- **Content:** ID of the created order.

#### Error Response

- **Status Code:** `400`
- **Content:** Indicates that the request failed and should be retried.

## Endpoint: Pay Order

- **URL:** `/pay-order`
- **Method:** `POST`
- **Description:** Processes payment for the specified order using the provided payment token.
- **Authorization:** Required.

### Request

- **Body Parameters:**
  - `orderId` (string): ID of the order to be paid.
  - `tip` (number): Tip amount for the payment.
  - `sourceId` (string): Payment token (e.g., card nonce) for processing the payment.

### Response

- **Status:** `200 OK`, `201 Created`, or `400 Bad Request`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200` or `201`
- **Content:** JSON object containing the payment status.

#### Error Response

- **Status Code:** `400`
- **Content:** Error message indicating the reason for the failure.

## Endpoint: Get Order Total

- **URL:** `/get-order-total`
- **Method:** `POST`
- **Description:** Retrieves the total amount of the specified order, considering any tendered amounts.
- **Authorization:** Required.

### Request

- **Body Parameters:**
  - `orderId` (string): ID of the order to retrieve the total amount.

### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `text/plain`

#### Success Response

- **Status Code:** `200`
- **Content:** Total amount of the order as a string.

#### Error Response

- **Status Code:** `400`
- \*\*

## Endpoint: Get Mobile Ordering Menu

- **URL:** `/get-mobile-ordering-menu`
- **Method:** `GET`
- **Description:** Retrieves the mobile ordering menu with categories and items.
- **Authorization:** Required.

### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:** JSON object containing categories and their associated items.

#### Error Response

- **Status Code:** `400`
- **Content:** Indicates that the request failed and should be retried.

## Function: buildMod

- **Description:** Builds an array of modifiers for an item.
- **Parameters:**
  - `modifiers` (array): Array of modifier objects.
- **Returns:** Array of modifier objects with catalog object ID, name, and price.

## Function: buildModList

- **Description:** Builds a modifier list object with name, selection type, and modifiers.
- **Parameters:**
  - `modList` (object): Modifier list object.
- **Returns:** Modifier list object with name, selection type, and modifiers array.

## Endpoint: Get Mobile Ordering Item

- **URL:** `/get-mobile-ordering-item`
- **Method:** `POST`
- **Description:** Retrieves details of a mobile ordering item, including modifiers.
- **Authorization:** Required.

### Request

- **Body Parameters:**
  - `objectId` (string): ID of the catalog object representing the item.

### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:** JSON object containing details of the item, including modifiers.

#### Error Response

- **Status Code:** `400`
- **Content:** Indicates that the request failed and should be retried.

## Function: getItemPrice

- **Description:** Calculates the total price of an item including modifiers.
- **Parameters:**
  - `itemPrice` (number): Base price of the item.
  - `modifiers` (array): Array of modifier objects.
- **Returns:** Total price of the item including modifiers.

## Function: buildModCart

- **Description:** Builds an array of modifiers for the cart items.
- **Parameters:**
  - `modifiers` (array): Array of modifier objects.
- **Returns:** Array of modifier objects with name and price.

## Endpoint: Get Mobile Ordering Cart

- **URL:** `/get-mobile-ordering-cart`
- **Method:** `POST`
- **Description:** Retrieves the mobile ordering cart items with details, including modifiers.
- **Authorization:** Required.

### Request

- **Body Parameters:**
  - `object` (array): Array of objects representing cart items.
    - `itemID` (string): ID of the catalog object representing the item.
    - `itemQuantity` (number): Quantity of the item in the cart.
    - `modifiers` (array): Array of modifier object IDs associated with the item.

### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:** JSON object containing details of the cart items, including modifiers and total price.

#### Error Response

- **Status Code:** `400`
- **Content:** Indicates that the request failed and should be retried.

## Endpoint: Get Featured Items

- **URL:** `/get-featured-items`
- **Method:** `GET`
- **Description:** Retrieves a list of featured items with their names, descriptions, and image URLs.
- **Authorization:** Required.

### Response

- **Status:** `200 OK` or `400 Bad Request`
- **Content Type:** `application/json`

#### Success Response

- **Status Code:** `200`
- **Content:** JSON array containing details of featured items including name, description, and image URL.

#### Error Response

- **Status Code:** `400`
- **Content:** Indicates that there was an error while retrieving featured items.

</details>

## FAQs

1. **Is there a mobile app available for ordering?**
   - No, but our website is designed for mobile responsiveness! You can reach our website from your phone to place orders, view our menu, and navigate our site resources.
2. **How are online orders prepared and fulfilled?**
   - Our coffee shop partners with Square for payment processing and order fulfillment. When you order on our website, we communicate with Square to confirm and collect payment, then sending your order to our order system in house so we can prepare your order!
3. **How can I provide feedback or suggestions about the website or services?**
   - Feel free to make use of our sunroof emails listed at the bottom of every page! You can send an email to us to get in contact with any questions or concerns, or just leave a suggestion or comment on our services that you would like to see changed or updated! Please use nick@sunroofcoffee.com or reid@sunroofcoffee.com as opposed to our events form which we keep for catering and event requests!
4. **Can I schedule orders for a specific date and time?**
   - Currently no, the format of our payment and point of sale processing is intended for orders to be made on an ASAP basis! Please plan accordingly when ordering to help us get you the freshest food and best service possible!

## Gotchas and Problems

- No issues from a user perspective getting this application up and running as it is web hosted and fully insulated from any user end setup / installation process!

## Possible External Issues

- Beyond our own codebase, our system relies on Square, MongoDB Atlas, Amazon Web Services EC2 and Amplify Instances. Any of these services having issues, outages, or security concerns could adversely affect the end user which is beyond our immediate control as a development team.
