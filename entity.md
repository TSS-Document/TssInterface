# Entity

---

各个entity的基本信息.

## user

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | username | unique |
| string | name |  |
| url | avatar |  |
| enum\('male','female'\) | gender |  |
| email | email |  |
| int | schoolId |  |
| enum\('admin','student','teacher'\) | type |   |

## student extends user

| type | name | comment |
| :--- | :--- | :--- |
| int | gitId |  |
| string | number | 学号 |
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
| string | name | unique 如"14软件工程II二班" |
| string | description |  |
| collection | teachers | 参加的老师 |
| collection | students | 参加的学生 |
| collection | homeworks | 作业 |
| collection | exams | 考试 |

## question

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | title | unique |
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
| enum\('newly','notInit','initing',<br>initFail','initSuccess','ongoing',<br>'timeUp','analyzing','analyzingFinish'\) | gitInitStatus | git仓库初始化情况.新建,还未初始化,正在初始化,失败,成功,考试或作业进行中,时间到,分析中,分析结束 |
| Collection | students |   |

## onlineProgramAssignment
| type | name | comment |
| :--- | :--- | :--- |
| Collection | questions |  |
| Collection | initFailStudent | 仓库初始化失败的学生 |

## score

| type | name | comment |
| :--- | :--- | :--- |
| Student | student |  |
| Assignment | assigment |  |
| Question | question |  |
| int | score | 成绩,null表示成绩未出 |
| url | analysisReportUrl | 详细分析的url |
| url | scoreReportUrl | 成绩分析url |



