All question can be found here https://sqlzoo.net/wiki/SELECT_from_WORLD_Tutorial </br>
1.Read the notes about this [table](https://sqlzoo.net/wiki/Read_the_notes_about_this_table.). Observe the result of running this SQL command to show the name, continent and population of all countries.
```
SELECT name, continent, population FROM world;
```
</br>

2.How to use WHERE to filter records. Show the name for the countries that have a population of at least 200 million. 200 million is 200000000, there are eight zeros.
```
SELECT name
  FROM world
 WHERE population >= 200000000
```
</br>
3.Give the name and the per capita GDP for those countries with a population of at least 200 million.
```
SELECT name, gdp/population FROM world
WHERE population > 200000000 ;
```
</br>
4.Show the name and population in millions for the countries of the continent 'South America'. Divide the population by 1000000 to get population in millions.
```
SELECT name, population/1000000 FROM world
WHERE continent = 'South America';
```
</br>

5.Show the name and population for France, Germany, Italy
```
SELECT name, population FROM world
WHERE name in ('France','Germany','Italy') ;

```

</br>





</br>





</br>





</br>





</br>





</br>





</br>
