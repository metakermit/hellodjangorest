# Development

Setup your hellodjangorest development environment:

```shell
./scripts/install.sh
```

And start developing

```shell
./scripts/start.sh
```

## Deployment to Heroku

You can quickly deploy hellodjangorest to Heroku:

```shell
heroku login
heroku create hellodjangorest
heroku git:remote -a hellodjangorest
heroku addons:create heroku-postgresql:hobby-dev # for the DB
heroku addons:create heroku-redis:hobby-dev # for Celery
./scripts/deploy.sh
heroku run python manage.py migrate
```

Once this initial setup is working, you normally deploy by issuing:

```shell
./scripts/deploy.sh
```

## Frontend details


## Upgrading the scaffolding

The scaffolding for this Django project was built using
[generator-django-rest][]. If you think of an improvement for your
Django project and that could benefit a wider range of projects
(e.g. auth, user management, caching improvements etc.), please consider
[contributing back][generator-django-rest].

To upgrade your project with the latest version of generator-django-rest
install `node` and get these npm package:

```shell
npm install -g yo generator-django-rest
npm update -g yo generator-django-rest # maybe not necessary?
```

If you use `yarn` instead do:

```shell
yarn global add yo generator-django-rest
yarn global upgrade yo generator-django-rest
```

Then from within the root of your project (the path containing this file) run:

```shell
yo django-rest hellodjangorest
```

And resolve any conflicts using the interactive queries.


## Docker

To run `python manage.py` commands use `docker-compose run cli` instead:

```shell
docker-compose run cli migrate
docker-compose run cli createsuperuser
```

And to run the entire application with necessary services:

```shell
docker-compose up
```

If you want to run Django with runserver for better debug output,
update the *docker-compose.yml* file.


[generator-django-rest]: https://github.com/metakermit/generator-django-rest
