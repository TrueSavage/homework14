#Reverse Engineering User Story


	▪	package.json
	
	
As a developer I’m going to utilize NPM Node.js and when I install NPM at the Terminal I will use this command NPM Init and it will create a file with information about this application. 

    
    

	▪	server.js
	
	
As a developer I will utilize the server.js to activate the Routes and open the PORT for the WEBSITE.
	▪	Config config.json

As a developer this file will have information for MYSQL Database.
	▪	PASSPORT .js


As a Developer I want to create a secure environment so that non-authenticated users will be blocked from accessing the site. Passport is a Middleware tool to create  authentication and verification allowing access to the user based on permissions and proper username and password utilization!
As a User I want to be secure and safe when using this application. By signing in to my account and having it authenticated help to protects my account from being accessed by Bad Guys…
Passport is authentication middleware for Node. It is designed to serve a singular purpose: authenticate requests. When writing modules, encapsulation is a virtue, so Passport delegates all other functionality to the application. This separation of concerns keeps code clean and maintainable, and makes Passport extremely easy to integrate into an application
In modern web applications, authentication can take a variety of forms. Traditionally, users log in by providing a username and password. With the rise of social networking, single sign-on using an OAuth provider such as Facebook or Twitter has become a popular authentication method. Services that expose an API often require token-based credentials to protect access.
	
  
  ▪	middleware  Authenticated.js
	
	
As a developer I will utilize Middleware to be a  HELPER for    html-routes.js.  which RETURNS  information that allows html-routes.js to know whether the user is logged in or not. 

	
  ▪	Models index.js
	
	
As a Developer I will create a INDEX.JS file located within MODELS folder that Gathers up and creates connections to all defined databases. 

 
	▪	user.js
	
	
As a developer I will create a User.js file to provide definitions for MySQL database.
// Requiring bcrypt for password hashing. Using the bcryptjs version
 as the regular bcrypt module sometimes causes errors on Windows machines
var bcrypt = require("bcryptjs");
// Creating our User model
module.exports = function(sequelize, DataTypes) {
  var User = sequelize.define("User", {
    // The email cannot be null, and must be a proper email before creation
    email: {
      type: DataTypes.STRING,
      allowNull: false,
      unique: true,
      validate: {
        isEmail: true
      type: DataTypes.STRING,
      allowNull: false
  User.prototype.validPassword = function(password) {
    return bcrypt.compareSync(password, this.password);
  User.addHook("beforeCreate", function(user) {
    user.password = bcrypt.hashSync(user.password, bcrypt.genSaltSync(10), null);
  return User;


	▪	Public
	
	
login.html, members.html, signup.html
As a Developer the HTML will create the structure of the following pages. Login Html the User will log in with their email and password combination. This uses the file login.js for functionality!!!
As a developer after the User logs in as an existing account holder or creates a new account, the Member Page will be displayed.  HTML will provide the structure of the page and the members.js will provide the needed functionality.
 As a New User I will be able to sign up for an account on the Sign up page! As a developer I will use HTML to create a structure for the page and use JS for the functionality code. As user I will sign up with my email and password combination.
login.js, members.js,  signup.js
As a developer I will utilize Login.js, Members.js and Signup.js each of these are Helper’s  for the Login.html page. This  will call the login API and redirects to members.html if successful. The member.js is the HELPER to the member.html and the signup.js is the HELPER for the signup .html file It calls the login API and redirects to members.html if successful.


	▪	Routes
	
	
api-routes.js

Routes API calls requiring access to the database.  Routes allow calls to be made allowing a user access /members.  Uses middleware Passport to make sure a user is properly logged into their account otherwise they will be redirected to the login page.
.gitignore File allows Github to ignore files that are too large much and would affect the performance. 
 
