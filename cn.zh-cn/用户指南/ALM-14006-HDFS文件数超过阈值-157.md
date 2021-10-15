# ALM-14006 HDFS文件数超过阈值<a name="ALM-14006"></a>

## 告警解释<a name="section57589516"></a>

系统每30秒周期性检测HDFS文件数，并把实际文件数和阈值相比较。当检测到HDFS文件数指标超出阈值范围时产生该告警。

平滑次数为1，HDFS文件数指标的值小于或等于阈值时，告警恢复；平滑次数大于1，HDFS文件数指标的值小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section48543596"></a>

<a name="table35459729"></a>
<table><thead align="left"><tr id="row47975022"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p60771574"><a name="p60771574"></a><a name="p60771574"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p23550475"><a name="p23550475"></a><a name="p23550475"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p28540308"><a name="p28540308"></a><a name="p28540308"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row30063610"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p19233316"><a name="p19233316"></a><a name="p19233316"></a>14006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p14394746"><a name="p14394746"></a><a name="p14394746"></a>次要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p25123814"><a name="p25123814"></a><a name="p25123814"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section34239183"></a>

<a name="table21763021"></a>
<table><thead align="left"><tr id="row17034695"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p37633021"><a name="p37633021"></a><a name="p37633021"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p28375860"><a name="p28375860"></a><a name="p28375860"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row18643359173110"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row16743315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62793452"><a name="p62793452"></a><a name="p62793452"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row28270157"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p58708857"><a name="p58708857"></a><a name="p58708857"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row58617672"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56757437"><a name="p56757437"></a><a name="p56757437"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row41054890"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37111817"><a name="p37111817"></a><a name="p37111817"></a>NameService名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p53267196"><a name="p53267196"></a><a name="p53267196"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="row9642721"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p42862926"><a name="p42862926"></a><a name="p42862926"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p49344963"><a name="p49344963"></a><a name="p49344963"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section39717199"></a>

HDFS文件数过多，磁盘存储不足可能造成数据入库失败。对HDFS系统性能产生影响。

## 可能原因<a name="section21910476"></a>

HDFS文件数超过阈值。

## 处理步骤<a name="section62976559"></a>

**检查系统中文件数量。**

1.  在FusionInsight Manager首页，查看当前的HDFS文件数。HDFS文件数可以通单击“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”，单击图表区域右上角的下拉菜单，选择“定制 \> 文件和块”，勾选“HDFS文件”和“HDFS块数”监控项查看。
2.  在“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> 全部配置”中查找“NameNode”下的GC\_OPTS参数。
3.  配置文件对象数阈值：修改GC\_OPTS参数中Xmx的值（Xmx内存值对应文件数阈值的公式为（y = 0.2007 x - 0.6312），其中x为内存数Xmx（GB），y为文件数（单位KW）。用户根据需要调整内存大小）。
4.  确认GC\_PROFILE的值为custom，使GC\_OPTS配置生效。单击“保存”，单击“更多 \> 重启服务”重启服务。
5.  检查本告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li57477018164725)。


**检查系统中是否有不需要的文件。**

1.  <a name="li57477018164725"></a>以**root**用户登录HDFS客户端，用户密码为安装前用户自定义，请咨询系统管理员。执行**cd**命令进入客户端安装目录，然后执行**source bigdata\_env**命令设置环境变量。

    如果集群采用安全版本，要进行安全认证。

    执行**kinit hdfs**命令，按提示输入密码。向管理员获取密码。

2.  执行**hdfs dfs -ls **_文件或目录路径_命令，检查该目录下的文件或目录是否是可以删除的无用文件。
    -   是，执行[8](#li46417503164725)。
    -   否，执行[9](#li15104347164725)。

3.  <a name="li46417503164725"></a>执行**hdfs dfs -rm -r **_文件或目录路径_命令。确认删除无用的文件后，等待文件在垃圾站中超过保留时间后（NameNode的配置参数“fs.trash.interval”指定了垃圾站中数据的保留时间），检查本告警是否清除。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >删除文件为高危操作，在执行操作前请务必确认对应文件是否不再需要。

    -   是，处理完毕。
    -   否，执行[9](#li15104347164725)。


**收集故障信息。**

1.  <a name="li15104347164725"></a>在FusionInsight Manager首页，单击“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS”。
3.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section29918121"></a>

**NameNode JVM参数配置规则**

NameNode JVM参数“GC\_OPTS”默认值为：

-Xms2G -Xmx4G -XX:NewSize=128M -XX:MaxNewSize=256M -XX:MetaspaceSize=128M -XX:MaxMetaspaceSize=128M -XX:+UseConcMarkSweepGC -XX:+CMSParallelRemarkEnabled -XX:CMSInitiatingOccupancyFraction=65 -XX:+PrintGCDetails -Dsun.rmi.dgc.client.gcInterval=0x7FFFFFFFFFFFFFE -Dsun.rmi.dgc.server.gcInterval=0x7FFFFFFFFFFFFFE -XX:-OmitStackTraceInFastThrow -XX:+PrintGCDateStamps -XX:+UseGCLogFileRotation -XX:NumberOfGCLogFiles=10 -XX:GCLogFileSize=1M -Djdk.tls.ephemeralDHKeySize=2048

NameNode文件数量和NameNode使用的内存大小成比例关系，文件对象变化时请修改默认值中的“-Xms2G -Xmx4G -XX:NewSize=128M -XX:MaxNewSize=256M”。参考值如下表所示。

**表 1**  NameNode JVM配置

<a name="te26cc4df625545418ac6cc0a8f9f88f0"></a>
<table><thead align="left"><tr id="r12696e3d9eac47308ab8ceeeabaf9d60"><th class="cellrowborder" valign="top" width="28.01%" id="mcps1.2.3.1.1"><p id="a1d09de0bdefa473fb5bbe44fa938dd42"><a name="a1d09de0bdefa473fb5bbe44fa938dd42"></a><a name="a1d09de0bdefa473fb5bbe44fa938dd42"></a>文件对象数量</p>
</th>
<th class="cellrowborder" valign="top" width="71.99%" id="mcps1.2.3.1.2"><p id="a3cda0d608a9342f1a59ffca91ccb43fb"><a name="a3cda0d608a9342f1a59ffca91ccb43fb"></a><a name="a3cda0d608a9342f1a59ffca91ccb43fb"></a>参考值</p>
</th>
</tr>
</thead>
<tbody><tr id="rf83d3e2a613f4411b06455ba3d050a91"><td class="cellrowborder" valign="top" width="28.01%" headers="mcps1.2.3.1.1 "><p id="a698a4c1bac0e47a39311c4d3eab22de6"><a name="a698a4c1bac0e47a39311c4d3eab22de6"></a><a name="a698a4c1bac0e47a39311c4d3eab22de6"></a>10,000,000</p>
</td>
<td class="cellrowborder" valign="top" width="71.99%" headers="mcps1.2.3.1.2 "><p id="ae013dee8e5c249b589373d1f0d623955"><a name="ae013dee8e5c249b589373d1f0d623955"></a><a name="ae013dee8e5c249b589373d1f0d623955"></a>“-Xms6G -Xmx6G -XX:NewSize=512M  -XX:MaxNewSize=512M”</p>
</td>
</tr>
<tr id="r71dd137d8340469b9d6cfa56bad12a4f"><td class="cellrowborder" valign="top" width="28.01%" headers="mcps1.2.3.1.1 "><p id="a068a2ba0b8aa4d6d83a392de11a0c207"><a name="a068a2ba0b8aa4d6d83a392de11a0c207"></a><a name="a068a2ba0b8aa4d6d83a392de11a0c207"></a>20,000,000</p>
</td>
<td class="cellrowborder" valign="top" width="71.99%" headers="mcps1.2.3.1.2 "><p id="a702b804579e84bd490aae5a79da4302f"><a name="a702b804579e84bd490aae5a79da4302f"></a><a name="a702b804579e84bd490aae5a79da4302f"></a>“-Xms12G -Xmx12G -XX:NewSize=1G  -XX:MaxNewSize=1G”</p>
</td>
</tr>
<tr id="racee4c018a9f4a729de4be081d5da2c7"><td class="cellrowborder" valign="top" width="28.01%" headers="mcps1.2.3.1.1 "><p id="afbb0ed490b2d406583d777e01adad1f0"><a name="afbb0ed490b2d406583d777e01adad1f0"></a><a name="afbb0ed490b2d406583d777e01adad1f0"></a>50,000,000</p>
</td>
<td class="cellrowborder" valign="top" width="71.99%" headers="mcps1.2.3.1.2 "><p id="a9f14dacaf1354a21919d6791d891e970"><a name="a9f14dacaf1354a21919d6791d891e970"></a><a name="a9f14dacaf1354a21919d6791d891e970"></a>“-Xms32G -Xmx32G -XX:NewSize=3G  -XX:MaxNewSize=3G”</p>
</td>
</tr>
<tr id="r39bfe2109be84e2bb1757f212f3c7361"><td class="cellrowborder" valign="top" width="28.01%" headers="mcps1.2.3.1.1 "><p id="a03cfef126810415795047cb2bbc7b216"><a name="a03cfef126810415795047cb2bbc7b216"></a><a name="a03cfef126810415795047cb2bbc7b216"></a>100,000,000</p>
</td>
<td class="cellrowborder" valign="top" width="71.99%" headers="mcps1.2.3.1.2 "><p id="a61d1ccadcb8a4b738f933413bd59a772"><a name="a61d1ccadcb8a4b738f933413bd59a772"></a><a name="a61d1ccadcb8a4b738f933413bd59a772"></a>“-Xms64G -Xmx64G -XX:NewSize=6G  -XX:MaxNewSize=6G”</p>
</td>
</tr>
<tr id="r3ee104e2dbe84dd6b2aea0a70d6fb067"><td class="cellrowborder" valign="top" width="28.01%" headers="mcps1.2.3.1.1 "><p id="a795cdaa74df54d38aeb6f1317a72d62a"><a name="a795cdaa74df54d38aeb6f1317a72d62a"></a><a name="a795cdaa74df54d38aeb6f1317a72d62a"></a>200,000,000</p>
</td>
<td class="cellrowborder" valign="top" width="71.99%" headers="mcps1.2.3.1.2 "><p id="aeb30301f03f549c7b5f56ce86b23a410"><a name="aeb30301f03f549c7b5f56ce86b23a410"></a><a name="aeb30301f03f549c7b5f56ce86b23a410"></a>“-Xms96G -Xmx96G -XX:NewSize=9G  -XX:MaxNewSize=9G”</p>
</td>
</tr>
<tr id="r439309a2fb8c4f19a60122d992e22e77"><td class="cellrowborder" valign="top" width="28.01%" headers="mcps1.2.3.1.1 "><p id="ad0738c3e97f14db9a3a72023f45e6c59"><a name="ad0738c3e97f14db9a3a72023f45e6c59"></a><a name="ad0738c3e97f14db9a3a72023f45e6c59"></a>300,000,000</p>
</td>
<td class="cellrowborder" valign="top" width="71.99%" headers="mcps1.2.3.1.2 "><p id="ab31506428f634ad58ac748c65df24232"><a name="ab31506428f634ad58ac748c65df24232"></a><a name="ab31506428f634ad58ac748c65df24232"></a>“-Xms164G -Xmx164G -XX:NewSize=12G  -XX:MaxNewSize=12G”</p>
</td>
</tr>
</tbody>
</table>

