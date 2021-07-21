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

8.List the continents that have a total population of at least 100 million.
```
SELECT continent FROM world as A
WHERE (SELECT SUM(population) FROM world AS B WHERE
A.continent = B.continent) >= 100000000
GROUP BY continent;

-- This will return the countries and the population but they want just the countries the
-- above will give just the countries

SELECT continent, SUM(population) FROM world
GROUP BY continent 
HAVING SUM(population) > 100000000;

```


