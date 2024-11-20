#  0x03-user_authentication_service

## Tasks
0. User model
mandatory
In this task you will create a SQLAlchemy model named User for a database table named users (by using the mapping declaration of SQLAlchemy).

The model will have the following attributes:

id, the integer primary key
email, a non-nullable string
hashed_password, a non-nullable string
session_id, a nullable string
reset_token, a nullable string

1. create user
In this task, you will complete the DB class provided below to implement the add_user method.

2. Find user
In this task you will implement the DB.find_user_by method. This method takes in arbitrary keyword arguments and returns the first row found in the users table as filtered by the method’s input arguments. No validation of input arguments required at this point.

Make sure that SQLAlchemy’s NoResultFound and InvalidRequestError are raised when no results are found, or when wrong query arguments are passed, respectively.

Warning:

NoResultFound has been moved from sqlalchemy.orm.exc to sqlalchemy.exc between the version 1.3.x and 1.4.x of SQLAchemy - please make sure you are importing it from sqlalchemy.orm.exc

3. update user
In this task, you will implement the DB.update_user method that takes as argument a required user_id integer and arbitrary keyword arguments, and returns None.

The method will use find_user_by to locate the user to update, then will update the user’s attributes as passed in the method’s arguments then commit changes to the database.

If an argument that does not correspond to a user attribute is passed, raise a ValueError.

4. Hash password
In this task you will define a _hash_password method that takes in a password string arguments and returns bytes.

The returned bytes is a salted hash of the input password, hashed with bcrypt.hashpw.

5. Register user
In this task, you will implement the Auth.register_user in the Auth class provided below:

6. Basic Flask app
In this task, you will set up a basic Flask app.

Create a Flask app that has a single GET route ("/") and use flask.jsonify to return a JSON payload of the form:

7. Register user
In this task, you will implement the end-point to register a user. Define a users function that implements the POST /users route.

Import the Auth object and instantiate it at the root of the module as such:

...