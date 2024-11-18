# forgotPassword
forgot Password React
Steps to Setup a React App:
1. npx create-react-app frontend
   1. cd frontend
   2. Install the necessary packages for this project.("npm install --save react-router-dom @mui/material @emotion/react @emotion/styled @mui/icons-material axios react-toastify"),
   3. Create a .env file to hide your secret key(s) or variable(s).("REACT_APP_BACKEND_URL=http://localhost:4000"),
   4. Create the required files as seen in the folder structure and add the following codes.("App.js,Login.js,ForgotPassword.js,ResetPassword.js "),
   5. To start the frontend run the following command:("npm start")
2.Create a npm project inside a new folder `backend` folder as follows: ("1. mkdir backend, 2. cd backend")
  1.npm init -y
  2.Initialize the Node application using the following command:("npm init -y")
  3.Install necessary packages.("npm install --save express bcrypt cors crypto dotenv express mysql2 nodemailer ")
  4.Create a .env file in your backend's root folder and put your email id and password inside it to hide them.
PORT=4000
DATABASE_HOST=localhost
DATABSE_USER=<your_db_username>
DATABSE_PASSWORD=<your_db_password>
DATABASE_PORT=3306
DATABASE_NAME=users
DATABASE_CONNECTION_LIMIT=20
EMAIL_ID=<your_email>
EMAIL_PASSWORD=<your_email_app_password>
FORGOT_PASSWORD_TOKEN_SECRET=somesecret
FRONTEND_URL=http://localhost:3000
NO_OF_SALT_ROUNDS=10
5. Create the files `server.js`, `routes.js`, `email.js` and `db.js` which will run our Express Server and serve the React App with responses to routes hit.
6. Assuming that we are using MySQL database which contains `users` database with two tables `details` and `reset_tokens` whose schema is as follows:
   CREATE TABLE details
(
    id int auto_increment primary key,
    email varchar(255) not null unique,
    name varchar(255) not null,
    password varchar(255) not null
);

create table reset_tokens
(
    token varchar(255) not null,
    created_at varchar(255) not null, 
    expires_at varchar(255) not null,
    user_id int not null,
    PRIMARY KEY(user_id, token)
);
7.To start the backend server run the following command:("node server.js")
      
