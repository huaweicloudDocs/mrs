# 使用Flume客户端加密工具<a name="ZH-CN_TOPIC_0069282320"></a>

## 操作场景<a name="zh-cn_topic_0069042429_section6298670017199"></a>

安装Flume客户端后，配置文件的部分参数可能需要填写加密的字符，Flume客户端中提供了加密工具。

## 前提条件<a name="zh-cn_topic_0069042429_section39918060171959"></a>

已完成客户端安装。

## 操作步骤<a name="zh-cn_topic_0069042429_section17297599172010"></a>

1.  登录安装Flume客户端的节点，并切换到客户端安装目录。例如“/opt/FlumeClient“。
2.  切换到以下目录

    **cd fusioninsight-flume-1.6.0/bin**

3.  执行以下命令，加密原始信息：

    **./genPwFile.sh**

    输入两次待加密信息。

4.  执行以下命令，查看加密后的信息：

    **cat password.property**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果加密参数是用于Flume Server，那么需要到相应的Flume Server所在节点执行加密。加密脚本路径为“/opt/Bigdata/FusionInsight/FusionInsight-Flume-1.6.0/flume/bin/genPwFile.sh“，需要使用omm用户执行加密脚本进行加密。  


