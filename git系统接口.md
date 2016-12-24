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
    gitUrl:"url" //原来为gitlabUrl
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
