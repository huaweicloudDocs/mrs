# Shell客户端连接提示"authentication failed"<a name="mrs_03_0171"></a>

## 问题现象<a name="zh-cn_topic_0167275617_s4062da02d4d340ed9dbd38c42c5a7475"></a>

安全集群中，HiveServer服务正常的情况下，Shell客户端中执行beeline命令失败，界面提示“authentication failed”，如下：

```
Debug is true storeKey false useTicketCache true useKeyTab false doNotPrompt false ticketCache is null isInitiator true KeyTab is null refreshKrb5Config is false principal is null tryFirstPass is false useFirstPass is false storePass is false clearPass is false 
Acquire TGT from Cache 
Credentials are no longer valid 
Principal is null 
null credentials from Ticket Cache 
[Krb5LoginModule] authentication failed
No password provided
```

## 可能原因<a name="zh-cn_topic_0167275617_sde58cdd386c74b8c940eb2114143b0a3"></a>

-   客户端用户没有进行安全认证
-   kerberos认证超期

## 解决方案<a name="zh-cn_topic_0167275617_sf8f53c018c784bab9ca84e6d32b5d35d"></a>

1.  登录Hive客户端所在节点。
2.  执行**source **_集群客户端安装目录_**/bigdata\_env**命令。

    可通过**klist**命令查看本地是否有有效票据，如下信息表明票据在16年12月24日14:11:42生效，将在16年12月25日14:11:40失效。在此期间可以使用该票据，其他时间则该票据无效。

    ```
    klist
    Ticket cache: FILE:/tmp/krb5cc_0
    Default principal: admin@HADOOP.COM
    Valid starting     Expires            Service principal
    12/24/16 14:11:42  12/25/16 14:11:40  krbtgt/HADOOP.COM@HADOOP.COM
    ```

3.  执行**kinit** _username_进行认证，然后再使用客户端。

