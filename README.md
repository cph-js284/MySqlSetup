# MySqlSetup
This is a small script that creates and populates the classicmodels- and coffee.stackexchange- databases

--------------------------------------------------------------------------------------------------------------------------
```
sudo docker run --rm --name mysql01 -p 3306:3306 -e MYSQL_ROOT_PASSWORD=pass1234 -d mysql
sudo docker exec -it mysql01 bash 

apt-get update

apt-get install wget p7zip-full -y
apt-get install unzip

wget https://archive.org/download/stackexchange/coffee.stackexchange.com.7z
wget http://www.mysqltutorial.org/wp-content/uploads/2018/03/mysqlsampledatabase.zip
wget https://raw.githubusercontent.com/cph-js284/Assignment5Database/master/Assignment5scripts/CreateTables.sql

7z e coffee.stackexchange.com.7z 
unzip mysqlsampledatabase.zip

mysql -u root -ppass1234  --local-infile

source ./CreateTables.sql;
source ./mysqlsampledatabase.sql

```
