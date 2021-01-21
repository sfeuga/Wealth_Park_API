# Demo REST API in Python

> REQUIRE: pgsql, python 3

1. Setup your .env (see below for a .env example)
2. Run `virtualenv env`
3. Run `pip install -r requirements.txt`
4. Run `createdb test_db` and `createdb flask_api`
5. Run `python manage.py db init` and `python manage.py db migrate`
6. Run `flask run` and start testing the api (see below for curl examples)

## Examples

- .env
    ```bash
    source env/bin/activate
    export FLASK_APP="run.py"
    export SECRET="some-very-long-string-of-random-characters"
    export APP_SETTINGS="development"
    export DATABASE_URL="postgresql://localhost/flask_api"
    ```
- curl
    1. GET all buckets: `curl http://localhost:5000/bucketlists/`
    2. POST a new bucket: `curl -h "Content-Type: application/json" -X POST -d '{"name": "My First Bucket \o/"}' http://localhost:5000/bucketlists/`
    3. UPDATE a bucket: `curl -h "Content-Type: application/json" -X PUT -d '{"name": "Super Duper Bucket"]' http://localhost:5000/bucketlists/1`
    4. DELETE a bucket: `curl -X DELETE http://localhost:5000/bucketlists/1`