# Entity

---

各个entity的基本信息.

## user

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | username |  |
| url | avatar |  |
| enum\('男','女'\) | gender | 待商榷 |
| email | email |  |
| int | school\_id |  |
| enum\('admin','student','teacher'\) | type |  |

## student extends user

| type | name | comment |
| :--- | :--- | :--- |
| int | git\_id |  |
| int | number | 学号,待商榷 |
| collection | courses |  |

## teacher extends user

| type | name | comment |
| :--- | :--- | :--- |
| boolean | authority | 是否有审批权限 |

## course

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | title |  |
| string | description |  |
| collection | teachers |  |
| collection | students |  |
| collection | homeworks |  |
| collection | exams |  |





