web: gunicorn hellodjangorest.wsgi
worker: celery worker -A hellodjangorest.celery --loglevel=info --logfile=worker.log -B
