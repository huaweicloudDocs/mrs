# ALM-24003 Flume Client连接中断<a name="alm_24003"></a>

## 告警解释<a name="zh-cn_topic_0191813877_section19665522175625"></a>

告警模块对Flume Server的连接端口状态进行监控。当Flume Client连接到Flume Server的某个端口，Client端连续3分钟未与Server端连接时，系统产生此告警。

当Flume Server收到Flume Client连接消息，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813877_section42254989175625"></a>

<a name="zh-cn_topic_0191813877_table102091175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813877_row31905194175625"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813877_p34183898175625"><a name="zh-cn_topic_0191813877_p34183898175625"></a><a name="zh-cn_topic_0191813877_p34183898175625"></a><strong id="zh-cn_topic_0191813877_b39219631175625"><a name="zh-cn_topic_0191813877_b39219631175625"></a><a name="zh-cn_topic_0191813877_b39219631175625"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813877_p22673543175625"><a name="zh-cn_topic_0191813877_p22673543175625"></a><a name="zh-cn_topic_0191813877_p22673543175625"></a><strong id="zh-cn_topic_0191813877_b2735300175625"><a name="zh-cn_topic_0191813877_b2735300175625"></a><a name="zh-cn_topic_0191813877_b2735300175625"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813877_p20232782175625"><a name="zh-cn_topic_0191813877_p20232782175625"></a><a name="zh-cn_topic_0191813877_p20232782175625"></a><strong id="zh-cn_topic_0191813877_b47877317175625"><a name="zh-cn_topic_0191813877_b47877317175625"></a><a name="zh-cn_topic_0191813877_b47877317175625"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813877_row52857467175625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813877_p3301341916288"><a name="zh-cn_topic_0191813877_p3301341916288"></a><a name="zh-cn_topic_0191813877_p3301341916288"></a>24003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813877_p5684124816288"><a name="zh-cn_topic_0191813877_p5684124816288"></a><a name="zh-cn_topic_0191813877_p5684124816288"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813877_p4073835316288"><a name="zh-cn_topic_0191813877_p4073835316288"></a><a name="zh-cn_topic_0191813877_p4073835316288"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813877_section27218191175625"></a>

<a name="zh-cn_topic_0191813877_table57189892175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813877_row20832688175625"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813877_p9726186175625"><a name="zh-cn_topic_0191813877_p9726186175625"></a><a name="zh-cn_topic_0191813877_p9726186175625"></a><strong id="zh-cn_topic_0191813877_b20426813175625"><a name="zh-cn_topic_0191813877_b20426813175625"></a><a name="zh-cn_topic_0191813877_b20426813175625"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813877_p43959148175625"><a name="zh-cn_topic_0191813877_p43959148175625"></a><a name="zh-cn_topic_0191813877_p43959148175625"></a><strong id="zh-cn_topic_0191813877_b60088019175625"><a name="zh-cn_topic_0191813877_b60088019175625"></a><a name="zh-cn_topic_0191813877_b60088019175625"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813877_row35291346175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813877_p38975600162819"><a name="zh-cn_topic_0191813877_p38975600162819"></a><a name="zh-cn_topic_0191813877_p38975600162819"></a>ClientIP</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813877_p2907071162819"><a name="zh-cn_topic_0191813877_p2907071162819"></a><a name="zh-cn_topic_0191813877_p2907071162819"></a>Flume客户端IP地址。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813877_row54265439175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813877_p38880625162819"><a name="zh-cn_topic_0191813877_p38880625162819"></a><a name="zh-cn_topic_0191813877_p38880625162819"></a>ServerIP</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813877_p62322936162819"><a name="zh-cn_topic_0191813877_p62322936162819"></a><a name="zh-cn_topic_0191813877_p62322936162819"></a>Flume服务端IP地址。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813877_row5894265175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813877_p720032162819"><a name="zh-cn_topic_0191813877_p720032162819"></a><a name="zh-cn_topic_0191813877_p720032162819"></a>ServerPort</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813877_p58322633162819"><a name="zh-cn_topic_0191813877_p58322633162819"></a><a name="zh-cn_topic_0191813877_p58322633162819"></a>Flume服务端端口。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813877_section23922301175625"></a>

产生告警的Flume Client无法与Flume Server端进行通信，Flume Client端的数据无法传输到Flume Server端。

## 可能原因<a name="zh-cn_topic_0191813877_section58162349175625"></a>

-   Flume Client端与Flume Server端网络故障。
-   Flume Client端进程故障。
-   Flume Client端配置错误。

## 处理步骤<a name="zh-cn_topic_0191813877_section51182191175625"></a>

1.  检查Flume Client与Flume Server的网络状况。
    1.  登录告警定位参数中描述的Flume ClientIP所在主机，执行以下命令切换root用户。

        **sudo su - root**

    2.  执行**ping** _Flume Server IP地址_命令，检查Flume Client到Flume Server的网络是否正常。
        -   是，执行[2.a](#zh-cn_topic_0191813877_li33911624175511)。
        -   否，执行[4](#zh-cn_topic_0191813877_li572522141314)。

2.  检查Flume Client端进程故障。
    1.  <a name="zh-cn_topic_0191813877_li33911624175511"></a>登录告警定位参数中描述的Flume ClientIP所在主机，执行以下命令切换root用户。

        **sudo su - root**

    2.  执行**ps -ef|grep flume |grep client**命令，查看是否存在Flume Client进程。
        -   是，执行[3.a](#zh-cn_topic_0191813877_li37860237175538)。
        -   否，执行[4](#zh-cn_topic_0191813877_li572522141314)。

3.  检查Flume Client端的配置。
    1.  <a name="zh-cn_topic_0191813877_li37860237175538"></a>登录告警定位参数中描述的Flume ClientIP所在主机，执行以下命令切换root用户。

        **sudo su - root**

    2.  执行**cd** _Flume安装目录_**/fusioninsight-flume-1.6.0/conf/**命令，进入Flume的配置目录。
    3.  执行**cat properties.properties**命令，查看当前的Flume Client配置文件。
    4.  根据Flume Agent的配置说明检查“properties.properties“的配置是否有误。
        -   是，执行[3.e](#zh-cn_topic_0191813877_li1644380175538)。
        -   否，执行[4](#zh-cn_topic_0191813877_li572522141314)。

    5.  <a name="zh-cn_topic_0191813877_li1644380175538"></a>修改“properties.properties“配置文件。
    6.  查看告警列表中，该告警是否已清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0191813877_li572522141314)。

4.  <a name="zh-cn_topic_0191813877_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813877_section20269844175625"></a>

无。

