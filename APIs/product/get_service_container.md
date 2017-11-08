## 查询服务容器是否存在

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/products/:productName/groups/:groupName/services/:serviceName/containers/:container
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
{
   "pods" : [
      {
         "name" : "memcached-memcached-2064967262-gnl53",
         "status" : "Running",
         "containers" : [
            {
               "message" : "",
               "restart_count" : 0,
               "name" : "memcached",
               "status" : "running",
               "image" : "index.qiniu.com/spocktest/memcached:1.5.2",
               "reason" : ""
            }
         ],
         "age" : "13s",
         "ip" : "172.20.177.190",
         "labels" : {
            "s-group" : "memcached",
            "s-service" : "memcached",
            "s-product" : "memcached",
            "pod-template-hash" : "2064967262"
         }
      }
   ],
   "service_name" : "memcached",
   "ingress" : [
      {
         "age" : "14s",
         "name" : "memcached-memcached",
         "ips" : [
            "10.200.20.42",
            "10.200.20.43",
            "10.200.20.44"
         ],
         "host_info" : [
            {
               "backend" : [
                  {
                     "service_port" : "11211",
                     "service_name" : "memcached-memcached"
                  }
               ],
               "host" : "memcached-memcached-yaoshipu.ke-cs.dev.qiniu.io"
            }
         ],
         "labels" : {
            "s-group" : "memcached",
            "s-service" : "memcached",
            "s-product" : "memcached"
         }
      }
   ]
}
```
##### 错误返回
