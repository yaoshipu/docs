## 查询密钥配置

#### 注意事项

- 需要`admin`权限

#### 请求

```
GET /api/repos/:owner/:name/secrets/:secretName
```

##### 请求参数

无

##### 参数说明

|参数|说明|
|---|---|
|owner|Github用户|
|name|Github仓库名称|
|secretName|密钥名称|

##### 正常返回

```
200 OK
```

##### 错误返回
