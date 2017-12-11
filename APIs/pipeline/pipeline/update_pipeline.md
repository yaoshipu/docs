## 更新Pipeline

#### 注意事项

- 需要admin权限
- pipeline名字不能修改

#### 请求

```
PUT /api/v2/pipelines/:name
```

##### 请求参数

```json
{
  "description": "demo desc",
  "enabled": true,
  "schedule": "*/10 * * * * *",
  "sub_tasks": [
    {
      "type": "build",
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "branch": "dev",
      "pull_request_id": 1234,
      "commit_id": "456",
      "bin": "spock-backend",
      "image": "image full name",
      "package_file": "build service kodo package file",
      "dependency_builds": [
        {
          "repo_owner": "qbox",
          "repo_name": "aslan-platform",
          "branch": "master",
          "pull_request_number": 11
        }
      ]
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
      "timeout": 500
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

详见`创建Pipeline`

##### 正常返回

```
200 OK
```

##### 错误返回