## 服务实时日志

#### 注意事项

- 需要`user`权限

#### 请求

```
WS /api/logs/ws/pods/:podName/containers/:containerName
```
##### 请求参数

无

##### 参数说明

|参数|说明|
|---|---|
|podName|服务Pod名称|
|containerName|容器名称|

##### 正常返回

```
200 OK
```

##### 错误返回
