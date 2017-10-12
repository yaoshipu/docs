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

```json
{
  "id": 51,
  "name": "test-secret",
  "image": [
    "index.qiniu.com/spock/docker-client",
    "index.qiniu.com/spock/golang:1.7"
  ],
  "event": [
    "pull_request",
    "push"
  ]
}
```	

##### 错误返回
