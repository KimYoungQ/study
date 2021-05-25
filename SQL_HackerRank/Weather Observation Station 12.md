* [문제보러가기](https://www.hackerrank.com/challenges/weather-observation-station-12/problem?h_r=next-challenge&h_v=zen)
```
select distinct CITY
from STATION
where CITY not like '%[aeiou]' and CITY not like '[aeiou]%'
```
