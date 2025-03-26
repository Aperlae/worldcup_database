# Build a Worldcup Database
Building a db with PostgreSQL, creating bash scripts to insert data and query db | freeCodeCamp required project

## Instructions
For this project, we are asked to log in to PostgreSQL with psql to create our database by entering the command `psql --username=freecodecamp --dbname=postgres` in the terminal. 

We're advised to save the database by making a dump of it from a bash terminal with `pg_dump -cC --inserts -U freecodecamp universe > universe.sql`. The file will be located within the `project` folder. The database can be rebuilt by entering `psql -U postgres < universe.sql` in a terminal where the `.sql` file is. 

### Part 1: Create the database
Create the database structure according to the user stories below.

### Part 2: Insert the data
Complete the `insert_data.sh` script to correctly insert all the data form `games.csv` into the database. The file is started for you. Do not modify any of the code you start with. Using the PSQL variable defined, you can make database queries like this:
`$($PSQL "<query_here>")`. The tests have a 20 second limit, so try to make your script efficient. The less you have to query the database, the faster it will be. You can empty the rows in the tables of your database with `TRUNCATE TABLE games, teams;`.

### Part 3: Query the database
Complete the empty `echo` commands in the `queries.sh` file to produce output that matches the `expected_output.txt` file. The file has some starter code, and the first query is completed for you. Use the `PSQL` variable defined to complete rest of the queries. 
Note that you need to have your database filled with the correct data from the script to get the correct results from your queries. Hint: Test your queries in the psql prompt first and then add them to the script file.

## Tasks

- You should create a database named `worldcup`.
- You should connect to your worldcup database and then create `teams` and `games` tables.
- Your `teams` table should have a `team_id` column that is a type of `SERIAL` and is the primary key, and a `name` column that has to be `UNIQUE`.
- Your `games` table should have a `game_id` column that is a type of `SERIAL` and is the primary key, a `year` column of type `INT`, and a `round` column of type `VARCHAR`.
- Your `games` table should have `winner_goals` and `opponent_goals` columns that are type `INT`.
- All of your columns should have the `NOT NULL` constraint.
- Your two script (.sh) files should have executable permissions. Other tests involving these two files will fail until permissions are correct. When these permissions are enabled, the tests will take significantly longer to run.
- When you run your `insert_data.sh` script, it should add each unique team to the `teams` table. There should be 24 rows.
- When you run your `insert_data.sh` script, it should insert a row for each line in the `games.csv` file (other than the top line of the file). There should be 32 rows. Each row should have every column filled in with the appropriate info. Make sure to add the correct ID's from the teams table (you cannot hard-code the values)
- You should correctly complete the queries in the `queries.sh` file. Fill in each empty `echo` command to get the output of what is suggested with the command above it. Only user a single line like the first query. The output should match what is in the `expected_output.txt` file exactly, take note of the number of decimal places in some of the query results. 

### Testing
All tests passed =)


