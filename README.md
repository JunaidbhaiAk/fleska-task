

FLESKA - Food Ordering System
=============
FLESKA is a Food Orderding System where users can explore the menu and order food.The system have features of view Previous Orders,Cart


Project Structure
-------------
# client - Holds the client application

* [public/](.\client\public) - Holds our static files
  * [vite.svg](.\client\public\vite.svg)
* [src/](.\client\src) - Holds our main src files
  * [assets/](.\client\src\assets) - Any required assets can be stored here
    * [react.svg](.\client\src\assets\react.svg)
  * [components/](.\client\src\components) - React Components which is Building Blocks of our Pages
    * [CartDrawer/](.\client\src\components\CartDrawer) - Drawer of Our Cart Which occur on the left side
      * [CartDrawer.tsx](.\client\src\components\CartDrawer\CartDrawer.tsx) - Main Cart Component
      * [CartDrawerFooter.tsx](.\client\src\components\CartDrawer\CartDrawerFooter.tsx)  - Cart Footer Containe button for placing order or clear cart
      * [CartDrawerHeader.tsx](.\client\src\components\CartDrawer\CartDrawerHeader.tsx)  - cart header for input of call and address
      * [CartDrawerItem.tsx](.\client\src\components\CartDrawer\CartDrawerItem.tsx)      - Cart Items that is added
    * [SummaryDrawer/](.\client\src\components\SummaryDrawer)               - Previous Order Summary Compo Folder
      * [SummaryContent.tsx](.\client\src\components\SummaryDrawer\SummaryContent.tsx) - Previous Order Contents
      * [SummaryDrawer.tsx](.\client\src\components\SummaryDrawer\SummaryDrawer.tsx)   - Main Compo to be display on Drawer
      * [SummaryTotal.tsx](.\client\src\components\SummaryDrawer\SummaryTotal.tsx)     - to display at last of summary total
    * [Menu.tsx](.\client\src\components\Menu.tsx)       - To display all the dishes in grid style
    * [Navbar.tsx](.\client\src\components\Navbar.tsx)   - navbar of our page with cart button
    * [TypeFilter.tsx](.\client\src\components\TypeFilter.tsx) - filter componets which contain buttons like dinner,snacks,launch
  * [context/](.\client\src\context) - React Context Files
    * [CartContext.tsx](.\client\src\context\CartContext.tsx) - Cart Context api which contain usereducer hook and state of our cart
    * [DishContext.tsx](.\client\src\context\DishContext.tsx) - Dish Context used for providing dish items to our webpage used context because of prop drilling
  * [hooks/](.\client\src\hooks) - Custom Hooks Folder
    * [useClientOrder.tsx](.\client\src\hooks\useClientOrder.tsx)  - Used for getting all clients orders by clientId
    * [useSummaryOrder.tsx](.\client\src\hooks\useSummaryOrder.tsx) -  Used for getting order summary by using order id
  * [utils/](.\client\src\utils) - utility folder
    * [api.ts](.\client\src\utils\api.ts) - contain functions for fetching and posting data mostly api calls
    * [reducer.ts](.\client\src\utils\reducer.ts) - cartReducer function which is used in CartContext reducer fnc contain logic of adding and removing items from cart
    * [type.ts](.\client\src\utils\type.ts) - contain types which is used in our whole projects
  * [App.tsx](.\client\src\App.tsx) - file which renders all different components
  * [index.css](.\client\src\index.css) - default css
  * [main.tsx](.\client\src\main.tsx) - root file of our project where context our wrapped and our whole app is renderd
  * [vite-env.d.ts](.\client\src\vite-env.d.ts) - vite file
* [.env](.\client\.env) - enviormnet var for our projects
* [.eslintrc.cjs](.\client\.eslintrc.cjs) - eslint config default
* [.gitignore](.\client\.gitignore)
* [index.html](.\client\index.html) - main html where our page will be rendered
* [package-lock.json](.\client\package-lock.json)
* [package.json](.\client\package.json) - Defines npm behaviors like the scripts and info of packages installed
* [tsconfig.json](.\client\tsconfig.json)
* [tsconfig.node.json](.\client\tsconfig.node.json)
* [vite.config.ts](.\client\vite.config.ts)

# server - Holds the server application

* [src/](.\server\src) - main source folder
  * [config/](.\server\src\config) - This holds our configuration files, like database config uri
    * [db.js](.\server\src\config\db.js) - Our database config like connection and instance of our database
  * [controllers/](.\server\src\controllers) - These hold all of the callback functions  that each route will call
    * [dish.controller.js](.\server\src\controllers\dish.controller.js) - callback functions for dishes routes
    * [order.controller.js](.\server\src\controllers\order.controller.js) - callback functions for orders routes
  * [models/](.\server\src\models) - This holds all of our data models
    * [dish.model.js](.\server\src\models\dish.model.js) - schema or model of dish
    * [order.model.js](.\server\src\models\order.model.js) - schema or model of order
  * [routes/](.\server\src\routes) - This holds all of our HTTP to URL path associations for each unique url
    * [dish.routes.js](.\server\src\routes\dish.routes.js) - routes for our dishes
    * [order.routes.js](.\server\src\routes\order.routes.js) - routes for our orders
  * [app.js](.\server\src\app.js) - the root of our server where server starts
  * [dummyData.json](.\server\src\dummyData.json) - Contain dummy data of dishes for inserting at start of server
* [.env](.\server\.env) - enviormnet var for our projects
* [package-lock.json](.\server\package-lock.json)
* [package.json](.\server\package.json) - Defines npm behaviors like the scripts and info of packages installed


Getting Started
-------------
Prerequisites
----------------
- NodeJs - ^ 16
- MySQL
  
1. Clone the Repo
    Clone the repo by using command or download the repo

    `git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY`

2 . Create Database
  Create a database in mysql first with any name but make sure to remember the name for future use Example -

  `CREATE DATABASE fleska_db`

3 . Starting Server
  - Now go to server dir - `cd server`
  - Create a .env file on the dir and copy and paste this config
      PORT = 3000
      DB_HOST = 'localhost' //provide your db host name 
      DB_USER = 'root' // provide your db user name
      DB_PASS = 'mysql123' //password for your db
      DB_NAME = 'fleska_db' //name of the db which we created in previous step
  	
  - now run command `npm install`
  - After sucessfull installation run command - `npm run dev` to start dev server

4 . Starting Client
  - Navigate to main repo and open new terminal dont close the sever terminal
  - Now go to client dir - `cd client`
  - create .env file in root of client and paste the config
  	`VITE_SERVER_URL=http://localhost:3000/` //replace 3000 if you are running on diff port
  - now run` npm install`
  - After sucessfull installation run command - `npm run dev` to start client
  - Open browser and navigate to this url - http://127.0.0.1:5173/

Working Video
----------------------
[Video](https://www.youtube.com/watch?v=5GdXjD45zOQ)
