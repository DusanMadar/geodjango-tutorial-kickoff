# GeoDjango Tutorial kick-off

Helper repo for trying out [GeoDjango Tutorial](https://docs.djangoproject.com/en/dev/ref/contrib/gis/tutorial/).

Works with
- Python 3.9.7
- PostGIS 3.1.4 on top of PostgreSQL 14
- gdal


## How to run the Django server

Tested with

- Docker 24.0.1
- Docker Compose version v2.11.0

The included [docker-compose.yaml](docker-compose.yaml) file just starts a
container, but does not run the Django server by default.

Run `docker compose exec app bash` to exec into the app container.
`WorldBorder` model is ready, but you need to run
`python3 geodjango/manage.py migrate` to apply migrations.

Then run `python geodjango/manage.py runserver 0.0.0.0:8000` to start
the Django app on the exposed port `8000`.

Alternatively, replace `command: tail -F /dev/null` with
`command: python geodjango/manage.py runserver 0.0.0.0:8000` in
[docker-compose.yaml](docker-compose.yaml#L21) so that the app starts along
with the `db` service.
