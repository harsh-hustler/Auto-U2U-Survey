# Auto-U2U-Survey

Auto-U2U-Survey is a Web app basically created to provide automation.
This app is made in **flask** to do survey of an attribute(in this case height) of people and sending the average of the results automatically to their email i'd.

  - The result is calculated amongst the previously registered people
  - Database used is **PostgreSQL** as it is open source database
  - Responsive web app and is customizable further

# Features

  - Provides a better UI with pop ups when user hover over the area for entering details to introduce legitimacy
  - Restricted the same user to enter again.
  - Used the concept of **SMTP** for sending the result automatically to the user mail i'd



## There is only one branch in this repository i.e `master`  branch

### For `master` branch
* For Flask 1+
* Works with Python 3.9+
* `Procfile` for deploying to heroku

```
The template structure is as follows:
├── app.py          <- contains all the apps for the project. New apps should be added to this particular package only.
├── Procfile        <- Procfile for Heroku.
├── README.md
├── requirements.txt
├── runtime.txt
├── send_email.py   <- for sending email automatically to the registered user.
├── static          <- static files that are to be carried out throughout the project.
│   └── main.css
└── templates       <- templates to be carried out throughout the project.
    ├── index.html
    └── success.html
```

# How to Install

## To run on your local server
```
$ mkdir my_project
  --template=https://github.com/harsh-hustler/Auto-U2U-Survey/archive/master.zip \
  --name=Procfile \
  --extension=py \
$ pip install flask
$ pip install psycopg2
$ pip install Flask-SQLAlchemy
$ python
  >>from app import db
  >>db.create_all()
$ python app.py
```

It is considered good practice to run the above commands in a new and separate virtual environment. Read more about virtual environments [here](https://realpython.com/python-virtual-environments-a-primer/).Don't forget to enable Allow less secure app in your hosted mail i'd

# Deployment

## To run on cloud i.e.Remote Server
The project template contains the `Procfile` for deploying it to Heroku. Within your project directory, run the following commands in the sequence they appear.

```
$ heroku create
$ heroku addons:add heroku-postgresql:hobby-dev
$ git push heroku master
$ pip install gunicorn
$ pip freeze > requirements.txt
$ heroku run python
  >>from app import db
  >>db.create_all()
$ heroku open
```
Also, do not forget to set the project environment variables.

You should have a Heroku account (if not, create one [here](https://www.heroku.com/)), and Heroku CLI installed for the commands to work (if not, installation instructions can be found [here](https://devcenter.heroku.com/articles/heroku-cli)).


