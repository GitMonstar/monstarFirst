##支付宝_Ios
###一、登录支付宝账号创建应用
	1. bundleID
	2. Icon(320*320)
	3. 填写开发者网关、公匙
	4. 应用通过审核后，才能申请移动支付
###二、生成公匙和私匙
	RSA密钥生成命令
	生成RSA私钥
	openssl>genrsa -out rsa_private_key.pem 1024
	生成RSA公钥
	openssl>rsa -in rsa_private_key.pem -pubout -out rsa_public_key.pem
	将RSA私钥转换成PKCS8格式
	openssl>pkcs8 -topk8 -inform PEM -in rsa_private_key.pem -outform PEM -nocrypt

	注意：“>”符号后面的才是需要输入的命令。
###三、开发发者网关说明
	开发者网关可以向支付宝网关发送POST消息，主动调用支付宝OpenAPI（notify_url）
###四、开发需要的
	1. partner 合作者身份ID
	2. out_trade_no 网站唯一订单号
	3. 卖家支付宝账号
	4. it_b_pay 未付款交易的超时时间 
