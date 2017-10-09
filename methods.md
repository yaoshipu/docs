# 1. 模板管理接口

管理产品模板，管理产品线之间的依赖关系，产品线内服务的启动顺序。

## 创建产品模板

#### 注意事项

* 需要`admin`权限
* 产品模板依赖次序在`groups`里描述
* 产品模板依赖服务组,需要调用创建服务组模板预先创建

#### 请求

```
POST /api/templates/products
```

##### 请求参数

```
Content-Type: application/json
```

```json
{
  "product_name": "product-X",
  "groups": [
    "group-A", "group-B"
  ],
  "enabled": true
}
```

##### 参数说明

`product_name`  产品名称，全局唯一
`groups`  产品依赖服务组，服务组按配置的先后顺序启动
`enabled`  是否启用模版, 暂时没有使用

##### 请求返回
```
200 OK
```
##### 错误信息

```json
{
  "code":6100,
  "description":"empty product name",  
  "message":"Create Template Error"
}
```

## 更新产品模板

