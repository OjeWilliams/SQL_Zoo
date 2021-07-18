Questions can be found here https://sqlzoo.net/wiki/SELECT_within_SELECT_Tutorial

1.List each country name where the population is larger than that of 'Russia'. 
```
SELECT name FROM world
  WHERE population >
     (SELECT population FROM world
      WHERE name='Russia');
```
<br>

2.Show the countries in Europe with a per capita GDP greater than 'United Kingdom'.
```
SELECT name FROM world 
WHERE continent = 'Europe' 
AND gdp/population > (Select gdp/population from world where name = 'United Kingdom');
```
<br>

3.List the name and continent of countries in the continents containing either Argentina or Australia. Order by name of the country.
```
SELECT name, continent FROM world 
WHERE continent IN ( SELECT continent FROM world 
                    WHERE name IN ('Australia','Argentina'))
ORDER BY name
;
```
<br>

4.Which country has a population that is more than Canada but less than Poland? Show the name and the population.
```
SELECT name, population FROMM world 
WHERE population >
(SELECT population FROM world
WHERE name ='Canada') 
AND
population < (SELECT population FROM world
WHERE name ='Poland') 
;
```
<br>

5.Germany (population 80 million) has the largest population of the countries in Europe. Austria (population 8.5 million) has 11% of the population of Germany. <br>
Show the name and the population of each country in Europe. Show the population as a percentage of the population of Germany.
```

```
<br>

```

```
<br>

```

```
<br>

```

```
<br>

```

```
<br>

```

```
<br>
