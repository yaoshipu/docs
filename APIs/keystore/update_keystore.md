## 更新服务配置项

#### 注意事项

- 需要`user`权限

#### 请求

```
PUT /api/keystore/:key
```

##### 请求参数

```json
{
    "namespace": "shared-namespace",
    "value": "value"
}
```

##### 参数说明


|参数|描述|
|---|---|
|namespace|用户名称, 普通用户为自身LDAP用户名, 管理员用户为任意LDAP用户名或者`shared-namespace`|
|value|值|
|shared-namespace|共享参数|

##### 正常返回

```
200 OK
```

##### 错误返回
