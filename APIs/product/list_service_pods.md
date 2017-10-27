## 列出服务Pods

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/pods
```

##### 请求参数

```json
{
  "selector": "s-product=portal-v4"
}
```

##### 参数说明

无

##### 正常返回

```json
[
  {
    "name": "portal-v4-atboard-backend-4270770443-qksn4",
    "status": "Running",
    "age": "1d",
    "ip": "172.20.66.168",
    "labels": {
      "pod-template-hash": "4270770443",
      "s-group": "portal-v4",
      "s-product": "portal-v4",
      "s-service": "atboard-backend"
    },
    "containers": [
      {
        "name": "atboard-backend",
        "image": "index.qiniu.com/spocktest/atboard-backend:201709151717-v12-dev",
        "restart_count": 0,
        "status": "running",
        "message": "",
        "reason": ""
      }
    ]
  },
  {
    "name": "portal-v4-atboard-frontend-3647558514-cqp4k",
    "status": "Running",
    "age": "1d",
    "ip": "172.20.66.189",
    "labels": {
      "pod-template-hash": "3647558514",
      "s-group": "portal-v4",
      "s-product": "portal-v4",
      "s-service": "atboard-frontend"
    },
    "containers": [
      {
        "name": "atboard-frontend",
        "image": "index.qiniu.com/spocktest/atboard-frontend:201709121726-v292-ava-807",
        "restart_count": 0,
        "status": "running",
        "message": "",
        "reason": ""
      }
    ]
  }
]
```

##### 错误返回
