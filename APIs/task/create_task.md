## 创建任务

#### 注意事项

- 需要`user`权限

#### 请求

```
POST /api/tasks
```

##### 请求参数

```json
{
  "type": "pipeline",
  "pipeline_name": "demo-pipeline",
  "sub_tasks": [
    {
      "type": "build",
      "repo_owner": "yaoshipu",
      "repo_name": "sample-helloworld",
      "branch": "master",
      "pull_request_number": 6,
      "commit_id": "e96fb0b53ff1895354c1b1276e4536a6a7b1bd74",
      "commit_message": "test drone yml update",
      "image": "image full name",
      "package_file": "build service kodo package file",
      "timeout": 7200
    }
  ]
}
```

##### 参数说明

|key|value|
|---|---|
|pipeline_name|工作流名称|
|repo_name|代码库名称|
|repo_owner|代码库所有人|
|branch|代码编译分支 如果提供了pull_request_number, branch会被忽略|
|pull_request_number|pull request number|
|commit_id|commitID 如果是提交PR, 则需要提供|

##### 正常返回

```
200 OK
```

##### 错误返回
