# GeoDjango Tutorial kick-off

Helper repo for trying out [GeoDjango Tutorial](https://docs.djangoproject.com/en/dev/ref/contrib/gis/tutorial/).

Works with
- Python 3.9.7
- PostGIS 3.1.4 on top of PostgreSQL 14
- gdal


Run `docker-compose exec app bash` to exec into the app container.
`WorldBorder` model is ready, but you need to run `python3 geodjango/manage.py migrate` to apply migrations.
