* [문제 보러가기](https://www.hackerrank.com/challenges/weather-observation-station-6/problem?h_r=next-challenge&h_v=zen)
```
select distinct CITY
from STATION
where CITY like 'a%'
    or CITY like 'e%'
    or CITY like 'i%'
    or CITY like 'o%'
    or CITY like 'u%'
```

모범답안
```
select city from station where city like "[aeiou]%";
```
