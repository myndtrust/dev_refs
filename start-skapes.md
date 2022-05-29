sudo docker run --name some-postgres -p 5432:5432 -e POSTGRES_USER=taxi -e POSTGRES_DB=taxi -e POSTGRES_PASSWORD=taxi -d postgres
sudo docker run --name some-redis -p 6379:6379 -d redis
sudo docker rm -f /some-redis
python3 manage.py runserver 0.0.0.0:8000
sudo docker image prune -a
docker-compose exec taxi-database psql -U postgres
CREATE USER taxi WITH SUPERUSER CREATEDB CREATEROLE PASSWORD 'taxi';
CREATE DATABASE taxi OWNER taxi;
docker-compose exec taxi-server python manage.py collectstatic --noinput
docker-compose exec taxi-server python manage.py migrate
sudo  docker-compose exec taxi-client ng test
docker-compose exec taxi-server pytest
source ~/.bashrc
sudo  docker-compose exec taxi-nginx nginx -s reload
sudo pip3 install --upgrade pip
sudo python3 -m venv .venv
sudo fuser -k 4200/tcp
Install fuser: sudo apt-get install psmisc
dap django-admin user:eric pw:3959880
docker-compose exec db psql -U postgres
