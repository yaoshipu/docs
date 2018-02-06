## 服务历史日志

#### 注意事项

- 需要`user`权限

#### 请求

```
/api/logs/container
```
##### 请求参数

{
  "query": "s_product:spock-prod AND s_group:spock-prod AND s_service:spock-backend AND log:MR0e5R8NINOdWhAV",
  "start_time": 1517673600000,
  "end_time": 1517820869361
}

##### 参数说明

|参数|说明|
|---|---|
|namespace|服务所在用户|
|s_product|产品名称|
|s_group|服务组名称|
|s_service|服务名称|
|start_time|日志开始时间，单位毫秒|
|end_time|日志结束时间，单位毫秒|

##### 正常返回

```json
{
  "data": [
    {
      "timestamp": "2018-02-05T06:40:36.605287Z",
      "namespace": "spockadmin",
      "log": "[GIN] [MR0e5R8NINOdWhAV] [Completed]\t2018/02/05 - 06:40:36 |\u001b[97;41m 500 \u001b[0m| 2m8.282595012s | 222.73.202.226 | \u001b[97;46m POST \u001b[0m|\t /api/products/portal-v4\n"
    }
  ],
  "is_end": true
}
```

循环调用API直到is_end=true停止

##### 错误返回
