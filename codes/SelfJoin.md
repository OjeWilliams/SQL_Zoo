1.How many stops are in the database.
```
SELECT COUNT(*) FROM stops;
```
<br>

2.Find the id value for the stop 'Craiglockhart'
```
SELECT id FROM stops 
WHERE name = 'Craiglockhart' ;
```
<br>

3.Give the id and the name for the stops on the '4' 'LRT' service.
```
SELECT id, name FROM stops
JOIN route on id = stop
WHERE num = 4 AND company = 'LRT' ;
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

```

```
<br>
