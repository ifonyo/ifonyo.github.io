---
layout: post
title: 项目后台接口说明文档
---
# 总体设计
	android和ios跟后台交互api使用http协议，统一调用url为http://server/project/api，将param参数以json字符串的方式传入post调用，返回html/json形式的数据。
	
# 接口

## 登录
	短信认证
	* request
	> {"action":"auth","uid":"手机号码"}
	* resonse
	登录
	* request
	> {"action":"login","uid":"手机号码"
	* response
	> {"result":0,"message":"success"}
	注册
	* request
	> {"action":"reg","uid":"手机号码","invite":"推荐人代码"}
	* response
	> {"result":0,"message":"success"}
	注销
	
## 用户信息
	获取用户信息
	* request
	* response
	更新用户基本信息
	* request
	* response
	更新用户头像
	* request
	* response
	
## 列表
	获取列表
	* request
	* response
	获取列表详细
	* request
	* response
	
## 订单

## 支付
