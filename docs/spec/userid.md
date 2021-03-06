# 用户身份与设备身份

## 用户身份

身份凭证是用户的唯一标识，回答 “我是谁” 这个最为基础的哲学问题。

在身份设计中，遵循以下原则：

1. 设备就是身份。
2. 实名以后（绑定手机号），手机号的所有权即身份。

在具体的技术实现中，身份对应到存储在手机上的一对2048b的高强度RSA密钥。

## 设备身份

除了用户身份，用户的每个设备还拥有一个设备身份，也是一对2048bit的高强度RSA密钥，它的特殊之处在于：

* 每个设备均有一个属于自己唯一的身份证书。
* 设备身份的RSA密钥，永远只存储在本地，不会以任何形式传递到手机之外。
    * 手机被黑（比如插在了别人的电脑被读取文件）除外。
* 设备密钥，最终承担绝密消息加解密的责任。

## 删除身份

* 点击个人帧 - 删除身份，本机的身份便会永久清除。删除本机身份，会一起删除本机身份对应的相关数据：
    * 用户身份
    * 设备身份
    * 本机的聊天记录、站点列表、各类缓存等。
