# schnitzler-zeitungen

a simple django project for interacting with the [Transkribus-API](https://transkribus.eu/wiki/index.php/REST_Interface) to search and read documents hosted and processed by [Transkribus](https://transkribus.eu/Transkribus/)

## install

1. clone the repo `git clone https://github.com/acdh-oeaw/schnitzler-zeitungen.git`
1. create and activate a virtual environment
1. install the dependencies `pip install -r requirements.txt`
1. provide the needed `TRANSKRIBUS` settings via environment variables (see below as well as [acdh-django-transkribus](https://github.com/acdh-oeaw/acdh-django-transkribus))
1. start the developement server `python manage.py runserver`

## TRANSKRIBUS-Settings

Basically your user name and password and the ID of the collection you'd like to expose by the current application.

```python
TRANSKRIBUS = {
    "user": "mytranskribususer@whatever.com",
    "pw": "mytranskribuspassword",
    "col_id": "43497",
    "base_url": "https://transkribus.eu/TrpServer/rest"
}
```


## docker

### building the image

* `docker build -t schnitzlerzeitungen:latest .`
* `docker build -t schnitzlerzeitungen:latest --no-cache .`

### running the image

To run the image you should provide an `.env` file to pass in needed environment variables; see example below:

* `docker run -it -p 8020:8020 --env-file env.secret --name schnitzlerzeitungen schnitzlerzeitungen:latest`