# LdapServer健康检查指标项说明<a name="ZH-CN_TOPIC_0173397620"></a>

## SlapdServer服务可用性检查<a name="section19258516112619"></a>

**指标项名称：**SlapdServer服务可用性

**指标项含义：**系统对SlapdServer服务状态进行检查。如果检查结果不正常，则SlapdServer服务不可用。

**恢复指导：**如果该指标项检查结果不正常，原因可能是SlapdServer服务所在节点故障或者SlapdServer进程故障。操作人员进行SlapdServer服务恢复时，请尝试如下操作：

1.  检查SlapdServer服务所在节点是否故障。详细操作请参见告警ALM-12006处理。
2.  检查SlapdServer进程是否正常。详细操作请参见告警ALM-12007处理。

## 服务健康状态<a name="section11000801112620"></a>

**指标项名称：**服务状态

**指标项含义**：系统对LdapServer服务状态进行检查。如果检查结果不正常，则LdapServer服务不可用。

**恢复指导：**如果该指标项检查结果不正常，原因可能是主LdapServer服务所在节点故障或者主LdapServer进程故障。详细操作请参见告警ALM-25000处理。

## 检查告警<a name="section13920206112620"></a>

**指标项名称：**告警信息

**指标项含义**：系统对LdapServer服务的告警信息进行检查。如果存在告警信息，则LdapServer服务可能存在异常。

**恢复指导：**如果该指标项检查结果不正常，建议根据告警内容，查看对应的告警资料，并进行相应的处理。

