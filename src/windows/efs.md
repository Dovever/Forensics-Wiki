---
title: EFS加密与解密
icon: unlock
order: 2
sidebar: structure
pageview: true
---

## 加密方法

在资源管理器中在要加密的对象上右键——属性——高级——加密内容以便保护数据（不需要输入密码）

EFS加密是用账号本人的证书进行加密解密，所以，如果重做了系统，没有证书将无法解密。

### 解决办法

导出证书：CertMgr.msc命令，打开证书管理工具，在个人证书下找到加 密文件系统的证书，右键-所有任务-导出，后缀名cer。

![null](https://bu.dusays.com/2023/07/25/64bff0971fdd6.png)
重做系统后，把该证书导入，即可打开被EFS加密的对象。操作方法跟导出类似。