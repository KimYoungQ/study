```
select distinct CITY
from STATION
where CITY not like '[aeiou]%' or CITY not like '%[aeiou]'
```
