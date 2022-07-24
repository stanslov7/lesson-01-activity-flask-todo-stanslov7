
# Lesson 01 - Practice Activity: Web Frameworks and Flask

## Instructions:

Please submit your copy of the flask-todo project from this week's lesson. We will be grading this assignment based purely on the functional requirements specified in the lesson.

## Submitting Your Work
When you are done:

Zip up your project directory.
Submit the zip archive as a file.


# Deploying to Heroku:

--> Would have installed and added to virtual env and to requirements.txt file 
 "gunicorn" and "psycopg2" as well as,
--> created a Procfile for Heroku with contents: "web: gunicorn main:app"
--> would set secret var using:
$ heroku config:set SECRET_KEY=KjJPe35tQKY2YLRzm7vhm3aJdqqh8YHR

## Commands to be used:

$ git init                # Only necessary if this is not already a git repository
$ heroku create
$ heroku config:set SECRET_KEY=KjJPe35tQKY2YLRzm7vhm3aJdqqh8YHR
$ pip install gunicorn psycopg2
$ pip freeze > requirements.txt
$ echo "web: gunicorn main:app" > Procfile
$ git add .; git commit -a -m "Initial commit"  # Only necessary because this is a new git repo.
$ git push heroku master  # If you have any changes or files to add, commit them before you push. 
$ heroku addons:create heroku-postgresql:hobby-dev
$ heroku run python setup.py
$ heroku open



## And here's the code I used to set the secret key using an environment variable:

app.secret_key = os.environ.get('SECRET_KEY').encode()


**Note on this:
Can use the follwing to add Secret Key locally in non-bytes form also:
$ export SECRET_KEY=KjJPe35tQKY2YLRzm7vhm3aJdqqh8YHR

(in Heroku wouldve been done using command:
 $ heroku config:set SECRET_KEY=KjJPe35tQKY2YLRzm7vhm3aJdqqh8YHR
, as seen in above steps for this.)
