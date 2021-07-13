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
