## 删除服务配置项

#### 注意事项

- 需要`user`权限
- 此接口用于删除用户的配置

#### 请求

```
DELETE /api/keystore/:key?namespace=:namespace
```

##### 请求参数

|参数|描述|
|---|---|
|namespace|用户名称, 普通用户为自身LDAP用户名, 管理员用户为任意LDAP用户名或者`shared-namespace`|
|key|需要删除的键|

##### 参数说明

无

##### 正常返回

```
200 OK
```

##### 错误返回
