# /tmp目录权限不对导致DBserver实例状态一直处于Restoring<a name="mrs_03_0074"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274625_sd64242caa665405798481482f49ab0ee"></a>

DBServer实例状态一直是Restoring状态，重启之后仍然不恢复。

## 原因分析<a name="zh-cn_topic_0167274625_s4871ca6d7a6b47b1a0f8266b84631f32"></a>

1.  查看“/var/log/Bigdata/dbservice/healthCheck/dbservice\_processCheck.log“，可以看到gaussdb异常。

    **图 1**  gaussdb异常<a name="zh-cn_topic_0167274625_fig52931642145312"></a>  
    ![](figures/gaussdb异常.png "gaussdb异常")

2.  检查发现“/tmp“权限不对。

    **图 2**  /tmp权限<a name="zh-cn_topic_0167274625_fig11159145810531"></a>  
    ![](figures/tmp权限.png "tmp权限")


## 解决办法<a name="zh-cn_topic_0167274625_section4599086017025"></a>

1.  修改/tmp的权限。

    **chmod 1777 /tmp**

2.  等待实例状态恢复。

