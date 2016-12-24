# git系统接口

---

##上传项目

```
POST /exams/uploadProject
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

##创建用户

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

##创建考试所需仓库
```
POST /exams/createRepos
```
Param
```js
{
    //这个接口变得比较多
    gitIds:[1,2,3],
    projects:{
        "exam1_project1":"xxxxx.git"
    }
}
```