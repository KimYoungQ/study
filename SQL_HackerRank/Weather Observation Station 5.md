* [문제 보러가기](https://www.hackerrank.com/challenges/weather-observation-station-5/problem?h_r=next-challenge&h_v=zen)
```
select TOP 1 CITY, len(CITY)
from STATION
order by len(CITY), CITY

select TOP 1 CITY, len(CITY)
from STATION
order by len(CITY) desc, CITY
```
