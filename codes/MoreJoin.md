1.List the films where the yr is 1962 [Show id, title]
```
SELECT id, title
 FROM movie
 WHERE yr=1962 ;
```
<br>

2.Give year of 'Citizen Kane'.
```
SELECT yr FROM movie
WHERE title = 'Citizen Kane';
```
<br>

3.List all of the Star Trek movies, include the id, title and yr (all of these movies include the words Star Trek in the title). Order results by year.
```
SELECT id, title, yr FROM movie
WHERE title LIKE 'Star Trek%'
ORDER BY yr;
```
<br>

4.What id number does the actor 'Glenn Close' have?
```
SELECT id FROM actor
WHERE name = 'Glenn Close';
```
<br>

5.What is the id of the film 'Casablanca'
```
SELECT id FROM movie
WHERE title = 'Casablanca';
```
<br>

6.Obtain the cast list for 'Casablanca'. what is a cast list? <br>
Use movieid=11768, (or whatever value you got from the previous question)
```
SELECT name FROM casting
JOIN actor ON casting.actorid = actor.id
WHERE movieid = 27;
```
<br>

7.btain the cast list for the film 'Alien'
```
SELECT DISTINCT(name) FROM actor
JOIN casting ON actor.id = actorid
JOIN movie ON movie.id = movieid
WHERE title = 'Alien';

```
<br>

8.List the films in which 'Harrison Ford' has appeared
```
SELECT title FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = casting.actorid
WHERE name = 'Harrison Ford' ;
```

9.List the films where 'Harrison Ford' has appeared - but not in the starring role. [Note: the ord field of casting gives the position of the actor. If ord=1 then this actor is in the starring role]
```
SELECT title FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = casting.actorid
WHERE name = 'Harrison Ford' AND ord != 1 ;
```
<br>

10.List the films together with the leading star for all 1962 films.
```
SELECT title, name FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = casting.actorid
WHERE ord = 1 AND yr = 1962;
```
<br>

11.Which were the busiest years for 'Rock Hudson', show the year and the number of movies he made each year for any year in which he made more than 2 movies.
```
SELECT yr, COUNT(*) FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = casting.actorid
WHERE name = 'Rock Hudson'
GROUP BY yr  HAVING COUNT(*) > 2 ;

```
<br>

12.List the film title and the leading actor for all of the films 'Julie Andrews' played in.
```
SELECT title, name FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = casting.actorid
WHERE movie.id IN
(SELECT movie.id FROM movie
        JOIN casting ON movie.id = movieid
        JOIN actor ON actor.id = casting.actorid
        WHERE actor.name = 'Julie Andrews')
AND casting.ord = 1;


