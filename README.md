# 51token-sdk

在51token app 中打开的 web网页可以直接使用注入的对象发起交易,
进去dapp时，需要指定某个链

## token51.isConnected()
    说明：检查是否在51token中打开该网页
    参数：无
    方法类型： 同步
    返回值：Boolean 
    eg:
        true 代表接入51token成功
        false 代表接入51token失败


## token51.getIdentity()
    说明：获取当前用户
    参数：无
    方法类型： 异步
    参数：无
    返回值：
```json    
{
    "accounts":[
        {
            "authority":"active",
            "name":"xxxxxxxxxxxx",
            "blockchain":"eos"
        }
    ]
}
```

##  token51.forgetIdentity()
    说明：切换钱包
    方法类型： 异步
    参数：无
    返回值：切换后的钱包信息
```json    
{
    "accounts":[
        {
            "authority":"active",
            "name":"xxxxxxxxxxxx",
            "blockchain":"eos"
        }
    ]
}
```

## token51.pushActions(data)
	说明：发起交易
    方法类型： 异步
    参数：
        data: Object(交易报文)
    返回值：
        Object:
        {
            "result": true/false,
            "data":"成功返回信息",
            "error":"错误返回信息"
        }

输入交易报文示例
```json
{
    "actions": [
        {
            "account": "合约账户",
            "name": "transfer",
            "authorization": [
                {
                    "actor": "用户",
                    "permission": "active"
                }
            ],
            "data": {
                "from": "用户",
                "to": "用户",
                "quantity": "0.0001 代币标志",
                "memo": ""
            }
        }
    ]
}
```

# 测试

可以在51token中直接打开如下页面进行测试：

https://51token.github.io/51token-sdk/eos

https://51token.github.io/51token-sdk/enu

https://51token.github.io/51token-sdk/fibos