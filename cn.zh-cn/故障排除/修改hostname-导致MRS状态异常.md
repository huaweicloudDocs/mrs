# 修改hostname，导致MRS状态异常<a name="ZH-CN_TOPIC_0169694556"></a>

## 用户问题<a name="section18305143583116"></a>

修改hostname后，MRS状态异常怎么处理？

## 问题现象<a name="section117424454313"></a>

修改hostname，导致MRS状态异常。

## 原因分析<a name="section1237061220324"></a>

修改hostname导致兼容性问题和故障。

## 处理步骤<a name="section1950914915437"></a>

1.  以root用户登录集群的任意节点。
2.  在集群节点中执行**cat /etc/hosts**命令，查看各个节点的hostname值，根据此值来配置newhostname变量值 。
3.  在hostname被修改的节点上执行**sudo hostnamectl set-hostname $\{newhostname\}**命令，恢复正确的hostname。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >$\{newhostname\}：表示新的hostname取值。  

4.  修改完成后，重新登录修改hostname的节点，查看修改的hostname是否生效。

