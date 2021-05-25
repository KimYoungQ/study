```
select TOP 1 CITY, len(CITY)
from STATION
order by len(CITY), CITY

select TOP 1 CITY, len(CITY)
from STATION
order by len(CITY) desc, CITY
```
