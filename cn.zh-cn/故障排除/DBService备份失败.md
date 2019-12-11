# DBService备份失败<a name="ZH-CN_TOPIC_0185002829"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276016_sd64242caa665405798481482f49ab0ee"></a>

ls /srv/BigData/LocalBackup/default\_20190720222358/ -rlth

查看备份文件路径中没有DBService的备份文件。

**图 1**  查看备份文件<a name="zh-cn_topic_0167276016_fig6604647154910"></a>  
![](figures/查看备份文件.png "查看备份文件")

## 原因分析<a name="zh-cn_topic_0167276016_s4871ca6d7a6b47b1a0f8266b84631f32"></a>

-   查看DBService的备份日志/var/log/Bigdata/dbservice/scriptlog/backup.log，其实备份已经成功，只是上传至OMS节点时失败。

    ![](figures/zh-cn_image_0167276431.jpg)

-   失败原因是由于ssh不通。

    ![](figures/zh-cn_image_0167274644.jpg)


## 解决办法<a name="zh-cn_topic_0167276016_section4599086017025"></a>

1.  网络问题，联系网络工程师处理。
2.  网络问题解决之后重新备份即可。

