# postgreSQL

## Connect
```bash
  # connect as postgres user to postgres database
$ sudo -u postgres psql
  # connect as specific user to user database
$ sudo -u <user> psql
  # connect as specific user to specific database
$ sudo -u <user> psql -d <database>
```

## Manage User
The user used to connect to the database must be a system registered user too.
```bash
  # create an user with interactive shell (also set password)
$ sudo -u postgres createuser --interactive -P
  # create an user on system
$ sudo adduser <user>
  # drop an user
$ sudo -u postgres dropuser <user>

```
## Create Database
```bash
  # create database with postgres users
$ sudo -u postgres createdb <database>
```

## Prompt commands
- `\q` exit
- `\conninfo` show connection info
- `CREATE DATABASE <database>;` create database <database>
- `CREATE USER <user> WITH PASSWORD '<password>';` create <user> with <password>
- `GRANT ALL PRIVILEGES ON DATABASE <database> TO <user>;` grant privileges to <user> on <database>
