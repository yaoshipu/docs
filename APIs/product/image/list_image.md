## 列出镜像

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/registry/images
```

##### 请求参数

无

##### 参数说明

|参数|描述|
|---|---|
|host|registry域名|
|owner|registry用户名|
|name|服务名称，命名规则[a-z0-9_.-]|
|tag|标签，命名规则[A-Za-z0-9_.-]|

##### 正常返回

```json
[
  {
    "host": "index.qiniu.com",
    "owner": "spocktest",
    "name": "zoneproxy.kodo-1",
    "tag": "20170217-v2-develop"
  },
  {
    "host": "index.qiniu.com",
    "owner": "spocktest",
    "name": "zoneproxy.kodo-1",
    "tag": "latest"
  },
  {
    "host": "index.qiniu.com",
    "owner": "spocktest",
    "name": "acc",
    "tag": "20170427-v21-develop"
  },
  {
    "host": "index.qiniu.com",
    "owner": "spocktest",
    "name": "acc",
    "tag": "latest"
  }
]

##### 错误返回
