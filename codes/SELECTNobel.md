1.Change the query shown so that it displays Nobel prizes for 1950.
```
SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
```
<br>

2.Show who won the 1962 prize for Literature.
```
SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'Literature'
```
<br>

3.Show the year and subject that won 'Albert Einstein' his prize.
```
SELECT yr, subject FROM nobel
WHERE winner = 'Albert Einstein';
```
<br>

4.Give the name of the 'Peace' winners since the year 2000, including 2000.
```
SELECT winner FROM nobel
WHERE yr >= 2000 and subject='peace';
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
