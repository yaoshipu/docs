## 查询服务

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/products/:productName/groups/:groupName/services/:serviceName
```

##### 请求参数

|参数|说明|
|---|---|
|productOwner|默认不填为获取自身产品服务信息，填{owner name}为获取该用户产品服务信息，需要授权|

##### 参数说明

无

##### 正常返回

```json
{
  "service_name": "spock-frontend",
  "ingress": [
    {
      "name": "spock-dev-spock-frontend",
      "labels": {
        "s-group": "spock-dev",
        "s-product": "spock-dev",
        "s-service": "spock-frontend"
      },
      "host_info": [
        {
          "host": "spock-dev.ke-cs.dev.qiniu.io",
          "backend": [
            {
              "service_name": "spock-dev-spock-frontend",
              "service_port": "80"
            }
          ]
        }
      ],
      "ips": [
        "10.200.20.42",
        "10.200.20.43",
        "10.200.20.44"
      ],
      "age": "1d"
    }
  ],
  "pods": [
    {
      "name": "spock-dev-spock-frontend-1304887289-jjn89",
      "status": "Running",
      "age": "1d",
      "ip": "172.20.177.173",
      "labels": {
        "pod-template-hash": "1304887289",
        "s-group": "spock-dev",
        "s-product": "spock-dev",
        "s-service": "spock-frontend"
      },
      "containers": [
        {
          "name": "spock-frontend",
          "image": "index.qiniu.com/spocktest/spock-frontend:20171207165723-726",
          "restart_count": 0,
          "status": "running",
          "message": "",
          "reason": ""
        }
      ]
    }
  ],
  "product_owner": "yaoshipu"
}
```
##### 错误返回
