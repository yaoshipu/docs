## 创建Pipeline

#### 注意事项

* 需要`admin`权限

#### 请求

```
POST /api/v2/pipelines
```

##### 请求参数

```json
{
  "name": "test-pipeline",         // 必填
  "description": "this is a desc", // 选填
  "enabled": true,                 // 必填
  "team": "ASLAN",                 // 必填
  "info": {                        // 选填
    "product_name": "spock-kube",
    "group_name": "spock-kube",
    "service_name": "spock-backend",
    "container_name": "spock-backend"
  },
  "schedules": [                   // 选填
    {
      "enabled": true,     // 必填
      "number": 1,         // 必填
      "frequency": "day",  // 必填
      "time": "10:15",     // 选填
      "max_failures": 3    // 选填
    },
    {
      "enabled": true
      "number": 30,
      "frequency": "minutes",
    }
  ],
  "hook": {                        // 选填
    "enabled": true,   // 必填
    "git_hooks": [     
      {
        "repo": "aslan-platform", // 必填
        "branch": "develop",      // 必填
        "events": [               // 必填
          "pull_request",        
          "push"
        ],
        "match_folders": [        // 选填
          "\"
        ]
      }
    ]
  },
  "sub_tasks": [                  // 必填
    {
      "type": "buildv2", // 必填
      "enabled": true,   // 必填
      "build_os": "trusty",
      "job_ctx": {
        "clean_workspace": false,
        "scripts": "set -e
          export GOPATH=$WORKSPACE
          export PKG_DIR=$WORKSPACE/src/github.com/qbox/aslan-platform/_package
          echo $PKG_DIR
          mkdir -p $PKG_DIR
          cd $WORKSPACE/src/github.com/qbox/aslan-platform
          mkdir -p $WORKSPACE/bin && export GOBIN=$WORKSPACE/bin
          make deps build-backend-net
          cd spock/cmd/spock
          docker build --rm -t $IMAGE -f Dockerfile .
          docker push $IMAGE
          cp ./spock $PKG_DIR/spock
          tar -czvf $DIST_DIR/$PKG_FILE $PKG_DIR",
        "envs": [
          {"key":"TEST_ENV", "value"="ABC", "is_credential": true }
        ],
        "upload_pkg" : true, # 决定是否上传到KODO
        "package_file": "spock-backend-20180222103427-develop.tar.gz",
        "image": "reg.qiniu.com/spock-release-candidates/spock-backend:20180222103427-develop",
        "builds": [
          {
            "repo_owner": "qbox",
            "repo_name": "aslan-platform",
            "branch": "develop",
            "pr": 0,
            "commit_id": "",
            "commit_message": "",
            "checkout_path": "src/github.com/qbox/aslan-platform",
            "remote_name": "",
            "submodules": false
          }
        ]
      },
      "install_items": [
        {
          "name": "go",
          "version": "1.8.3"
        },
        {
          "name": "glide",
          "version": ""
        }
      ]
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
      "type": "floy_deploy",
      "service_name":"io",
      "env": "dev",
      "timeout": 10
    },
    {
    "type": "testingv2",   // 必填
    "enabled": true,       // 必填
    "test_name": "test",
    "build_os": "trusty",
    "job_ctx": {
        "test_threshold": 100,
          "test_result_path":"/dora-cloud/test/reporters",
        "clean_workspace": false,
        "scripts": "your testing scripts",
    "envs": [],
    "builds": [
        {
            "repo_owner": "qbox",
            "repo_name": "dora-cloud",
            "branch": "develop",
            "pr": 0,
            "commit_id": "",
            "commit_message": "",
            "remote_name": "origin",
            "submodules": false
        }
    ]
    },
    "install_items": [
        {
          "name": "go",
          "version": "1.8.3"
        },
        {
          "name": "ginkgo",
          "version": "latest"
        }
      ]
    },
    {
      "type": "distribute",    // 必填
      "enabled": true,         // 必填
      "dist_host": "jumpbox",
      "timeout": 600
    },
    {
      "type": "jira",        // 必填
      "enabled": true,       // 必填
      "repo_owner": "qbox",
      "repo_name": "aslan-platform",
      "timeout": 600
    }
  ]
}
```

##### 参数说明

| 参数 | 说明 |
| --- | --- |
| timeout | 任务超时时间, 单位秒 |
| test\_job\_name | 单个用户唯一 |
| schedule.number | minutes区间最小值为30,其他&gt;0 |
| schedule.frequency | 任务周期，支持 minutes, hour, hours, day, days, monday -&gt; sunday |
| schedule.time | 任务运行时间，可以和 day, days, monday -&gt; sunday 配合使用 |
| install\_ctx | 全部可选 |
| build\_os | precise, trusty, xential |

##### 正常返回

```
200 OK
```

##### 错误返回



