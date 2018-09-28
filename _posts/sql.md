---
layout:     post
title:      SQL 基础操作
subtitle:   sql的基础操作
date:       2018-09-28
author:     wy
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - SQL
    - DataScience
    - DataBase
---
# SQL
## function, declare, limit, offset
``` sql
CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
BEGIN
  declare m INT;
  set m = n-1;
  RETURN (
      select distinct Salary 
      from Employee 
      order by Salary 
      desc
      limit 1 offset m 
  );
END
```

## top 3 without using limit
* key point:  one salary is among top 3 = less than 3 (<3) salary is larger than itself
``` sql
select Department.Name as Department, e1.Name as Employee, e1.Salary as Salary
from Department , Employee e1
where e1.DepartmentId=Department.Id and 
3 > (
    select count(distinct(e2.salary))
    from employee e2
    where e1.Salary < e2.Salary and e1.DepartmentId = e2.DepartmentId
)
order by  Department, Salary
```

## Between 
`(Request_at BETWEEN '2013-10-01' AND '2013-10-03')`

## Not In
``` sql
where client_id not in (select users_id as id
                        from Users
                        where Banned='Yes')
```

## IF
`IF(condition, value_if_true, value_if_false)`

``` sql
ROUND(COUNT(IF(Status != 'completed', TRUE, NULL)) / COUNT(*), 2) AS 'Cancellation Rate'
```

