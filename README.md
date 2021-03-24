# Assignment App | Capstone CS50W

</br>

# Overview

This project contains a Django Rest API with a React frontend. I call this the Assignment App. Users will be able to signup and login to their account. Teachers will be able to create quizes. Students will be able to answer those quizes and view their results. When the teacher creates the quizes, they will be able to assign choices along with the correct answer. After the student answers the quizes, they can check their results by going to their profile page by clicking on the profile tab.

</br>

# Justification

I consider that this project meets all the expectations raised in the assignment of the CS50W final project, as it is a web platform that implements most of the concepts and techniques taught in the course.

The whole application is based on the Django framework, which allowed managing user authentication, database models, http requests, static files and the page rendering.

On the other hand, user interface was designed with React JS. The web application is mobile responsive. I have included bootstrap library to make my react components / front end mobile responsive.

The difference between this web application and previous projects is that this application makes use and manages the data to check the assignments / quizes, create the quizes / assignments, check the results of the assignments instantly. With the potential to include more features in the future with respect to other services such as submission date, due date and, more.

- [x] Your web application must be sufficiently distinct from the other projects in this course (and, in addition, may not be based on the old CS50W Pizza project), and more complex than those.
- [x] Your web application must utilize Django (including at least one model) on the back-end and JavaScript on the front-end.
- [x] Your web application must be mobile-responsive.

</br>

# Structure

The web platform is structured as follows

- **src:** This folder contains the front end part (React) that displays the landing page that allows the users to interact with the application.
- **home:** The home folder is the main Django app
- **api:** This folder contains the api funtions and models which can be called from the front end. This folder contains the funtions and models for assignments, graded assignments, questions, choices. This folder also have serializers to validate the incoming data (quizes)
- **users:** This folder app handles the models and funtions relating to users (students and trachers).

</br>

# File Contents

## Front End:

- `./src/components/`:

  - `Choices.js` - Choice radio button to handle the answer choices.
  - `Result.js` - This handles the result of the quizes.

- `./src/containers/`:

  - `AssignmentCreate.js` - Handles the creation of assignments / quizes.
  - `AssignmentDetails.js` - File for submitting the assignments along with the user info and answer choices.
  - `AssignmentList.js` - This displays the list of assignments.
  - `Layout.js` - This file is the main layout of the UI of the web application.
  - `Login.js` - This file handles the login.
  - `Profile.js` - This file renders the profile page.
  - `QuestionForm.js` - This file handles the form where the questions are created.
  - `Questions.js` - This file handles the questions and lets you navigate and submit.
  - `Signup.js` - This file handles the signing up / creating the user accounts.

- `./src/store/`:

  - `./src/store/actions`: This folder contains the actions, which are objects that contains the paylod of information. they are the only source of information for the redux store to be updated. Axios is also used which helps to fetch ans save the data.
  - `./src/store/reducers`: This folder contains reducers, funtions which receives the new value to update the state in store based action type. Basically the manage the state in the application.

- `./src/`:
  - `App.js` - This file contains the subcomponents of the app.
  - `App.test.js` - it is a simple text file to check if the components renders.
  - `index.js` - This file renders the app.js, which contains the other components to render.
  - `routes.js` - This file contains some collection of navigational components. it calls the high order components (hoc)

</br>

## Back End:

### Models in the app

There are 6 models for the web application's database.

1. `User` - A fully featured User model with admin-compliant permissions.
2. `Student` - Holds the information of students.
3. `Assignment` - Holds the information of the assignments.
4. `GradedAssignment` - Holds the information about the submitted assignments.
5. `Choice` - Holds the informations about the choices for the assignment / quiz.
6. `Question` - Holds the information about the questions in the assignment.

### Views and serializers py files:

'views.py' contains the funtions for the web application. These view functions sends and receives http request and response. They also combine with serializers to deal with model instances and querysets.

### Manage.py file:

This file is used as a command-line utility and for deploying, debugging, or running the web application.This file contains code for runserver, makemigrations or migrations, etc. that we use in the shell. (Not changing anything here)

### _init_.py files:

This file is empty and remains that way. they are present only to tell that this particular directory is a package. (No changes to this file either)

### settings folder:

This file is present for adding all thr applications and the middleware application present. This also has informations about templates and databases. This is present in the main file of the Django web application.

### urls.py files:

This file handles all the URLs of our Django web application. This file contains the lists of all the endpoints that we will have for our web application. Also, this files is like a link to the views in the app with the host web URL.

### wsgi folder:

This file mainly concerns with the WSGI server and is used for deploying the web application on to the servers similar to apache, etc. (No changes to this file as well)

### admin.py files:

Similar to the name of the file, this file is used for registering the models into the django administration. The models that are present have a superuser/admin who can control the information that is being stored. (they are pre-built)

### apps.py files:

This file deals with the application configuration of the apps. The default configuration is sufficient enough in most of the cases.

### models.py files:

This file contains the models of our web application (classes). They are the blueprints of the database we are using and hence contain the information regarding attributes and the fields, etc of the database.

### views.py files:

This files are the crucial ones, it contains all the views. This file can be considered as the file that interacts with the client. This web application uses views with the concept of serializers in the Django Rest_Framework.

### test.py files:

This file containts the code that contains different test cases for the application. It is used to test the working of the application. (did not implement tests in this web application)

</br>

# Installation & how to run the application

Run the application in their default ports (Django: 8000 & React: 3000). Run the backend first and then the front end.

## Backend

```json
virtualenv env
pip install -r requirements.txt
python manage.py runserver
```

## Frontend

```json
npm i
npm start
```

## For deploying

```json
npm run build
```

</br>

# Avinash-Murugappan
