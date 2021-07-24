# Questions can be fount here https://sqlzoo.net/wiki/Using_Null

1.List the teachers who have NULL for their department.
```
SELECT name FROM teacher 
WHERE dept IS NULL ;
```
<br>

2.Note the INNER JOIN misses the teachers with no department and the departments with no teacher.
```
SELECT teacher.name, dept.name
 FROM teacher INNER JOIN dept
           ON (teacher.dept=dept.id)
```
<br>

3.Use a different JOIN so that all teachers are listed.
```
SELECT teacher.name, dept.name
 FROM teacher LEFT JOIN dept
           ON (teacher.dept=dept.id)
```
<br>

4.Use a different JOIN so that all departments are listed.
```
SELECT teacher.name, dept.name
 FROM teacher RIGHT JOIN dept
           ON (teacher.dept=dept.id) ;
```
<br>

5.Use COALESCE to print the mobile number. Use the number '07986 444 2266' if there is no number given. Show teacher name and mobile number or '07986 444 2266'
```
SELECT name, COALESCE(mobile, '07986 444 2266') 
FROM teacher ;
```
<br>

6.Use the COALESCE function and a LEFT JOIN to print the teacher name and department name. Use the string 'None' where there is no department.
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
<br>

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
```

<br>

13.Obtain a list, in alphabetical order, of actors who've had at least 15 starring roles.
```
SELECT name FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = casting.actorid
WHERE ord = 1
GROUP BY name HAVING COUNT(ord) >= 15
ORDER BY name;
```
<br>

14.List the films released in the year 1978 ordered by the number of actors in the cast, then by title.
```
SELECT title, COUNT(actorid) FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = casting.actorid
WHERE yr = 1978
GROUP BY title
ORDER BY COUNT(actorid) DESC, title;

```
<br>

15.List all the people who have worked with 'Art Garfunkel'.
```
SELECT name FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = casting.actorid
WHERE movie.id IN
(SELECT movie.id FROM movie
        JOIN casting ON movie.id = movieid
        JOIN actor ON actor.id = casting.actorid
        WHERE actor.name = 'Art Garfunkel')
AND actor.name != 'Art Garfunkel'
;
```

