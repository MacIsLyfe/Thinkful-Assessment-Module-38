Creating relations: Relating tables through keys
Instructions
In this practice problem, you will create three tables with data associations between them.

You will write your queries in the relevant SQL files to get the tests to pass.

Only one query should be written per file. Carefully check your syntax if you encounter errors. In particular, the names of the tables are very important because the automated tests depend on them to work properly.

Set up a database (optional)
This setup is optional, but if you would like a way to debug your queries, you can set up a database and connect it to DBeaver from your local machine. You can then execute any queries you write for this assessment and verify their outputs in DBeaver on your local machine.

Set up a new instance called thinkful_music_events on ElephantSQL. The instructions for creating a new database instance can be found in the Creating and deleting databases lesson of the previous module.
Connect DBeaver to your database instance and rename the database connection to thinkful_music_events for easy reference. The instructions for connecting DBeaver to your instance can be found in the Installing DBeaver lesson of the previous module.
Now, you can execute your queries in DBeaver.
After creating all the tables described below, you can run the src/seed.sql script in DBeaver to seed your database. Then you can use the SELECT * FROM <table_name> command to retrieve the records from the tables and check that the tables were properly populated. As you're creating your queries for this assessment, you can execute your queries in DBeaver to see if they're retrieving the datasets properly.


Tables
Artists
Write a query to create a table called artists in src/artists.sql. It should have the following fields:

A artist_id field that serves as a primary key for the table
A artist_name field with a varying character datatype and a character limit of 255 characters
A genre_name field with a varying character datatype and a character limit of 100 characters


Songs
Write a query to create a table called songs in src/songs.sql. It should have the following fields:

A song_id field that serves as a primary key for the table
A song_name field with a varying character datatype, a character limit of 100 characters, and a default string value of no song title
A album_name field with a varying character datatype, a character limit of 100 characters, and a default string value of no album title
Create a one-to-many relationship between the artists and songs tables. (That is, an artist can be associated with many songs.) To do this, reference the artist_id from the artists table as a foreign key called artist in the songs table. Set a constraint on this foreign key so that it cannot be null.


Concerts
Write a query to create a table called concerts in src/concerts.sql. It should have the following fields:

A concert_id field that serves as a primary key for the table
A concert_name field with a varying character datatype, a character limit of 255 characters
A concert_date field with a date datatype


Create a many-to-many relationship between the artists and concerts tables. (That is, an artist can be scheduled to perform at various concerts, and a concert can have many artists performing in it.) To do this, create a join table called artists_concerts in src/artists_concerts.sql with the following fields:

A artist_id foreign key field with integer datatype that references artist_id from the artists table
A concert_id foreign key field with integer datatype that references concert_id from the concerts table
A scheduled_start_at field with a time datatype
A scheduled_end_at field with a time datatype
Create a composite key out of the artist_id and concert_id columns. Set this key as the primary key for the table.
