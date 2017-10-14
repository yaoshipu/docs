## 列出Agent状态

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/v2/status/agents
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
{
  "test-pipeline": {
    "lastest_task": {
      "task_id": 23,
      "task_creator": "yaoshipu",
      "pipeline_name": "test-pipeline",
      "status": "passed",
      "create_time": 1507278250,
      "start_time": 1507278250,
      "end_time": 1507278254
    },
    "last_task_success": {
      "task_id": 23,
      "task_creator": "yaoshipu",
      "pipeline_name": "test-pipeline",
      "status": "passed",
      "create_time": 1507278250,
      "start_time": 1507278250,
      "end_time": 1507278254
    },
    "last_task_failure": null
  }
}
```

##### 错误返回
