* [문제 보러가기](https://www.hackerrank.com/challenges/more-than-75-marks/problem?h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen)
```
select name
from STUDENTS
where MARKS > 75
order by right(name,3), ID
```
