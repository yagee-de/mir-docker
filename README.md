# mir-docker
Docker-Compose Setup for MyCoRe MIR

## Setup
Copy (or link) any `mir.war` to the base directory. It will be deployed later to Tomcat.
Run `docker-compose build` and after that start MIR with `docker-compose up`.

On the first run you are required to setup MIR. Here are the required settings:
* SOLR
  * URL: `http://solr:8983/solr/mir`
* Postgres
  * JDBC-URL: `jdbc:postgresql://postgres/mir`
  * User: `mir`
  * Password: `datastore_pass`
  
You can stop all container at once using `docker-compose down`.

## Data folder

The `data` folder is used to store data from PostgreSQL, SOLR and MIR in their respective subfolders after the first run of `docker-compose up`. 
