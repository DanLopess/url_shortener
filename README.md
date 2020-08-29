<h1 align="center">URL Shortener</h1>


# About

<br/>

**URL Shortnenet** allows people to shorten a long url with a customized one.

# Technologies

* Require download
  * [Postgres >= 10](https://www.postgresql.org/)
  * [Java 11](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html)
  * [Maven](https://maven.apache.org/download.cgi)
  * [Node 12.14](https://nodejs.org/en/) ([Node Version Manager](https://github.com/nvm-sh/nvm) recommended)
  * [Docker](https://www.docker.com/)
* No download required
  * [Spring-boot](https://spring.io/)
  * [Vue.js](https://vuejs.org/)

# Installation

* **Install**
```
sudo apt update && sudo apt upgrade
sudo apt install openjdk-11-jdk postgresql
```
* **Start db, change to postgres user and create DB**
```
sudo service postgresql start
sudo su -l postgres
dropdb tutordb
createdb tutordb
```
* **Create user to access db and load dump**
```
psql tutordb
CREATE USER your-username WITH SUPERUSER LOGIN PASSWORD 'yourpassword';
\q
exit
psql tutordb < dump.sql
```
* **Go to [API Service Agreement](https://fenix.tecnico.ulisboa.pt/personal/external-applications/api-service-agreement) and then to [Applications](https://fenix.tecnico.ulisboa.pt/personal/external-applications/#/applications)  and create an application that redirects to http://localhost:8081/login and accessess curricular and information**
* **Rename `backend/src/main/resources/application-dev.properties.example` to `application-dev.properties` and fill its fields**
* **Run server**
```
cd backend
mvn clean spring-boot:run
```
* **See documentation on http://localhost:8080/swagger-ui.html**
* **Rename `frontend/example.env` to `.env` and fill its fields**
* **Run frontend**
```
cd frontend
npm i
npm start
```
* **Access http://localhost:8081**

# License

This project is licensed under the GNU License
