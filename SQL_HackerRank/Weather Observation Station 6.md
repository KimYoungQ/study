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
