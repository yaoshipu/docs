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
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "branch": "dev",
      "pull_request_number": 123,
      "commit_id": "456",
      "bin": "spock-backend",
      "image": "index.qiniu.com/spocktest/spock-backend:1.0.3",
      "package_file": "build service kodo package file",
      "timeout": 7200
    },
    {
      "type": "deploy",
      "namespace": "yaoshipu",
      "product_name": "spock-kube",
      "group_name": "spock-kube",
      "service_name": "spock-backend",
      "container_name": "spock-backend",
      "image": "same as previous build task value",
      "package_file": "same as previous build task value",
      "timeout": 600
    },
    {
      "type": "testing",
      "product_name": "spock-kube",
      "group_name": "spock-test",
      "service_name": "spock-backend-test",
      "container_name": "spock-backend-test",
      "threshold": 90,
      "command": "command to run test",
      "result_path": "test result path",
      "timeout": 3600
    },
    {
      "type": "distribute",
      "dist_host": "jumpbox",
      "package_file": "same as previous build task value",
      "timeout": 600
    },
    {
      "type": "jira",
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "pull_request_number": 123,
      "timeout": 600
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
