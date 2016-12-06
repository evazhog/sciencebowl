# sciencebowl

A question bank application for Science Bowl created by Albany High School students and alums.



## Setting up your enviornment

Make sure you have Python [installed properly](http://install.python-guide.org) and [Postgres](https://devcenter.heroku.com/articles/heroku-postgresql#local-setup)

Then:
```sh
$ git clone https://github.com/andimus/sciencebowl
$ cd sciencebowl
$ pip install -r requirements.txt
$ createdb sciencebowl
$ python manage.py migrate
$ python manage.py collectstatic
```

If you want to be able to deploy to heroku, you'll need to install the [Heroku Toolbelt](https://toolbelt.heroku.com/), get access from an admin.

Then:
```sh
$ heroku git:remote -a sciencebowl
```

## Running Locally
Once you've set things up, you can run locally:

```sh
$ heroku local
```

Your app should now be running on [localhost:5000](http://localhost:5000/).

## Deploying to Heroku

```
$ git push heroku master
```
The app is now live at: [https://sciencebowl.herokuapp.com](https://sciencebowl.herokuapp.com).


## Admin Functionality
Python has some nice built in admin functionality we can use to edit the DB.

Create a superuser
```
$ python manage.py createsuperuser
```

You should be able to use the admin page at: [http://localhost:5000/admin](http://localhost:5000/admin)

Note: don't forget to add new tables to `admin.py` to be able to edit them.

## Changing Schema
After a schema change, you'll need to migrate your database locally to work. To do this run:
```
$ python manage.py makemigrations
$ python manage.py migrate
```

Also, make sure to include your migration files (the `hello/migrations/####_auto...py` files generated by the makemigrations script) when you check in. After you deploy, run the migrate function on heroku:
```
$ heroku run python manage.py migrate
```

## Documentation

For more information about using Python on Heroku, see these Dev Center articles:

- [Python on Heroku](https://devcenter.heroku.com/categories/python)
