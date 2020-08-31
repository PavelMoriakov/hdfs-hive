# Docker HDFS-HIVE
A development big data infrastructure with docker-compose.

## Local machine requirements
8 GB Ram

## Prepare environment

1. Start Docker
2. Git clone from this repository with following command: git clone <repository_url>
3. Open terminal and print `docker compose up`
4. Check that containers upped `docker ps --format '{{.Names}}'` . 
<br>	Expected result:
<br>hive-server
<br>hive-metastore
<br>hive-metastore-postgresql
<br>datanode
<br>hue
<br>database
<br>namenode 

## Example
* Connect to hive-server Docker bash - `docker exec -it hive-server /bin/bash` 
* Launch Hive - `hive`
* Create Table - `CREATE TABLE students (name VARCHAR(64), age INT, gpa DECIMAL(3, 2));`  
<br> Expected output: 
<br> OK
<br>Time taken: 1.359 seconds
*  Insert test data to created table - `INSERT INTO TABLE students VALUES ('fred flintstone', 35, 1.28), ('barney rubble', 32, 2.32);`
*  Check data - `SELECT * FROM default.students;`

## URLS
HUE UI - http://localhost:8888
<br>HDFS NameNode UI - http://localhost:50070


<br> In this repository, we used an initial [Git Project](https://github.com/m-semnani/bd-infra) 
<br> You can find more explanation in [this article](https://itnext.io/creating-a-big-data-development-platform-using-docker-compose-892f7f4da738).
