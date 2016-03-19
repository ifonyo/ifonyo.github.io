---
layout: post
title: 项目后台接口说明文档
---
# 总体设计
	android和ios跟后台交互api使用http协议，统一调用url为http://server/project/api，将param参数以json字符串的方式传入post调用，返回html/json形式的数据。
# API接口列表
## 登录相关
	短信认证
	登录
	注册
	注销
## 用户信息相关
	获取用户信息
	更新用户基本信息
	更新用户头像
## 列表相关	
	获取列表
	获取列表详细
## 订单相关
## 支付相关
