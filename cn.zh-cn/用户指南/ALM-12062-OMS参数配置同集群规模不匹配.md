# ALM-12062 OMS参数配置同集群规模不匹配<a name="ALM-12062"></a>

## 告警解释<a name="section25514987"></a>

系统每一个小时，整点检查一次OMS参数配置和集群规模是否匹配，如果检查OMS配置的参数不足以支撑当前的集群规模，系统将发送此告警。待用户修改OMS参数配置，该告警会自动清除。

## 告警属性<a name="section28308296"></a>

<a name="table36969235"></a>
<table><thead align="left"><tr id="row42433012"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p14521914"><a name="p14521914"></a><a name="p14521914"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p35424385"><a name="p35424385"></a><a name="p35424385"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p50802928"><a name="p50802928"></a><a name="p50802928"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row21396528"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p55397225"><a name="p55397225"></a><a name="p55397225"></a>12062</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p57990210"><a name="p57990210"></a><a name="p57990210"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p66695395"><a name="p66695395"></a><a name="p66695395"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section53448080"></a>

<a name="table33617909"></a>
<table><thead align="left"><tr id="row23730911"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p43155662"><a name="p43155662"></a><a name="p43155662"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p5947729"><a name="p5947729"></a><a name="p5947729"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1245134911362"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row12004049"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p32803893"><a name="p32803893"></a><a name="p32803893"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p39869670"><a name="p39869670"></a><a name="p39869670"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row23282710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p6851364"><a name="p6851364"></a><a name="p6851364"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p18089651"><a name="p18089651"></a><a name="p18089651"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row28589139"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p34018885"><a name="p34018885"></a><a name="p34018885"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4066316"><a name="p4066316"></a><a name="p4066316"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section656349174713"></a>

安装集群或者系统扩容节点未同步修改相应的OMS配置。

## 可能原因<a name="section14827121311816"></a>

OMS配置同集群规模不匹配。

## 处理步骤<a name="section8673534085"></a>

**检查OMS配置同集群规模是否匹配。**

1.  打开FusionInsight Manager页面，在告警列表中，单击此告警所在行的![](figures/zh-cn_image_0263895710.png)，查看该告警的主机地址。
2.  以**root**用户登录告警所在主机，用户密码为安装前用户自定义，请咨询系统管理员。

1.  执行命令**su - omm**，切换到**omm**用户。
2.  执行命令**vi $BIGDATA\_LOG\_HOME/controller/scriptlog/modify\_manager\_param.log**打开对应日志，搜索日志“**Current oms configurations can not support** **_xx_  nodes**”，其中_xx_为当前集群节点个数**。**
3.  参考[根据集群节点数优化Manager配置](#section183241356931)，对当前集群配置进行优化。
4.  配置完成后等待1小时后，查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[7](#li1767253417818)。


**收集故障信息。**

1.  <a name="li1767253417818"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“Controller”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895632.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section183241356931"></a>

**根据集群节点数优化Manager配置**

1.  以**omm**用户登录主管理节点。
2.  执行以下命令，切换目录。

    **cd $\{BIGDATA\_HOME\}/om-server/om/sbin**

3.  执行以下命令查看当前集群Manager相关配置。

    **sh oms\_config\_info.sh -q**

4.  执行以下命令指定当前集群的节点数。

    命令格式：**sh oms\_config\_info.sh -s **_节点数_

    例如：

    **sh oms\_config\_info.sh -s 1000**

    根据界面提示，输入“y“：

    ```
    The following configurations will be modified:
         Module       Parameter         Current               Target 
         Controller   controller.Xmx    4096m             =>  16384m
         Controller   controller.Xms    1024m             =>  8192m        Controller   controller.node.heartbeat.error.threshold     30000                      =>   60000                   
         Pms          pms.mem           8192m             =>  10240m 
    Do you really want to do this operation? (y/n):
    ```

    界面提示以下信息表示配置更新成功：

    ```
    ...
    Operation has been completed. Now restarting OMS server.                  [done]
    Restarted oms server successfully.
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   配置更新过程中，OMS会自动重启。
    >-   相近数量的节点规模对应的Manager相关配置是通用的，例如100节点变为101节点，并没有新的配置项需要刷新。


