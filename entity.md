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
| int | schoolId |  |
| enum\('admin','student','teacher'\) | type |  |

## student extends user

| type | name | comment |
| :--- | :--- | :--- |
| int | gitId |  |
| string | number |  |
| collection | courses | 参加的课程 |

## teacher extends user

| type | name | comment |
| :--- | :--- | :--- |
| boolean | authority | 是否有审批权限 |
| collection | courses | 教的课程 |

## course

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | title |  |
| string | description |  |
| collection | teachers | 参加的老师 |
| collection | students | 参加的学生 |
| collection | homeworks | 作业 |
| collection | exams | 考试 |

## question

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | description |  |
| url | gitUrl | 对应git地址 |
| url | fileUrl | 压缩包的地址 |
| User | creator |  |
| User | verifier | 审批者,null时表示未审批 |
| string | type | 题目类型 |

## assignment

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | title |  |
| string | description |  |
| Datetime | startAt | 开始时间 |
| Datetime | endAt | 结束时间 |
| User | author | 创建者 |
| Course | course | 课程 |
| enum\('fail','success','notyet'\) | gitInitStatus | git仓库初始化情况.失败,成功,或还未初始化. |
| Collection | questions |  |
| Collection | students |  |
| Collection | initFailStudent | 仓库初始化失败的学生 |



