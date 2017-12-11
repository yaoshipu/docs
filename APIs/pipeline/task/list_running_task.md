## 列出运行中任务

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/v2/tasks/running
GET /api/v2/tasks/ws/running [websocket 接口]
```
##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
[
  {
    "task_id": 1,
    "pipeline_name": "test-pipeline",
    "status": "running",
    "task_creator": "yaoshipu",
    "create_time": 1507107936,
    "start_time": 1507107939,
    "end_time": 1507107936,
    "sub_tasks": [
      {
        "branch": "master",
        "commit_id": "e96fb0b53ff1895354c1b1276e4536a6a7b1bd74",
        "commit_message": "test drone yml update",
        "image": "image full name",
        "package_file": "build service kodo package file",
        "pull_request_id": 6,
        "repo_name": "sample-helloworld",
        "repo_owner": "yaoshipu",
        "timeout": 3600,
        "type": "build"
      }
    ]
  }
]
```

##### 错误返回
