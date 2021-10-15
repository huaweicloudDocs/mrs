# ALM-43001 Spark2x服务不可用<a name="ALM-43001"></a>

## 告警解释<a name="sfd8b339bedd64c0a800ae1a67c395e3d"></a>

系统每300秒周期性检测Spark2x服务状态，当检测到Spark2x服务不可用时产生该告警。

Spark2x服务恢复时，告警清除。

## 告警属性<a name="s4d15fff803034c2e90ea3bef147e12a0"></a>

<a name="t67ad7044936342388f012166d0f0b216"></a>
<table><thead align="left"><tr id="r988998ef3957491ebfae6d586db6b498"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="a87d511f23c734506a10ae013a3188b02"><a name="a87d511f23c734506a10ae013a3188b02"></a><a name="a87d511f23c734506a10ae013a3188b02"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0085589435_p134110272463"><a name="zh-cn_topic_0085589435_p134110272463"></a><a name="zh-cn_topic_0085589435_p134110272463"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0085589435_p041172717467"><a name="zh-cn_topic_0085589435_p041172717467"></a><a name="zh-cn_topic_0085589435_p041172717467"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="rfd73b8384d0f4f93968a2f65ec95704b"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="a53fca132f875466099d765181f0cd30f"><a name="a53fca132f875466099d765181f0cd30f"></a><a name="a53fca132f875466099d765181f0cd30f"></a>43001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="a231198015e854c01b4747f427e9b896b"><a name="a231198015e854c01b4747f427e9b896b"></a><a name="a231198015e854c01b4747f427e9b896b"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="a35e0eddc667f418c95150abdfc44c104"><a name="a35e0eddc667f418c95150abdfc44c104"></a><a name="a35e0eddc667f418c95150abdfc44c104"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s237c9014275649c0af4a6de81817d6da"></a>

<a name="tf806d41abf4143deb857f483ebbc1442"></a>
<table><thead align="left"><tr id="rf9a887fa209a4d37aa2d23c28fcbca22"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="a80750c4ea59c4d2db9fea11d051e4da5"><a name="a80750c4ea59c4d2db9fea11d051e4da5"></a><a name="a80750c4ea59c4d2db9fea11d051e4da5"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="a455eeb8ae9a54e04809ab220fec60d59"><a name="a455eeb8ae9a54e04809ab220fec60d59"></a><a name="a455eeb8ae9a54e04809ab220fec60d59"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1658442101311"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="r87c0de301fda4bc2a5c20eb06b8eef1e"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a763605012b264765a790dafaa8c23bae"><a name="a763605012b264765a790dafaa8c23bae"></a><a name="a763605012b264765a790dafaa8c23bae"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="r79ee8dfdaa6e431489e367b67703dba9"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="ad8c63d4eba42438b86558e485c0cc71f"><a name="ad8c63d4eba42438b86558e485c0cc71f"></a><a name="ad8c63d4eba42438b86558e485c0cc71f"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="r4389d3033fb14642960afdcd45b94800"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="aa0aa13f9693b433c8efea87a6b09bc10"><a name="aa0aa13f9693b433c8efea87a6b09bc10"></a><a name="aa0aa13f9693b433c8efea87a6b09bc10"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="sc2d2366502ca4f06a13a93507bd6daf2"></a>

用户提交的Spark任务执行失败。

## 可能原因<a name="s1e0bd4f55bfb4f19b241e718c3cba660"></a>

-   KrbServer服务异常。
-   LdapServer服务异常。
-   ZooKeeper服务异常。
-   HDFS服务异常。
-   Yarn服务异常。
-   对应的Hive服务异常。
-   Spark2x assembly包异常。

## 处理步骤<a name="s63bd3093c017460f9d177b51a60f7cd2"></a>

若告警原因为：Spark2x assembly包异常，则表示spark的包存在异常，等待10分钟左右，告警自动恢复。

**检查Spark2x依赖的服务是否有服务不可用告警。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”。
2.  在告警列表中，查看是否存在以下告警：

    -   ALM-25500 KrbServer服务不可用
    -   ALM-25000 LdapServer服务不可用
    -   ALM-13000 ZooKeeper服务不可用
    -   ALM-14000 HDFS服务不可用
    -   ALM-18000 Yarn服务不可用
    -   ALM-16004 Hive服务不可用

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >若集群启用了多实例功能且安装了多个Spark2x服务，请根据“定位信息”中的“服务名”值来查看具体产生告警的Spark2x服务，然后确认对应的Hive服务是否故障，Spark2x对应Hive，Spark2x1对应Hive1，以此类推。

    -   是，执行[3](#l0ca5fe03ce10420c9ad6c90f8583a4bd)。
    -   否，执行[4](#zh-cn_topic_0085589435_li3748337517)。

3.  <a name="l0ca5fe03ce10420c9ad6c90f8583a4bd"></a>根据对应服务不可用告警帮助提供的故障处理对应告警。

    告警全部恢复后，等待几分钟，检查本告警是否恢复。

    -   是，处理完毕。
    -   否，执行[4](#zh-cn_topic_0085589435_li3748337517)。


**收集故障信息。**

1.  <a name="zh-cn_topic_0085589435_li3748337517"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。（Hive为根据告警定位信息中的“服务名”确定的具体Hive服务。）
    -   KrbServer
    -   LdapServer
    -   ZooKeeper
    -   HDFS
    -   Yarn
    -   Hive

3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s36f409bbb4a74860b9bd0d367c6a8856"></a>

无。

