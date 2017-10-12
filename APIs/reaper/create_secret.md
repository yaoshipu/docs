## 创建密钥配置

#### 注意事项

- 需要`admin`权限
- event: 可选择的event为 pull_request, push, tag, deployment. 默认选择为 pull_request  
- image: 授权注入secrets的镜像名称

#### 请求

```
POST /api/repos/:owner/:name/secrets
```

##### 请求参数

```json
{
  "name": "test-secret",
  "value": "test-pwd",
  "image": [
    "index.qiniu.com/spock/docker-client",
    "index.qiniu.com/spock/golang:1.7"
  ]
}
```

##### 参数说明

|参数|说明|
|---|---|
|owner|Github用户|
|name|Github仓库名称|

##### 正常返回

```json
{
  "id": 22,
  "name": "test-secret",
  "image": [
    "index.qiniu.com/spock/docker-client",
    "index.qiniu.com/spock/golang:1.7"
  ],
  "event": [
    "pull_request"
  ]
}
```	
##### 错误返回
