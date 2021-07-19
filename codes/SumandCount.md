1.Show the total population of the world.
```
SELECT SUM(population)
FROM world;
```
<br>

2.List all the continents - just once each.
```
SELECT continent FROM world;
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

```

```
<br>

```

```
<br>

```

```
<br>
