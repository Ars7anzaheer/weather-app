Download Weather Data from
https://tinyurl.com/y4dtdayb


wget -O weather.csv https://tinyurl.com/y4dtdayb

docker cp pokemon.csv cassandra-test:/home/pokemon.csv

CREATE KEYSPACE weather WITH REPLICATION = {'class' : 'SimpleStrategy', 'replication_factor' : 2};

DESCRIBE KEYSPACES

CREATE TABLE weather.city(id int PRIMARY KEY, name text, original text, temperature float, description text, icon text);

DESCRIBE TABLES

COPY weather.city (id,name,original,temperature,description,icon) FROM 'weather.csv' WITH DELIMITER=',' AND HEADER=TRUE;

SELECT * FROM weather.city;


INSERT INTO weather.city(ID,Name,Original,Temperature,Description,Icon)
VALUES (7,Vancouver,Vancouver,14.9,clear sky, 02n);

INSERT INTO weather.city(ID,Name,Original,Temperature,Description,Icon)
   ... VALUES(7,'Vancouver','Vancouver',14.9,'clear sky','02n');


kubectl run weather-app --image=gcr.io/${PROJECT_ID}/weather-app:v1 --port 8080


kubectl expose deployment weather-app --type=LoadBalancer --port 80 --target-port 8080

kubectl get services

kubectl cp weather.csv cassandra-npz55:/weather.csv

gcloud container clusters create cassandra --num-nodes=3 --machine-type "n1-standard-2"


docker images

docker rmi 

docker build -t gcr.io/${PROJECT_ID}/weather-app:v1 .

docker push gcr.io/${PROJECT_ID}/weather-app:v1

kubectl run weather-app --image=gcr.io/${PROJECT_ID}/weather-app:v1 --port 8080

kubectl expose deployment weather-app --type=LoadBalancer --port 80 --target-port 8080

kubectl get services