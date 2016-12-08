# Entity

---

各个entity的基本信息.

## user

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | username |  |
| url | avatar |  |
| enum\('male','female'\) | gender |  |
| email | email |  |
| int | school\_id |  |
| enum\('admin','student','teacher'\) | type |  |

## student extends user

| type | name | comment |
| :--- | :--- | :--- |
| int | git\_id |  |
| string | number |  |
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



