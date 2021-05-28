* [Average Population of Each Continent](https://www.hackerrank.com/challenges/average-population-of-each-continent/problem?h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen)

```
SELECT B.CONTINENT, AVG(A.POPULATION)
    FROM CITY AS A
        INNER JOIN COUNTRY AS B
            ON A.COUNTRYCODE = B.CODE
    GROUP BY B.CONTINENT
```
