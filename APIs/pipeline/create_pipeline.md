## 创建Pipeline

#### 注意事项

- 需要`admin`权限

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
      "bin": "spock-backend",
      "timeout": 7200
    },
    {
      "type": "deploy",
      "namespace": "yaoshipu",
      "product_name": "spock-kube",
      "group_name": "spock-kube",
      "service_name": "spock-backend",
      "container_name": "spock-backend",
      "timeout": 600
    },
    {
      "type": "testing",
      "test_image": "index.qiniu.com/spocktest/spock-tricorder:1.0.0",
      "test_job_name": "spock-test",
      "repo": "aslan-platform",
      "owner": "qbox",
      "branch": "develop",
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
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "timeout": 600
    }
  ]
}
```

##### 参数说明

|参数|说明|
|---|---|
|timeout|任务超时时间, 单位秒|
|test_job_name|单个用户唯一|

##### 正常返回

```
200 OK
```

##### 错误返回
