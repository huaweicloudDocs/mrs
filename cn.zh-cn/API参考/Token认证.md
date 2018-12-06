# Token认证<a name="ZH-CN_TOPIC_0109962609"></a>

## 应用场景<a name="s2bef0514f3c8406b9d58133b9bfae00b"></a>

当您使用Token认证方式完成认证鉴权时，需要获取用户Token并在调用接口时增加“X-Auth-Token”到业务接口请求消息头中。

本节介绍如何调用接口完成Token认证。

## 调用接口步骤<a name="s4a955e2c0b264875b1a9d95bee7a2c12"></a>

1.  发送“POST https://_**IAM的Endpoint**_/v3/auth/tokens”，获取IAM的Endpoint及消息体中的区域名称，请参见[终端节点及区域说明](http://developer.huaweicloud.com/dev/endpoint)。

    请求内容示例如下：

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >下面示例代码中的斜体字需要替换为实际内容，详情请参考《统一身份认证服务API参考》。  

    ```
    {
      "auth": {
        "identity": {
          "methods": [
            "password"
          ],
          "password": {
            "user": {
              "name": "username",
              "password": "password",
              "domain": {
                "name": "domainname"
              }
            }
          }
        },
        "scope": {
          "project": {
            "name": "cn-north-1" //假设区域名称是“cn-north-1”
            
          }
        }
      }
    }
    ```

2.  <a name="l685d589e421c47db956ef323e25b2346"></a>获取Token，请参考《统一身份认证服务API参考》的“获取用户Token”章节。请求响应成功后在响应消息头中包含的“X-Subject-Token”的值即为Token值。
3.  调用业务接口，在请求消息头中增加“X-Auth-Token”，“X-Auth-Token”的取值为[2](#l685d589e421c47db956ef323e25b2346)中获取的Token。

