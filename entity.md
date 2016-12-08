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
| collection | courses |  |

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

## question

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | description |  |
| url | git\_url |  |
| url | file\_url | 压缩包的地址 |
| User | creator |  |
| User | verifier | 审批者,null时表示未审批 |



