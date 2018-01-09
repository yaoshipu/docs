## 下载测试报告

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/itreport/jobs/:testJobName
```

##### 请求参数

|参数|描述|
|---|---|
|testJobName|":pipelineName-:taskid-:testName"|

##### 正常返回

```json
{
    "Tests": 1,
    "Failures": 1,
    "Skips": 1,
    "Time": 1.123,
    TestCases:[
        {
            "Name": "test",
            "ClassName": "qqq",
            "Failure": "failed",
            "Skipped": "skipped",
            "Time": 1.123
        }    
    ]
}
```

##### 错误返回
