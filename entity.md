# Entity

---

各个entity的基本信息.

## user

| type | name | comment |
| :--- | :--- | :--- |
| int | id |not null ,auto inc (插入时自动生成)  下同  |
| string | username |not null , unique |
| string | name |  |
| string | password |not null |
| url | avatar |  |
| enum\('male','female'\) | gender |not null |
| email | email | not null |
| int | schoolId |not null  |
| enum\('admin','student','teacher'\) | type | not null  |
| timestamp |createdAt  |not null (插入时自动生成) 下同 |
| timestamp |deletedAt  | null (删除时手动设置) 下同|

## student extends user

| type | name | comment |
| :--- | :--- | :--- |
| int | gitId |not null  |
| string | number | 学号 |
| collection | courses | 参加的课程 |

## teacher extends user

| type | name | comment |
| :--- | :--- | :--- |
| boolean | authority | not null 是否有审批权限 |
| collection | courses | 教的课程 |

## course

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | name |not null, unique 如"14软件工程II二班" |
| string | description |  |
| collection | teachers | 参加的老师 |
| collection | students | 参加的学生 |
| collection | homeworks | 作业 |
| collection | exams | 考试 |

## question

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | title |not null , unique |
| string | description | not null |
| url | gitUrl | 对应git地址 |
| url | fileUrl | 压缩包的地址 |
| User | creator |not null  |
| User | verifier | 审批者,null时表示未审批 |
| string | type |not null 题目类型 |

## assignment

| type | name | comment |
| :--- | :--- | :--- |
| int | id |  |
| string | title |not null |
| string | description |  |
| Datetime | startAt | not null 开始时间 |
| Datetime | endAt | not null 结束时间 |
| User | author |not null 创建者 |
| Course | course |not null 课程 |
| enum\('newly','notInit','initing',<br>initFail','initSuccess','ongoing',<br>'timeUp','analyzing','analyzingFinish'\) | status |not null git仓库初始化情况.新建,还未初始化,正在初始化,失败,成功,考试或作业进行中,时间到,分析中,分析结束 |
| enum('exam','homework') | type |not null 类型 |
| enum('onlineProgram') | mode |not null 模式 |
| Collection | students |   |

## onlineProgramAssignment
| type | name | comment |
| :--- | :--- | :--- |
| Collection | questions |  |
| Collection | initFailStudent | 仓库初始化失败的学生 |

## score

| type | name | comment |
| :--- | :--- | :--- |
| Student | student | not null |
| Assignment | assigment | not null  |
| Question | question | not null  |
| int | score | 成绩,null表示成绩未出 |
| url | analysisReportUrl | 详细分析的url |
| url | scoreReportUrl | 成绩分析url |



