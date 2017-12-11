## 取消等待中任务

#### 注意事项

- 需要`user`权限
- 用于取消等待中的任务，包括waiting和blocked的任务

#### 请求

```
DELETE /api/v2/tasks/id/:id/pipelines/:name/pending
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
