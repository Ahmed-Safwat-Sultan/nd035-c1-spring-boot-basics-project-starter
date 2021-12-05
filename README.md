# Simple Cloud Storage
The functionality splits to three parts
1. **Simple File Storage:** Upload/download/remove files
2. **Note Management:** Add/update/remove text notes
3. **Password Management:** Save, edit, and delete website credentials.  


## Starter Project
 [You can download or clone the starter repository here](https://github.com/udacity/nd035-c1-spring-boot-basics-project-starter/tree/master/starter/cloudstorage).

a database schema for the project and has added it to the `src/main/resources` directory. That means you don't have to design the database, only develop the Java code to interact with it. 

Your tech lead also created some HTML templates from the design team's website mockups, and they placed them in the `src/main/resources/templates` folder. These are static pages right now, and you have to configure them with Thymeleaf to add functionality and real data from the server you develop. You may also have to change them to support testing the application.

From the link above, you can download the starter code and open it as a Maven project in IntelliJ.

## Added to the starter code
these are implemented to the starter code:

1. The back-end with Spring Boot
2. The front-end with Thymeleaf
3. Application tests with Selenium

### The Back-End
The back-end is all about security and connecting the front-end to database data and actions. 

1. Managing user access with Spring Security
 -  restricting unauthorized users from accessing pages other than the login and signup pages. .
 - implementing a custom `AuthenticationProvider` which authorizes user logins by matching their credentials against those stored in the database.  


2. Handling front-end calls with controllers
 -controllers for the application that bind application data and functionality to the front-end. That means using Spring MVC's application model to identify the templates served for different requests and populating the view model with data needed by the template. 
 - The controllers also is responsible for determining what, if any, error messages the application displays to the user. 
 - It's a good idea to keep your controllers in a single package to isolate the controller layer. Usually, we simply call this package `controller`!


3. Making calls to the database with MyBatis mappers
 -designing Java classes to match the data in the database. 
 
### The Front-End
functionality described by the following individual page requirements:

1. Login page
 - Everyone should be allowed access to this page, and users can use this page to login to the application. 
 - Show login errors, like invalid username/password, on this page. 


2. Sign Up page
 - Everyone should be allowed access to this page, and potential users can use this page to sign up for a new account. 
 - Validate that the username supplied does not already exist in the application, and show such signup errors on the page when they arise.
 - Remember to store the user's password securely!


3. Home page
The home page is the center of the application and hosts the three required pieces of functionality. The existing template presents them as three tabs that can be clicked through by the user:


 i. Files
  - The user should be able to upload files and see any files they previously uploaded. 

  - The user should be able to view/download or delete previously-uploaded files.
  - Any errors related to file actions should be displayed. For example, a user should not be able to upload two files with the same name, but they'll never know unless you tell them!


 ii. Notes
  - The user should be able to create notes and see a list of the notes they have previously created.
  - The user should be able to edit or delete previously-created notes.

 iii. Credentials
 - The user should be able to store credentials for specific websites and see a list of the credentials they've previously stored. If you display passwords in this list, make sure they're encrypted!
 - The user should be able to view/edit or delete individual credentials. When the user views the credential, they should be able to see the unencrypted password.

The home page should have a logout button that allows the user to logout of the application and keep their data private.

### Testing

1. tests for user signup, login, and unauthorized access restrictions.
 - test that verifies that an unauthorized user can only access the login and signup pages.
 - test that signs up a new user, logs in, verifies that the home page is accessible, logs out, and verifies that the home page is no longer accessible. 


2. tests for note creation, viewing, editing, and deletion.
 - test that creates a note, and verifies it is displayed.
 - test that edits an existing note and verifies that the changes are displayed.
 - test that deletes a note and verifies that the note is no longer displayed.


3. tests for credential creation, viewing, editing, and deletion.
 - test that creates a set of credentials, verifies that they are displayed, and verifies that the displayed password is encrypted.
 - test that views an existing set of credentials, verifies that the viewable password is unencrypted, edits the credentials, and verifies that the changes are displayed.
 - test that deletes an existing set of credentials and verifies that the credentials are no longer displayed.


### Password Security
Used a hashing function to store a scrambled version instead.  When the user signs up, you only store a hashed version of their password in the database, and on login, you hash the password attempt before comparing it with the hashed password in the database. 


For storing credentials in the main part of the application, we can't hash passwords because it's a one-way operation. The user needs access to the unhashed password, after all! So instead, you should encrypt the passwords.




All of us here at *Simple Cloud storage* e wish you good luck !
