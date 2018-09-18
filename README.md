# 51token-sdk

通过引用 51token.js 可以使用 _51token对象来进行调用。

异步方法可以传入callback，不传入的话返回值是Promise。异步方法的返回值是指回调函数的输入。

## Common

通用方法

### _51token.isConnected()
    说明：检查是否在51token中打开该网页
    参数：无
    方法类型： 同步
    返回值：Boolean 
    eg:
        true 代表接入51token成功
        false 代表接入51token失败


### _51token.getCurrentWallet()
    说明：获取当前用户
    参数：无
    方法类型： 同步
    返回值：
    （1）null 未导入任何钱包
    （2）Object
        eg:{
            "result": true/false,
            "data":{
                "name":"账户名",
                "blockchain":"EOS/ENU/FO"
            }
        }

### _51token.getAllWallets(callback)
    说明：获取所有钱包
    方法类型： 异步
    参数：
        callback: 回调函数
    返回值：
        Object:
        eg:[
            {
                "name":"钱包名",
                "blockchain":"EOS/ENU/FO"
            },
            {
                "name":"钱包名",
                "blockchain":"EOS/ENU/FO"
            },
            {
                "name":"钱包名",
                "blockchain":"EOS/ENU/FO"
            },
            {
                "name":"钱包名",
                "blockchain":"EOS/ENU/FO"
            }
        ]

## eos

###  _51token.eos.chooseWallet(callback)
    说明：切换钱包
    方法类型： 异步
    参数：
        callback: 回调函数
    返回值：
        Object
        eg:{
            "result": true/false,
            "data":{
                "name":"账户名",
                "blockchain":"EOS/ENU/FO"
            }
        }

### _51token.eos.generateKeyPair(callback)
    说明：生成公私钥
    方法类型： 异步
    参数：
        callback: 回调函数
    返回值：
        Object:
        eg:{
            "result": true/false,
            "data":{
                "PublicKey":"公钥",
                "PrivateKey":":"私钥"
            }

### _51token.eos.transaction(data,callback)
	说明：发起交易
    方法类型： 异步
    参数：
        data: Object(交易报文),
        callback: 回调函数
    返回值：
        Object:
        eg:{
            "result": true/false,
            "data":"成功返回信息",
            "error":"错误返回信息"
        }

交易报文示例
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

## enu

使用方法同eos

- _51token.enu.chooseWallet(callback)
- _51token.enu.generateKeyPair(callback)
- _51token.enu.transaction(data,callback)

## fibos

使用方法同eos

- _51token.fibos.chooseWallet(callback)
- _51token.fibos.generateKeyPair(callback)
- _51token.fibos.transaction(data,callback)