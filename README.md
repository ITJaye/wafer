[新wafer]支持微信小程序登陆授权新要求
=========================================


微信小程序新的登陆方式修改为：
用户每次进入小程序，通过wx. checkSession检查会话状态，调用wx.login获取code发送到服务端，服务端通过code换取用户的openId、unionId和session_key，此时注册用户信息，给定默认的头像和昵称，达到用户注册的目的，并给客户端返回用户的userInfo
1.小程序端需要用户头像和昵称的时候，小程序端布置【获取用户头像昵称按钮】，用户点击时通过wx.getUserInfo带上withCredentials:true 获取 encryptedData 和 iv 上传到服务端进行信息解密，解密后得到用户的userInfo，此时可以更新数据库中用户的信息。


阅读 [Wiki](https://github.com/tencentyun/wafer/wiki) 文档了解 Wafer 提供的服务、部署方法、架构设计以及实现细节。

## 开发者资源索引

* 客户端
  - [SDK](https://github.com/ITJaye/wafer-client-sdk) - 客户端增强 SDK 源码
* 业务服务器
  - [PHP SDK](https://github.com/ITJaye/wafer-php-server-sdk) - PHP 解决方案的 SDK 源码
* 会话服务器
  - [Session Server](https://github.com/ITJaye/wafer-session-server) - PHP 会话服务器的源码
* 微信小程序文档
  
  - 新登陆授权要求 [小程序授权登陆新要求](https://developers.weixin.qq.com/blogdetail?action=get_post_info&lang=zh_CN&token=&docid=c45683ebfa39ce8fe71def0631fad26b)
  - 原始项目 [Wafer](https://github.com/tencentyun/wafer)
* 部署方法
  - [自行部署 Wafer 的一点心得](https://github.com/tencentyun/wafer/issues/8) - @ITJaye

