# Cinema API
- Api service for cinema management written on DRF

## Feauters:
- JWT authenticated
- Admin panel /admin/
- Documentation is located via /api/doc/swagger/
- Managing orders and tickets
- Media files on movie image (stored in docker )
- Creating movies with actors , genres 
- Filtering movies and movie sessions
- Docker app starts only when db is available ( custom command via management/commands )

## Installing using GitHub:
-Install Postgres and create DB

```shell
git clone https://github.com/bythewaters/cinema-api.git
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
open .env.sample and change enviroment variables on yours !Rename file from .env.sample to .env
python manage.py migrate
python manage.py runserver
```
- Use the following command to load prepared data from fixture(if you need):
  - `python manage.py loaddata cinema_service_db_data.json`.

## Run with Docker:
- Docker should be installed
```
- docker-compose build
- docker-compose up
```
- Use the following command to load prepared data from fixture in docker(if you need):
  - `docker ps`(copy name or id docker container)
  - `docker exec -t -i <docker_name_or_id> sh`
  - `python manage.py loaddata cinema_service_db_data.json`.

## Getting access:
- Create user via /api/user/register/
- Get user token via /api/user/token/
- Authorize with it on /api/doc/swagger/ OR 
- Install ModHeader extension and create Request header with value ```Bearer <Your access token>```
