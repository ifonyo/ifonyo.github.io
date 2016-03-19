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
	eg. {"action":"auth","uid":"130xxxxxxxx"}
	* resonse
	登录
	* request
	> {"action":"login","uid":"手机号码","code":"验证码"}
	eg. {"action":"login","uid":"130xxxxxxxx","code":"6xxxxx"}
	* response
	> {"result":返回码,"message":"错误信息"}
	eg. {"result":0,"message":"success"}
	注册
	* request
	> {"action":"reg","uid":"手机号码","code":"验证码","invite":"推荐人代码"}
	eg. {"action":"reg","uid":"130xxxxxxxx","code":"6xxxxx","invite":"xxxxxx"}
	* response
	> {"result":返回码,"message":"错误信息"}
	eg. {"result":0,"message":"success"}
	注销
	* request
	> {"action":"logout"}
	
## 用户信息
	获取用户信息
	* request
	> {"action":"queryuser"}
	* response
	> {"result":"返回码","message":"错误信息","uid":"手机号码","name":"姓名","nickname":"昵称","sex":"性别","age":年龄,"identity":"身份证号","address":"家庭住址"}
	eg. {"result":0,"message":"success","uid":"130xxxxxxxx","name":"js","nickname":"js","sex":"男","age":18,"identity":"xxxxxxxxxxxxxxxxxx","address":"..."}
	更新用户信息
	* request
	> {"action":"updateuser","name":"姓名","nickname":"昵称","sex":"性别","age":年龄,"identity":"身份证号","address":"家庭住址"}
	eg. {"action":"updateuser","name":"js","nickname":"js","sex":"男","age":18,"identity":"xxxxxxxxxxxxxxxxxx","address":"..."}
	* response
	> {"result":"返回码","message":"错误信息"}
	eg. {"result":0,"message":"success"}
	获取用户头像
	* request
	> {"action":"queryicon"}
	* response
	> {"result":"返回码","message":"错误信息","data":"图片的base64编码"}
	eg. {"result":0,"message":"success","data":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"}
	更新用户头像
	* request
	> {"action":"updateicon","data":"图片的base64编码"}
	eg. {"action":"updateicon","data":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"}
	* response
	> {"result":"返回码","message":"错误信息"}
	eg. {"result":0,"message":"success"}
	
## 列表
	获取列表
	* request
	> {"action":"querylist"}
	* response
	> {"result":"返回码","message":"错误信息","itemidlist":itemID列表}
	eg. {"result":0,"message":"success","itemidlist":[1,2,3,4,5]}
	获取列表详细
	* request
	> {"action":"queryitem","itemid":itemID}
	eg. {"action":"queryitem","itemid":1}
	* response
	> {"result":"返回码","message":"错误信息","itemname":"item名称","itemdesc":"item描述","itemprice":价格,"buycount":已申购数量,"imgdata":"图片base64编码"}
	eg. {"result":0,"message":"success","itemname":"...","itemdesc":"...","itemprice":199,"buycount":200,"imgdata":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"}
	
## 订单

## 支付
