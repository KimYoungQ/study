* [African Cities](https://www.hackerrank.com/challenges/african-cities/problem?h_r=next-challenge&h_v=zen)

```
SELECT A.NAME 
    FROM CITY AS A
        INNER JOIN COUNTRY AS B
            ON A.COUNTRYCODE = B.CODE
    WHERE B.CONTINENT = 'Africa'
```