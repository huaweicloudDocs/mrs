# ALM-24001 Flume Agent异常<a name="ZH-CN_TOPIC_0093195083"></a>

## 告警解释<a name="zh-cn_topic_0054336020_section19665522175625"></a>

Flume Agent监控模块对Flume Agent状态进行监控，当Flume Agent进程故障时，系统产生此告警。

当检测到Flume Agent进程故障恢复，且告警处理完成时，告警恢复。

## 告警属性<a name="zh-cn_topic_0054336020_section42254989175625"></a>

<a name="zh-cn_topic_0054336020_table102091175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0054336020_row31905194175625"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0054336020_p34183898175625"><a name="zh-cn_topic_0054336020_p34183898175625"></a><a name="zh-cn_topic_0054336020_p34183898175625"></a><strong id="zh-cn_topic_0054336020_b39219631175625"><a name="zh-cn_topic_0054336020_b39219631175625"></a><a name="zh-cn_topic_0054336020_b39219631175625"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0054336020_p22673543175625"><a name="zh-cn_topic_0054336020_p22673543175625"></a><a name="zh-cn_topic_0054336020_p22673543175625"></a><strong id="zh-cn_topic_0054336020_b2735300175625"><a name="zh-cn_topic_0054336020_b2735300175625"></a><a name="zh-cn_topic_0054336020_b2735300175625"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0054336020_p20232782175625"><a name="zh-cn_topic_0054336020_p20232782175625"></a><a name="zh-cn_topic_0054336020_p20232782175625"></a><strong id="zh-cn_topic_0054336020_b47877317175625"><a name="zh-cn_topic_0054336020_b47877317175625"></a><a name="zh-cn_topic_0054336020_b47877317175625"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0054336020_row52857467175625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0054336020_p45931966162646"><a name="zh-cn_topic_0054336020_p45931966162646"></a><a name="zh-cn_topic_0054336020_p45931966162646"></a>24001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0054336020_p29501732162646"><a name="zh-cn_topic_0054336020_p29501732162646"></a><a name="zh-cn_topic_0054336020_p29501732162646"></a>一般</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0054336020_p40830091162646"><a name="zh-cn_topic_0054336020_p40830091162646"></a><a name="zh-cn_topic_0054336020_p40830091162646"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0054336020_section27218191175625"></a>

<a name="zh-cn_topic_0054336020_table57189892175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0054336020_row20832688175625"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0054336020_p9726186175625"><a name="zh-cn_topic_0054336020_p9726186175625"></a><a name="zh-cn_topic_0054336020_p9726186175625"></a><strong id="zh-cn_topic_0054336020_b20426813175625"><a name="zh-cn_topic_0054336020_b20426813175625"></a><a name="zh-cn_topic_0054336020_b20426813175625"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0054336020_p43959148175625"><a name="zh-cn_topic_0054336020_p43959148175625"></a><a name="zh-cn_topic_0054336020_p43959148175625"></a><strong id="zh-cn_topic_0054336020_b60088019175625"><a name="zh-cn_topic_0054336020_b60088019175625"></a><a name="zh-cn_topic_0054336020_b60088019175625"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0054336020_row35291346175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0054336020_p20355870162656"><a name="zh-cn_topic_0054336020_p20355870162656"></a><a name="zh-cn_topic_0054336020_p20355870162656"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0054336020_p38212784162656"><a name="zh-cn_topic_0054336020_p38212784162656"></a><a name="zh-cn_topic_0054336020_p38212784162656"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0054336020_row54265439175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0054336020_p6941546162656"><a name="zh-cn_topic_0054336020_p6941546162656"></a><a name="zh-cn_topic_0054336020_p6941546162656"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0054336020_p25394391162656"><a name="zh-cn_topic_0054336020_p25394391162656"></a><a name="zh-cn_topic_0054336020_p25394391162656"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0054336020_row5894265175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0054336020_p57573702162656"><a name="zh-cn_topic_0054336020_p57573702162656"></a><a name="zh-cn_topic_0054336020_p57573702162656"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0054336020_p32958279162656"><a name="zh-cn_topic_0054336020_p32958279162656"></a><a name="zh-cn_topic_0054336020_p32958279162656"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0054336020_section23922301175625"></a>

产生告警的Flume Agent实例无法提供正常功能，定义在该实例下的数据传输任务暂时中断，对于实时数据传输，会丢失实时数据。

## 可能原因<a name="zh-cn_topic_0054336020_section58162349175625"></a>

-   JAVA\_HOME目录不存在或JAVA权限异常。
-   Flume Agent目录权限异常。

## 处理步骤<a name="zh-cn_topic_0054336020_section51182191175625"></a>

1.  检查Flume Agent配置文件。
    1.  登录故障节点IP所在主机，执行以下命令切换root用户。

        **sudo su - root**

    2.  执行**cd** _Flume安装目录_**/fusioninsight-flume-1.6.0/conf/**命令，进入Flume的配置目录。
    3.  执行**cat ENV\_VARS**命令，检查JAVA\_HOME目录是否存在，Flume Agent运行用户是否有JAVA可执行权限。
        -   是，执行[2.a](#zh-cn_topic_0054336020_li53200420164950)。
        -   否，执行[1.d](#zh-cn_topic_0054336020_li5041523116491)。

    4.  <a name="zh-cn_topic_0054336020_li5041523116491"></a>指定正确的JAVA\_HOME目录并赋予Flume Agent运行用户JAVA可执行权限，执行[2.d](#zh-cn_topic_0054336020_li22464349164950)。

2.  检查Flume Agent的目录权限。
    1.  <a name="zh-cn_topic_0054336020_li53200420164950"></a>登录故障节点IP所在主机，执行以下命令切换root用户。

        **sudo su - root**

    2.  执行以下命令，进入Flume Agent的安装目录。

        **cd** _Flume Agent的安装目录_

    3.  执行**ls -al \* -R**命令，检查是否所有文件的所有者均是运行Flume Agent的用户。
        -   是，执行[3.a](#zh-cn_topic_0054336020_li4782764165025)。
        -   否，使用**chown**命令修改文件属主为运行Flume Agent的用户，执行[2.d](#zh-cn_topic_0054336020_li22464349164950)

    4.  <a name="zh-cn_topic_0054336020_li22464349164950"></a>查看告警列表中，该告警是否已清除。
        -   是，处理完毕。
        -   否，执行[3.a](#zh-cn_topic_0054336020_li4782764165025)。


3.  收集故障信息。
    1.  <a name="zh-cn_topic_0054336020_li4782764165025"></a>在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系公有云运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0054336020_section20269844175625"></a>

无。

