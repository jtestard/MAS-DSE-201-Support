# MAS-DSE-201-Support
This repository is made to help students of the MAS DSE 201 course offered in Winter 2015 at UCSD. It contains documentation on software required for the course.


## 1. Install PostgreSQL

### Mac OS X

1. The recommended way to install PostgreSQL in Mac OS X is using [Postgres.app](http://postgresapp.com/). Follow the instructions on the website to install the software. This will install PostgreSQL version 9.4.
2. Once you installed the application, launch it and you should see a small elephant on your toolbar (see screenshot). ![alt tag](./images/postgres_app.jpg))
3. Click on "Open psql" and you are presented with an interactive shell you can use for SQL commands.

##### PgAdmin installation

The above installation only provides a command line interface for PostgreSQL. For those who prefer a Graphical User Interface, follow these steps to install PgAdmin. Note that you still need to complete the steps above to install PostgreSQL itself.

1. Download PgAdmin [here](https://ftp.postgresql.org/pub/pgadmin3/release/v1.20.0/osx/pgadmin3-1.20.0.dmg).
2. Open PgAdmin in click on the Connect button in the top right corner (looks like a plug).
3. Configure PgAdmin as follows (replacing `julestestard` by your MacOS username) then click OK (don't put a password) : ![alt tag](./images/pgadmin-config.png)
4. Back to the main page, you should see a `<your_username>` server with a `<your_username>` database. If the server is shown with a cross onto it, just double click it (this should start the connection). ![alt tag](./images/pgadmin-menu.png)
5. You're good to go! I suggest following online guides on PgAdmin for further details about the GUI.

### Linux (Ubuntu)

1. The first step is to install postgres with the following PostgreSQL as follows : run `sudo apt-get install postgresql` on the terminal. Verify that the installed version of PostgreSQL. The version number shouldn't matter as long as it's fairly recent (version 9.0+).
2. Run `sudo -u postgres createuser -s <username>` on the terminal. By default, the PostgreSQL installation will install a user called `postgres` which will have the administrator role (highest level of privilege). In our case, it is OK to have our own user be a super user as well. This command creates a new user (which bears our own name) and gives it administrator powers.
3. Run `createdb <username>` on the terminal. This will create a database whose name is the same as our own name.
4. Run `psql` on the terminal and you will have a client session to your database. Note that `psql` is a shorthand for `psql -U <username> -d <username>`, which means "create a client connection to the database \<username> as user \<username>".

##### PgAdmin Installation

The above installation only provides a command line interface for PostgreSQL in Linux. For those who prefer a Graphical User Interface, follow these steps to install PgAdmin. Note that you still need to complete the steps above to install PostgreSQL itself.

1. The first step is to install PgAdmin. For this, just run `sudo apt-get install pgadmin3` on the terminal.
2. Follow steps 2-5 found on the MacOS PgAdmin install.


### Windows
1. Download [Postgresql 9.4](http://www.enterprisedb.com/products-services-training/pgdownload#windows) 
2. Click Next
 ![alt tag](./images/windows/1.jpg))
3. Click Next
![alt tag](./images/windows/2.jpg)
4. Provide password (e.g. postgres)
![alt tag](./images/windows/3.jpg)
5. Click Next
![alt tag](./images/windows/4.jpg)
6. Click Next
![alt tag](./images/windows/5.jpg)
7. Click Next
![alt tag](./images/windows/6.jpg)
8. Click Finish
![alt tag](./images/windows/8.jpg)
9. Launch psql and put in password for user postgres (defaults for other fields is ok for now)
![alt tag](./images/windows/9.jpg)
10. Launch pgAdmin
![alt tag](./images/windows/10.jpg)
11. Double click on PostgresSQL 9.4 and put in the password for user postgres
![alt tag](./images/windows/11.jpg)


## 2. Setup a simple database

At this point we assume you have logged into PostgreSQL through `psql` (see section 1 for PostgreSQL installation for your system).

## 2.1 Loading data

Please download and unzip the [sql.zip](sql.zip) at a convenient location on your system. To load data from sql within `psql`, do the following (in Linux or MacOS):

	psql> \i <path_to_location>/sql/create_tables_enrollment.sql 
	psql> \i <path_to_location>/sql/create_tables_movie.sql
	
Do the following (in Windows):
	
	psql> \i <path_to_location>\sql\create_tables_enrollment.sql
	psql> \i <path_to_location>\sql\create_tables_movie.sql


## 2.2 Running Queries

To run a few example queries, do the following (in Linux or MacOS):

	psql> \i <path_to_location>/sql/run_queries_enrollment.sql 
	psql> \i <path_to_location>/sql/run_queries_movie.sql

Do the following (in Windows):
	
	psql> \i <path_to_location>\sql\run_queries_enrollment.sql 
	psql> \i <path_to_location>\sql\run_queries_movie.sql
