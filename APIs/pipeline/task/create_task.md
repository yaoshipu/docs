## 创建任务

#### 注意事项

* 需要`user`权限
* image格式

  * 格式1: index.qiniu.com/spocktest/spock-backend:20171010142156-develop
  * 格式2: index.qiniu.com/spocktest/spock-backend:20171010142156-pr123
  * spock-backend 为二进制或者服务名称
  * 20171010142156 为时间戳精确到秒
  * develop 为分支名称
  * pr123 为Git PR

* package\_file 格式

  * spock-backend-20171010142156-develop.tar.gz
  * spock-backend-20171010142156-pr123.tar.gz

#### 请求

```
POST /api/tasks
```

##### 请求参数

```json
{
  "type": "pipeline",
  "pipeline_name": "demo-pipeline",
  "info": {
    "product_name": "spock-kube",
    "group_name": "spock-kube",
    "service_name": "spock-backend",
    "container_name": "spock-backend"
  },
  "sub_tasks": [
    {
      "type": "buildv2",
      "enabled": true,
      "build_os": "trusty",
      "job_ctx": {
        "clean_workspace": false,
        "scripts": "set -e
          printenv
          go version
          export PKG_DIR=$WORKSPACE/src/github.com/qbox/aslan-platform/_package
          echo $PKG_DIR
          mkdir -p $PKG_DIR
          export GOPATH=$WORKSPACE
          cd $WORKSPACE/src/github.com/qbox/aslan-platform
          make deps-cache clean-spock build-spock-net
          make depinstall-spock-portal build-spock-portal
          cd spock/cmd/spock
          docker build --rm -t $IMAGE -f Dockerfile .
          docker push $IMAGE
          cp ./spock $PKG_DIR
          tar -czvf $DIST_DIR/$PKG_FILE $PKG_DIR",
        "envs": [
          {"key":"TEST_ENV", "value":"ABC", "is_credential": true }
        ],
        "package_file": "spock-backend-test-0105-2.tar.gz",
        "image": "index.qiniu.com/spocktest/spock-backend-test:01052",
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
      "install_items": [
        {
          "name": "go",
          "version": "1.8.3"
        },
        {
          "name": "glide",
          "version": "latest"
        },
        {
          "name": "node",
          "version": "6.11.2"
        },
        {
          "name": "yarn",
          "version": "latest"
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
      "image": "same as previous build task value",
      "package_file": "same as previous build task value",
      "timeout": 600
    },
    {
      "type": "floy_deploy",
      "service_name": "io",
      "package_file": "IO.2018-03-05-17-40-22.tar.gz",
      "env": "dev"
    },
    {
    "type": "testingv2",
    "enabled": true,
    "test_name": "test",
    "build_os": "trusty",
    "job_ctx": {
        "test_threshold":100,
          "test_result_path":"/dora-cloud/test/reporters",
        "clean_workspace": false,
        "scripts": "#!/bin/bash
                  set -e
                  export PATH=$PATH:/go/bin
                  cd /workspace/dora-cloud/test
                  source env.sh
                  ./startup.sh
                  export TEST_ENV=product
                  export TEST_ZONE=z0
                  export COMPARE_LEVEL=0
                  echo $USER_NAME
                  make dependency
                  cd /workspace/dora-cloud/test
                  #make testsmoke
                  for p in pfop;
                  do 
                    cd  /workspace/dora-cloud/test/src/qtest.com/fop/$p
                    ginkgo -p -keepGoing=true
                  cd -
                  done
                  echo $?",
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

| key | value |
| --- | --- |
| pipeline\_name | 工作流名称 |
| repo\_name | 代码库名称 |
| repo\_owner | 代码库所有人 |
| branch | 代码编译分支 如果提供了pull\_request\_number, branch会被忽略 |
| pull\_request\_number | pull request number |
| commit\_id | commitID 如果是提交PR, 则需要提供 |
| install\_ctx | 全部可选 |
| build\_os | precise, trusty, xential |

##### 正常返回

```
200 OK
```

##### 错误返回



