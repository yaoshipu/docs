## 列出任务状态

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/v2/tasks/status
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  "test-pipeline": {
    "lastest_task": {
      "task_id": 23,
      "task_creator": "yaoshipu",
      "pipeline_name": "test-pipeline",
      "status": "passed",
      "created": 1507719109,
      "started": 1507721237,
      "updated": 1507721240
  }
]
```

##### 错误返回
