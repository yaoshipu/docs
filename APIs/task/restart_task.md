## 重试任务

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/v2/tasks/id/:id/pipelines/:name/restart
```

##### 请求参数

- id：队列任务的ID
- name: pipeline 名称

##### 参数说明

无

##### 正常返回

```
200 OK
```

##### 错误返回
