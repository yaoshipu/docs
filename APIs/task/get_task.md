## 查询任务

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/v2/tasks/id/:id/pipelines/:name
GET /api/v2/tasks/ws/id/:id/pipelines/:name
```

##### 请求参数

无

##### 参数说明

|参数|说明|
|---|---|
|id|运行任务的ID|
|name|pipeline名称|

##### 正常返回

```json
{
  "task_id": 1,
  "pipeline_name": "test-pipeline",
  "status": "failed",
  "task_creator": "yaoshipu",
  "task_revoker": "yaoshipu",
  "create_time": 1507111692,
  "start_time": 1507111694,
  "end_time": 1507111692,
  "sub_tasks": [
    {
      "Log": {},
      "branch": "master",
      "commit_id": "e96fb0b53ff1895354c1b1276e4536a6a7b1bd74",
      "commit_message": "test drone yml update",
      "image": "image full name",
      "package_file": "build service kodo package file",
      "pull_request_id": 6,
      "repo_name": "sample-helloworld",
      "repo_owner": "yaoshipu",
      "service_name": "",
      "status": "cancelled",
      "reaper_build_nubmer": 127,
      "reaper_procs": [
        {
          "job_id": 1,
          "prod_names": [
            "aslan-platform.git",
            "backend_build",
            "frontend_build",
            "publish"
          ]
        }
      ],
      "timeout": 3600,
      "type": "build"
    }
  ]
}
```

##### 错误返回
