# ALM-27001 DBService服务不可用<a name="ALM-27001"></a>

## 告警解释<a name="section12415154"></a>

告警模块按30秒周期检测DBService服务状态。当DBService服务不可用时产生该告警。

DBService服务恢复时，告警清除。

## 告警属性<a name="section44627527"></a>

<a name="table65606365"></a>
<table><thead align="left"><tr id="row38885752"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p62738218"><a name="p62738218"></a><a name="p62738218"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p48630921"><a name="p48630921"></a><a name="p48630921"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p46790524"><a name="p46790524"></a><a name="p46790524"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row31936108"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p36687936"><a name="p36687936"></a><a name="p36687936"></a>27001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p18932833"><a name="p18932833"></a><a name="p18932833"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p57164470"><a name="p57164470"></a><a name="p57164470"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section66103423"></a>

<a name="table66919335"></a>
<table><thead align="left"><tr id="row15734150"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p66506614"><a name="p66506614"></a><a name="p66506614"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p18326663"><a name="p18326663"></a><a name="p18326663"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row5969144611210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row8064736"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p30954125"><a name="p30954125"></a><a name="p30954125"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row10151671"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33121175"><a name="p33121175"></a><a name="p33121175"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row29655127"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p18694496"><a name="p18694496"></a><a name="p18694496"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section58059901"></a>

数据库服务不可用，无法对上层服务提供数据入库、查询等功能，使部分服务异常。

## 可能原因<a name="section52777065"></a>

-   浮动IP不存在。
-   没有主DBServer实例。
-   主备DBServer进程都异常。

## 处理步骤<a name="section5231540"></a>

**检查集群环境中是否存在浮动IP。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> DBService \> 实例”。
2.  查看是否有主实例存在。
    -   是，执行[3](#li6439231114233)。
    -   否，执行[9](#li3383240514233)。

3.  <a name="li6439231114233"></a>选择主DBServer实例，记录IP地址。
4.  以**root**用户登录上述IP所在主机，执行**ifconfig**命令查看DBService的浮动IP在该节点是否存在，用户密码为安装前用户自定义，请咨询系统管理员。
    -   是，执行[5](#li5611337914233)。
    -   否，执行[9](#li3383240514233)。

5.  <a name="li5611337914233"></a>执行**ping **_浮动IP__地址_命令检查DBService的浮动IP的状态，是否能ping通。
    -   是，执行[6](#li589692014233)。
    -   否，执行[9](#li3383240514233)。

6.  <a name="li589692014233"></a>以**root**用户登录DBService浮动IP所在主机，执行以下命令删除浮动IP地址。

    **ifconfig **_interface _**down**

7.  在FusionInsight Manager首页，选择“ 集群 \>  _待操作集群的名称_  \> 服务 \> DBService \> 更多 \> 重启服务”重启DBService服务，检查是否启动成功。
    -   是，执行[8](#li1867223714233)。
    -   否，执行[9](#li3383240514233)。

8.  <a name="li1867223714233"></a>等待约两分钟，查看告警列表中的DBService服务不可用告警是否恢复。
    -   是，处理完毕。
    -   否，执行[14](#li5783704714233)。


**检查主DBServer实例状态。**

1.  <a name="li3383240514233"></a>选择角色状态异常的DBServer实例，记录IP地址。
2.  在“告警”页面，查看是否有上述IP所在主机DBServer实例“进程故障”告警产生。
    -   是，执行[11](#li2543669314233)。
    -   否，执行[19](#li2746648014233)。

3.  <a name="li2543669314233"></a>按“ALM-12007 进程故障”提供的步骤处理该告警。
4.  等待5分钟，查看告警列表中的DBService服务不可用告警是否恢复。
    -   是，处理完毕。
    -   否，执行[19](#li2746648014233)。


**检查主备DBServer数据库进程状态。**

1.  以**root**用户登录DBService浮动IP所在主机，执行**su - omm**命令切换至**omm**用户。
2.  <a name="li5783704714233"></a>执行**cd $\{DBSERVER\_HOME\}**命令进入DBService服务的安装目录。
3.  执行**sh sbin/status-dbserver.sh**命令查看DBService的主备HA进程状态，状态是否查询成功。

    ```
    HAMode 
    double 
    
    NodeName                  HostName               HAVersion                StartTime                HAActive             HAAllResOK           HARunPhase          
    10_5_89_12                host01                 V100R001C01              2019-06-13 21:33:09      active               normal               Actived             
    10_5_89_66                host03                 V100R001C01              2019-06-13 21:33:09      standby              normal               Deactived           
    
    NodeName                  ResName                ResStatus                ResHAStatus              ResType             
    10_5_89_12                floatip                Normal                   Normal                   Single_active       
    10_5_89_12                gaussDB                Active_normal            Normal                   Active_standby      
    10_5_89_66                floatip                Stopped                  Normal                   Single_active       
    10_5_89_66                gaussDB                Standby_normal           Normal                   Active_standby  
    ```

    -   是，执行[16](#li3422413114233)。
    -   否，执行[19](#li2746648014233)。

4.  <a name="li3422413114233"></a>查看主备HA进程是否都处于abnormal状态。
    -   是，执行[17](#li6099674614233)。
    -   否，执行[19](#li2746648014233)。

5.  <a name="li6099674614233"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> DBService \> 更多 \> 重启服务”重启DBService服务，查看界面是否提示重启成功。
    -   是，执行[18](#li4033453314233)。
    -   否，执行[19](#li2746648014233)。

6.  <a name="li4033453314233"></a>等待约两分钟，查看告警列表中的DBService服务不可用告警是否恢复。
    -   是，处理完毕。
    -   否，执行[19](#li2746648014233)。


**收集故障信息。**

1.  <a name="li2746648014233"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“DBService”和“NodeAgent”。
3.  单击右上角的![](figures/zh-cn_image_0263895392.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section47083863"></a>

无。

