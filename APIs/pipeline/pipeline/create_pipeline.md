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
  "schedules": [
    {
      "number": 1,
      "frequency": "day",
      "time": "10:15",
      "enabled": true
    },
    {
      "number": 30,
      "frequency": "minutes",
      "time": "",
      "enabled": true
    }
  ],
  "sub_tasks": [
    {
      "type": "build",
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "branch": "dev",
      "bin": "spock-backend",
      "timeout": 7200,
      "dependency_builds": [
        {
          "repo_owner": "qbox",
          "repo_name": "aslan-platform",
          "branch": "master"
        }
      ]
    },
    {
      "type": "build.v2",
      "enabled": true,
      "job_ctx": {
        "scripts": [
          "set -e",
          "printenv",
          "export GOPATH=$WORKSPACE",
          "cd $WORKSPACE/src/github.com/qbox/aslan-platform",
          "#make deps-cache clean-spock build-spock-net",
          "#make depinstall-spock-portal build-spock-portal",
          "cd spock/cmd/spock",
          "#docker build --rm -t $IMAGE -f Dockerfile .",
          "#docker push $IMAGE",
          "mkdir -p $DIST_DIR/_package && cp spock $DIST_DIR/_package"
        ],
        "envs": [
          "TEST_ENV=ABC"
        ],
        "package_file": "spock-backend-test-1230-6.tar.gz",
        "package_dir": "/workspace/pipeline_name/packege_path",
        "TestThreshold": 100,
        "TestResultPath", "",
        "TestJobName", "",
        "image": "index.qiniu.com/spocktest/buildv2:test",
        "builds": [
          {
            "repo_owner": "qbox",
            "repo_name": "aslan-platform",
            "branch": "develop",
            "pr": 0,
            "commit_id": "",
            "commit_message": "",
            "checkout_path": "/src/github.com/qbox",
            "remote_name": "origin",
            "submodules": false
          }
        ]
      },
      "install_ctx": {
        "go_version": "1.8.3", 
        "node_version": "6.11.2",
        "yarn": true,
        "glide": true,
        "bower": false,
        "ginkgo": false,
        "node_gyp": false,
        "phantomjs": false
      }
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
      "script": "command to run test",
      "result_path": "test result path",
      "workspace": "/workspace",
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
|schedule.number|minutes区间最小值为30,其他>0|
|schedule.frequency|任务周期，支持 minutes, hour, hours, day, days, monday -> sunday|
|schedule.time|任务运行时间，可以和 day, days, monday -> sunday 配合使用|
|install_ctx| 全部可选 |

##### 正常返回

```
200 OK
```

##### 错误返回
