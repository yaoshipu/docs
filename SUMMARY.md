# Summary

## Overview

* [Spock API](README.md)

## API接口文档

## 1. 模板管理接口

* 产品模板
  * [创建产品模板](APIs/template/product/create_product_tmpl.md)
  * [更新产品模板](APIs/template/product/update_product_tmpl.md)
  * [列出产品模板](APIs/template/product/list_product_tmpl.md)
  * [查询产品模板](APIs/template/product/get_product_tmpl.md)
  * [删除产品模板](APIs/template/product/delete_product_tmpl.md)
* 服务组模板
  * [创建服务组模板](APIs/template/group/create_group_tmpl.md)
  * [更新服务组模板](APIs/template/group/update_group_tmpl.md)
  * [列出服务组模板](APIs/template/group/list_group_tmpl.md)
  * [查询服务组模板](APIs/template/group/get_group_tmpl.md)
  * [删除服务组模板](APIs/template/group/delete_group_tmpl.md)
* 服务模板
  * [创建服务模板](APIs/template/service/create_service_tmpl.md)
  * [列出服务模板名称](APIs/template/service/list_service_tmpl.md)
  * [查询服务模板](APIs/template/service/get_service_tmpl.md)
  * [删除服务模板](APIs/template/service/delete_service_tmpl.md)
  * [检查服务模板Yaml](APIs/template/service/validate_service_yaml.md)
* 配置模板
  * [创建配置模板](APIs/template/config/create_config_tmpl.md)
  * [列出配置模板](APIs/template/config/list_config_tmpl.md)
  * [查询配置模板](APIs/template/config/get_config_tmpl.md)
  * [删除配置模板](APIs/template/config/delete_config_tmpl.md)
  * [修改配置模板名称](APIs/template/config/update_config_tmpl_name.md)

## 2. 产品管理接口

* 产品管理
  * [创建产品](APIs/product/product/create_product.md)
  * [更新产品](APIs/product/product/update_product.md)
  * [列出产品](APIs/product/product/list_product.md)
  * [删除产品](APIs/product/product/delete_product.md)
  * [列出产品更新信息](APIs/product/product/list_product_revision.md)
* 服务组管理
  * [列出服务组](APIs/product/group/list_group.md)
  * [查询服务组](APIs/product/group/get_group.md)
* 服务管理
  * [查询服务](APIs/product/service/get_service.md)
  * [重启服务](APIs/product/service/restart_service.md)
  * [更新容器镜像](APIs/product/service/update_container_image.md)
  * [扩容服务](APIs/product/service/scale_service.md)
  * [删除服务Pod](APIs/product/service/delete_pod.md)
  * [列出服务Pods](APIs/product/service/list_service_pods.md)
  * [列出镜像](APIs/product/service/list_image.md)
* 配置管理
  * [列出配置](APIs/product/configmap/list_configmaps.md)
  * [更新配置](APIs/product/configmap/update_configmap.md)

## 3. Pipeline管理接口

* Pipeline管理
  * [创建Pipeline](APIs/pipeline/pipeline/create_pipeline.md)
  * [更新Pipeline](APIs/pipeline/pipeline/update_pipeline.md)
  * [列出Pipeline](APIs/pipeline/pipeline/list_pipelines.md)
  * [查询Pipeline](APIs/pipeline/pipeline/get_pipeline.md)
  * [删除Pipeline](APIs/pipeline/pipeline/delete_pipeline.md)
  * [检查服务容器](APIs/pipeline/get_service_container.md)
  * [检查测试Job](APIs/pipeline/validate_test_job.md)
  * [创建关注Pipeline](APIs/pipeline/pipeline/create_favorite_pipeline.md)
  * [列出关注Pipeline](APIs/pipeline/pipeline/list_favorite_pipeline.md)
  * [删除关注Pipeline](APIs/pipeline/pipeline/delete_favorite_pipeline.md)
* 任务管理
  * [创建任务](APIs/pipeline/task/create_task.md)
  * [查询任务](APIs/pipeline/task/get_task.md)
  * [列出等待中任务](APIs/pipeline/task/list_pending_task.md)
  * [列出运行中任务](APIs/pipeline/task/list_running_task.md)
  * [取消等待中任务](APIs/pipeline/task/cancel_pending_task.md)
  * [取消运行中任务](APIs/pipeline/task/cancel_running_task.md)
  * [重启任务](APIs/pipeline/task/restart_task.md)
  * [列出任务](APIs/pipeline/task/list_task.md)
  * [列出任务状态](APIs/pipeline/task/list_task_status.md)
  * [列出Agent状态](APIs/pipeline/task/list_agent_status.md)
* 测试管理
  * [查找测试报告](APIs/pipeline/itreport/find_itreport.md)
  * [下载测试报告](APIs/pipeline/itreport/download_itreport.md)

## 4. 日志管理接口

* 任务日志
  * [测试任务日志](APIs/log/test_job_logs.md)
  * [测试任务实时日志](APIs/log/test_job_logs_ws.md)
  * [构建任务日志](APIs/log/build_job_logs.md)
  * [构建任务实时日志](APIs/log/build_job_logs_ws.md)
* 服务日志
  * [服务历史日志](APIs/log/container_log.md)
  * [服务实时日志](APIs/log/container_log_ws.md)

## 5. 统计信息管理接口

* 工程仪表盘
* [创建insights config](APIs/insights/create_config.md)
* [列出insights config](APIs/insights/list_config.md)
* [更新insights config](APIs/insights/update_config.md)
* [删除insights config](APIs/insights/delete_config.md)
* [获取项目进度insights](APIs/insights/get_project_insights.md)
* [获取质量现状insights](APIs/insights/get_quality_insights.md)
* [获取工作流insights](APIs/insights/get_pipeline_insights.md)
* [获取团队统计信息](APIs/insights/get_team_stats.md)
* [获取产品统计信息](APIs/insights/get_product_stats.md)
* [获取jiraproject列表](APIs/jira/get_jira_project.md)
* [获取jiraboard列表](APIs/jira/get_jira_board.md)


* Spock使用信息

## 6. 系统管理接口

* 通知管理
  * [创建通知](APIs/system/notification/create_notify.md)
  * [拉取消息](APIs/system/notification/pull_notify.md)
  * [拉取系统通知](APIs/system/notification/pull_announcement.md)
  * [拉取全部系统通知](APIs/system/notification/pull_all_announcement.md)
  * [通知状态设置已读](APIs/system/notification/read_notify.md)
  * [更新通知](APIs/system/notification/update_notify.md)
  * [通知删除](APIs/system/notification/notify_deletebyid.md)
  * [创建关注](APIs/system/notification/create_subscribe.md)
  * [更新关注](APIs/system/notification/update_subscribe.md)
  * [获得关注列表](APIs/system/notification/list_subscribe.md)
  * [取消关注](APIs/system/notification/delete_subscribe.md)
* 安装管理脚本
  * [创建脚本](APIs/system/installscript/create_install.md)
  * [列出脚本](APIs/system/installscript/list_install.md)
  * [获取脚本](APIs/system/installscript/get_install.md)
  * [更新脚本](APIs/system/installscript/update_install.md)
  * [删除脚本](APIs/system/installscript/delete_install.md)
* 维护管理
  * [设置开始维护](APIs/system/maintenance/start.md)
  * [设置结束维护](APIs/system/maintenance/end.md)
  * [查询维护状态](APIs/system/maintenance/status.md)
  * [查询禁止访问URL列表](APIs/system/maintenance/blocked_list.md)
* 用户管理
  * [获取用户kube配置](APIs/system/user/get_user_kubeconfig.md)
* 仓库管理
  * [创建仓库 webhook](APIs/system/webhook/create_hook.md)
  * [删除仓库 webhook](APIs/system/webhook/delete_hook.md)
  * [列出仓库 webhook](APIs/system/webhook/list_hooks.md)

