## 查找测试报告

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/itreport/pipelines/:pipelineName/id/:id/names/:testName
```

##### 请求参数

|参数|描述|
|---|---|
|pipelineName|testpipeline名称|
|id|taskid|
|testName|testname|


##### 正常返回

```json
{
  "PipelineName": "testpipeline",
  "PipelineTaskId": 3,
  "TestName": "test",
  "TestJobName": "test",
  "Created": 1505803134,
  "Error": "error message",
  "TestSuiteSummary": {
    "Tests": 1,
    "Failures": 1,
    "Skips": 1,
    "Time": 1.123
  }
}
```

##### 错误返回

```json
{
  "code":6401,
  "message":"get it report error",
  "description":"error details"
}
```