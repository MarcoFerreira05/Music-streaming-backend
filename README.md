# Computer Labs III (2024/2025)

## Grade
20/20

## Group Participants
* Marco Rocha Ferreira - A106857 - MarcoFerreira05
* Lucas Rafael da Cunha Franco Robertson - A89467 - lucasxdsy
* Samuel Gibson Da Cunha Figueiredo Lobato  - A106907 - samuelgib05

## Description

This is a database-like application for a music streaming service (e.g., Spotify) built in C. 

### Project Goals

The main goals of this project are:
* deepen knowledge and practical skills with the C programming language, including the use of gdb to debug and valgrind to analyse memory leaks
* learn how to build a scalable code base through modularity and encapsulation
* apply time and spacial algorithmic analysis to ensure query performance, even with large amounts of data

### How It Works

Data is first parsed from CSV files and then stored in memory using different strategies and data structures in order to efficiently answer any of the 6 queries. The CSV files are organized as follows:
* Musics:
    * id
    * title
    * list of artist ids
    * duration
    * genre
    * year
    * lyrics
* Users:
    * username
    * email
    * first_name
    * last_name
    * birth_date 
    * country
    * subscription_type
    * list of liked musics ids
* Artists:
    * id
    * name
    * description
    * recipe_per_stream
    * type (individual or group)
    * list of constituents ids
    * country 
* Albums:
    * id
    * title
    * list of artists ids
    * year
    * producers
* History:
    * id
    * user_id
    * music_id
    * timestamp
    * duration
    * platform (mobile or desktop)

With this data, the application is required to be able to answer the following 6 queries.
1. Generate the summary of a user or artist, according to the id received by argument. User result: email;first_name;last_name;age;country. Artist result: name;type;country;num_albums_individual;total_recipe.
2. List the top N artists with the biggest discography. The query can receive an optional country filter.
3. Enumerate the most popular music genres in a given age group, in descending order of likes.
4. Determine the artist who has been in the top 10 the most times. The query can also receive an optional time range, so it either refers to the whole dataset or the given interval.
5. Recomend N users to a target user based on the latter's musical taste
6. Generate the annual summary of a given user. The query receives the year and the user id and produces the following output: listening time;number_musics;most_listened_artist;day_with_most_reproductions;favorite_genre;favorite_album;favorite_hour. The query can also receive an optional argument to show the top 10 most played artists by the user (artist_name;number_musics_from_this_artist;listening_time).

Finally, time and memory usage constraints were imposed according to the size of the dataset in order to stimulate good resource management.