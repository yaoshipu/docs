## 取消运行中任务

#### 注意事项

- 需要`user`权限
- 用于取消运行中的任务，不能取消调用第三方接口的子任务，下一个子任务会被取消

#### 请求

```
DELETE /api/v2/tasks/id/:id/pipelines/:name/running
```

##### 请求参数

无

##### 参数说明

|参数|说明|
|---|---|
|id|运行任务的ID|
|name|pipeline名称|

##### 正常返回

```
200 OK
```

##### 错误返回
