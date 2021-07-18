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

```

```
<br>
