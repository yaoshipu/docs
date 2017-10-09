## 创建Pipeline

#### 注意事项

- 需要admin权限

#### 请求

```
POST /api/v2/pipelines
```

##### 请求参数


```json
{
  "name": "test-pipeline",
  "description": "demo desc",
  "enabled": true,
  "schedule": "*/10 * * * * *",
  "sub_tasks": [
    {
      "type": "build",
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "branch": "dev",
      "pull_request_id": 123,
      "commit_id": "456",
      "commit_message": "commit message",
      "image": "image full name",
      "package_file": "build service kodo package file",
      "timeout": 7200
    },
    {
      "type": "deploy",
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
      "timeout": 600
    },
    {
      "type": "jira",
      "timeout": 600
    }
  ]
}
```

##### 参数说明

无

##### 正常返回

```
200 OK
```

##### 错误返回
