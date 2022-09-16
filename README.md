# proj-5 IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS)
To perform the task, mysql ser and mysql client need to be created, meaning we creating 2 servers for this purpose. one for sql server and another for sql client.
# Install Mysql server on one 
this can be done with the command : sudo apt install mysql-server -y
also run : sudo systemctl enable mysql   to enable it 
# Install mysql -client on the other one
This can be done with the command : sudo apt install mysql-client -y
# Open the tcp port 3300 for MYSQL on aws console
by defauly 3306 is the port for mysql, so the port needs to be opend on the sql server. and for security sake only the ipp address of the clienet should be allowed access to the port and its done as shwon below
![Screen Shot 2022-09-16 at 7 36 19 PM](https://user-images.githubusercontent.com/112595648/190708473-a24e8880-91db-4bbe-a0f2-c4dc586fe7a7.png)

