## 查询Pipeline

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/v2/pipelines/:name
```

##### 请求参数

无

##### 参数说明

无

##### 正常返回

```json
{
  "name": "test-pipeline",
  "description": "demo desc",
  "update_by": "yaoshipu",
  "update_time": 1506652697,
  "enabled": true,
  "schedule": "*/10 * * * * *",
  "sub_tasks": [
    {
      "branch": "dev",
      "commit_id": "456",
      "commit_message": "commit message",
      "image": "image full name",
      "package_file": "build service kodo package file",
      "pull_request_id": 1234,
      "repo_name": "aslan-platform",
      "repo_owner": "qbox",
      "timeout": 7200,
      "type": "build"
    },
    {
      "container_name": "spock-backend",
      "group_name": "spock-kube",
      "image": "same as previous build task value",
      "package_file": "same as previous build task value",
      "product_name": "spock-kube",
      "service_name": "spock-backend",
      "timeout": 500,
      "type": "deploy"
    },
    {
      "type": "testing",
      "test_image": "index.qiniu.com/spocktest/spock-tricorder:1.0.0",
      "test_job_name": "spock-test",
      "repo": "aslan-platform",
      "owner": "qbox",
      "branch": "develop",
      "threshold": 90,
      "script": "command to run test",
      "result_path": "test result path",
      "workspace": "/workspace",
      "timeout": 3600
    },
    {
      "dist_host": "jumpbox",
      "timeout": 600,
      "type": "distribute"
    },
    {
      "timeout": 600,
      "type": "jira"
    }
  ]
}
```	

##### 错误返回
