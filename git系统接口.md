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
    gitUrl:"url"
}
```

##创建用户

```
POST /users/createUser
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
    gitId
}
```
