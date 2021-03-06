# SQL Homework

The Glasgow Film Theatre are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'
```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:
```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions.  Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1. Return ALL the data in the 'movies' table.

  SELECT *  FROM movies;

  returns movies table on terminal.

2. Return ONLY the name column from the 'people' table

SELECT name FROM people;

3. Oops! Someone at CodeClan HQ spelled Jean's name wrong! Change it to reflect the proper spelling ('Gene BaMaung' should be 'Jean BaMaung').


UPDATE people SET name = 'Jean BaMaung' WHERE name = 'Gene BaMaung';

SELECT name FROM people;

4. Return ONLY your name from the 'people' table.

SELECT name FROM people WHERE name = 'Chris Murphy';


5. The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.


DELETE FROM movies WHERE title = 'Batman Begins';

SELECT * FROM movies;

6. Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people(name) VALUES ('Alan Russell');

SELECT * FROM people;

7. Jeff Bridges has decided to hijack our movie evening, Remove him from the table of people.

DELETE FROM people WHERE name = 'Jeff Bridges';

SELECT * FROM people;

8. The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this. (The year should be 2018)

INSERT INTO movies(title, year, show_time) VALUES ('Avengers: Infinity War', 2018, '00:00');

SELECT * FROM movies;

9. The cinema would also like to make the Guardian movies a back to back feature. Update the 'Guardians of the Galaxy' show time from 15:30 to 20:00

UPDATE movies SET show_time = '20:00' WHERE title = 'Guardians of the Galaxy';
UPDATE movies SET show_time = '23:00' WHERE title = 'Guardians of the Galaxy 2';

SELECT * FROM movies;

## Extension

1. Research how to delete multiple entries from your table in a single command.

-- DELETE FROM movies WHERE year = 2014;

will delete all films with the same release date. 

If the id is known, you can use select multiple entries using

 -- DELETE FROM movies WHERE id IN(1, 4, 15, 18);
removes 'Iron Man', 'Thor', 'Doctor Strange' and 'Thor: Ragnarok' by id.
