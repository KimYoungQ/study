* [Population Census](https://www.hackerrank.com/challenges/asian-population/problem) 

```
SELECT SUM(A.POPULATION) 
    FROM CITY AS A
      INNER JOIN COUNTRY AS B
        ON COUNTRYCODE = B.CODE
    WHERE B.CONTINENT = 'Asia'
```
