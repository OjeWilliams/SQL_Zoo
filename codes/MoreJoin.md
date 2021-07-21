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

3.Give the total GDP of Africa
```
SELECT SUM(gdp) FROM world
WHERE continent = 'Africa' ;
```
<br>

4.How many countries have an area of at least 1000000
```
SELECT COUNT(name) FROM world
WHERE area >= 1000000 ;
```
<br>

5.What is the total population of ('Estonia', 'Latvia', 'Lithuania')
```
SELECT SUM(population) FROM world
WHERE name IN ('Estonia', 'Latvia', 'Lithuania');
```
<br>

6.For each continent show the continent and number of countries.
```
SELECT continent, COUNT(name) FRom world
GROUP BYcontinent ;
```
<br>

7.For each continent show the continent and number of countries with populations of at least 10 million.
```
SELECT continent, COUNT(name) FROM world
WHERE population >= 10000000
GROUP BY continent ;

-- Initially thought this would be correct but this first groups the countries by continent and returns 
-- continents which have more than a 100 million countries. i,e none lol

SELECT continent, COUNT(population) FROM world
GROUP BY continent 
HAVING COUNT(populations) >= 10000000;

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


