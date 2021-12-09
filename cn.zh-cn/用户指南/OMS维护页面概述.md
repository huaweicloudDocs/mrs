# OMS维护页面概述<a name="admin_guide_000160"></a>

## 总览<a name="section71293442312"></a>

登录FusionInsight Manager以后，选择“系统  \>  OMS“后，打开OMS维护页面，管理员可以在此页面对OMS进行维护操作，包含查看基本信息、查看OMS业务模块的服务状态，也可以手工触发健康检查。

## 基本信息<a name="section4371164773515"></a>

FusionInsight Manager支持显示当前OMS的关联信息，包含如[表1](#table14579151510169)所示内容：

**表 1**  OMS信息说明

<a name="table14579151510169"></a>
<table><thead align="left"><tr id="row165801215161612"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="p12580415191613"><a name="p12580415191613"></a><a name="p12580415191613"></a>项目</p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="p10580415181611"><a name="p10580415181611"></a><a name="p10580415181611"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row658051511616"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="p12580141518168"><a name="p12580141518168"></a><a name="p12580141518168"></a>版本</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="p458011154163"><a name="p458011154163"></a><a name="p458011154163"></a>表示OMS版本，与FusionInsight Manager版本相同。</p>
</td>
</tr>
<tr id="row5992182015577"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="p499212011573"><a name="p499212011573"></a><a name="p499212011573"></a>IP模式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="p399242013579"><a name="p399242013579"></a><a name="p399242013579"></a>表示当前集群网络的IP地址模式。</p>
</td>
</tr>
<tr id="row358011591619"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="p20580121512164"><a name="p20580121512164"></a><a name="p20580121512164"></a>HA模式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="p12580915181611"><a name="p12580915181611"></a><a name="p12580915181611"></a>表示OMS工作模式，由安装FusionInsight Manager时的配置文件指定。</p>
</td>
</tr>
<tr id="row20626135101719"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="p1762623511718"><a name="p1762623511718"></a><a name="p1762623511718"></a>当前主用</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="p66268350178"><a name="p66268350178"></a><a name="p66268350178"></a>表示OMS主进程节点主机名，即主管理节点主机名。单击主机名可进入对应的主机详情页面。</p>
</td>
</tr>
<tr id="row697310159181"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="p29731115131820"><a name="p29731115131820"></a><a name="p29731115131820"></a>当前备用</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="p5973415161813"><a name="p5973415161813"></a><a name="p5973415161813"></a>表示OMS备进程节点主机名，即备管理节点主机名。单击主机名可进入对应的主机详情页面。</p>
</td>
</tr>
<tr id="row5251576197"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="p1825317161913"><a name="p1825317161913"></a><a name="p1825317161913"></a>持续时间</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="p192531979197"><a name="p192531979197"></a><a name="p192531979197"></a>表示OMS进程启动持续的时间。</p>
</td>
</tr>
</tbody>
</table>

## OMS服务状态<a name="section193422041131915"></a>

FusionInsight Manager支持显示OMS所有业务模块的运行状态，每个业务模块的状态显示为![](figures/zh-cn_image_0263899675.png)表示运行正常。

## 健康检查<a name="section5976142292315"></a>

管理员可以在OMS维护页面单击“健康检查”开始为OMS的状态进行检查。如果某些检查项存在问题，可直接打开检查说明进行处理。

**图 1**  健康检查<a name="fig15410153111514"></a>  
![](figures/健康检查-61.png "健康检查-61")

## 进入/退出维护模式<a name="section31707133135"></a>

配置OMS进入或退出维护模式。

## 系统参数<a name="section128352391512"></a>

在大集群场景下对接DMPS集群。

