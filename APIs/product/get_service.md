## 查询服务

#### 注意事项

#### 请求

```
GET /api/products/:productName/groups/:groupName/services/:serviceName
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
{
  "service_name": "index",
  "ingress": [
    {
      "name": "index",
      "hosts": "index-demo.ke-cs.dev.qiniu.io",
      "address": "10.200.20.43,10.200.20.44,10.200.20.69",
      "ports": "80",
      "age": "5d"
    }
  ],
  "pods": [
    {
      "name": "portal-v4-index-2615846670-x9xz0",
      "ready": "1/1",
      "status": "Running",
      "restarts": 2,
      "age": "5d",
      "ip": "172.20.177.165",
      "node": "cs58"
    }
  ],
  "service": [
    {
      "name": "portal-v4-index",
      "clust_ip": "None",
      "external_ip": "\u003cnone\u003e",
      "ports": "80/TCP",
      "age": "5d",
      "selector": "product=portal-v4,service=index,svc-group=portal-v4"
    }
  ],
  "replica_set": [
    {
      "name": "portal-v4-index-2615846670",
      "desired": 1,
      "current": 1,
      "ready": 1,
      "age": "5d",
      "containers": "index",
      "images": "index-dev.qiniu.io/spock/index:latest",
      "selector": "pod-template-hash=2615846670,product=portal-v4,service=index,svc-group=portal-v4"
    }
  ]
}
```
##### 错误返回
