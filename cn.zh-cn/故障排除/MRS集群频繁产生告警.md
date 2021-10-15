# MRS集群频繁产生告警<a name="mrs_03_0263"></a>

## 用户问题<a name="section18305143583116"></a>

集群频繁发出Manager主备节点间心跳中断，DBService主备节点间心跳中断，节点故障等告警，偶尔会造成hive不可用。

## 问题现象<a name="section117424454313"></a>

集群频繁发出Manager主备节点间心跳中断，DBService主备节点间心跳中断，节点故障等告警，偶尔会造成hive不可用，影响客户业务。

## 原因分析<a name="section1237061220324"></a>

1.  在出现告警时间点发现虚拟机发生了重启，告警发生的原因是因虚拟机重启导致的。

    ![](figures/zh-cn_image_0280284052.png)

    ![](figures/zh-cn_image_0280284060.png)

2.  经OS定位虚拟机发生重启的原因是节点没有可用的内存，系统发生内存溢出触发了oom-killer，当进程处于被调用的状态会使进程处于disk sleep状态，最终导致虚拟机发生重启。

    ![](figures/zh-cn_image_0280296061.png)

    ![](figures/zh-cn_image_0280296115.png)

    ![](figures/zh-cn_image_0280296156.png)

3.  查看占用的内存进程，发现占用内存都是正常的业务进程。

结论：虚拟机内存不能满足服务需求。

## 处理步骤<a name="section5661655478"></a>

-   建议扩大节点内存。
-   建议关闭不需要的服务来规避该问题。

