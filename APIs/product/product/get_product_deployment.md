## 获取产品部署环境状态

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/validate/product/:productName/user/:userName
```

##### 参数说明

|参数|说明|
|---|---|
|status|是否可部署|
|msg|详细信息|



##### 正常返回

```
{
    "status": true,
    "msg": "对应环境可部署"
}
```

##### 错误返回
