# git系统接口

---

## 修改记录

* **2016.12.28**  [\#创建考试所需仓库](#创建考试所需仓库) projects参数改为 string的list
* **2017.01.05**  [\#上传项目](#上传项目)url改成exam/uploadProject，原本是exams/uploadProject

## 上传项目

```
POST /exam/uploadProject
```

Param

```js
{
    projectName:"string",
    fileUrl:"url"
}
```

Response

```js
{
    gitUrl:"xxxxx.git" //原来为gitlabUrl
}
```

## 创建用户

```
POST /users/createUser
// 原来为/user,现在加了个s
```

Param

```js
{
    username:"string",
    password:"string"
}
```

Response

```js
{
    gitId: 1 
    //原来为gitlabId,返回值为string
    //现在是gitId,返回值是int
}
```

## 创建考试所需仓库

```
POST /exams/createRepos
```

Param

```js
{
    //这个接口变得比较多
    gitIds:[1,2,3],
    projects:[
        "exam1_project1"
        "exam1_project2"
        //tss系统按某些规则,比如 考试+项目名 生成的
        ...
    ]
}
```

Response

```js
{
    failedRepo:{
        1 : ["exam1_project1","exam1_project2"],
        2 : ["exam1_project1"]
        // gitId : projectNames
    }
}
```



