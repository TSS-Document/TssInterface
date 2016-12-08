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
| string | type | 题目类型 |

## assignment

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | title |  |
| string | description |  |
| Datetime | startAt |  |
| Datetime | endAt |  |
| User | author | 创建者 |
| Course | course | 课程 |
| enum\('fail','success','notyet'\) | gitInitStatus | git仓库初始化情况.失败,成功,或还未初始化. |



