## 测试容器实时日志

#### 注意事项

- 需要`user`权限

#### 请求

```
WS /api/logs/ws/pipelines/:pipelineName/tasks/:taskId/tests/:testName/tails/:lines
```
##### 请求参数

无

##### 参数说明

|参数|说明|
|---|---|
|pipelineName|pipeline名称|
|taskId|任务id|
|testName|测试job名称|
|lines|获取实时日志的行数|

##### 正常返回

```
200 OK
```

##### 错误返回
