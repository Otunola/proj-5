# proj-5 IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS)
To perform the task, mysql ser and mysql client need to be created, meaning we creating 2 servers for this purpose. one for sql server and another for sql client.
# Install Mysql server on one 
this can be done with the command : sudo apt install mysql-server -y
also run : sudo systemctl enable mysql   to enable it 
# Install mysql -client on the other one
This can be done with the command : sudo apt install mysql-client -y
# Open the tcp port 3306 for MYSQL on aws console
by defauly 3306 is the port for mysql, so the port needs to be opend on the sql server. and for security sake only the ipp address of the clienet should be allowed access to the port and its done as shwon below
![Screen Shot 2022-09-16 at 7 36 19 PM](https://user-images.githubusercontent.com/112595648/190708473-a24e8880-91db-4bbe-a0f2-c4dc586fe7a7.png)

NOw both installation has beeen done. but as of now, theres no data on the mysql database, meaning the server is empty. so there has to be something in it for the client to request.
# mysql secure installion
run the command : sudo mysql_secure_installation
then follow the promts
# Next we create users into mysql data
this can be achieved with the command below
 : CREATE USER 'remote_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
 which means that remote user with password "password" and the % represent any ip address
 # we create Database
 next we create database with the commad
 : CREATE DATABASE test_db;
 # next thing is to grant priviledges
 This can be achieved with the command below
 : GRANT ALL ON test_db.* TO 'remote_user'@'%' WITH GRANT OPTION;
 the command above grants all priviledges on the database to the 'remote user'
# next we Flush the privileges with the command below
: FLUSH PRIVILEGES;
now our database is created
# configure the MYSQL to allow connection from remote hosts
run the command: sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf
then replace the bind ip address from Replace ‘127.0.0.1’ to ‘0.0.0.0 as shown below this is to allow coonection to the database from any ip source
<img width="575" alt="Screen Shot 2022-09-17 at 1 48 46 AM" src="https://user-images.githubusercontent.com/112595648/190833976-33bb6e50-f9ae-41a1-a1a2-75529422772a.png">

# REstart the MYSQL SERVICE
this can be done with the command
: sudo systemctl restart mysql

# Connect to MYSQL Server from Client
next is to connect to our database server from the client with the command : sudo mysql -u remote_user -h 172.31.22.172 -p 
enter the password when prompted and if we IN... as shown below
<img width="559" alt="Screen Shot 2022-09-17 at 2 02 11 AM" src="https://user-images.githubusercontent.com/112595648/190834420-f5f5d86b-dba2-4533-b83a-5a19435fb40a.png">
Performing sql queries like : Show databases;
<img width="568" alt="Screen Shot 2022-09-17 at 2 04 03 AM" src="https://user-images.githubusercontent.com/112595648/190834516-6c015330-b347-4fe0-88c2-29134f6a83ec.png">


