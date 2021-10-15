# KrbServer健康检查指标项说明<a name="mrs_01_0263"></a>

## KerberosAdmin服务可用性检查<a name="section13031472111847"></a>

**指标项名称：**KerberosAdmin服务可用性

**指标项含义**：系统对KerberosAdmin服务状态进行检查，如果检查结果不正常，则KerberosAdmin服务不可用。

**恢复指导：**如果该指标项检查结果不正常，原因可能是KerberosAdmin服务所在节点故障，或者SlapdServer服务不可用。操作人员进行KerberosAdmin服务恢复时，请尝试如下操作：

1.  检查KerberosAdmin服务所在节点是否故障。
2.  检查SlapdServer服务是否不可用。

## KerberosServer服务可用性检查<a name="section4286505111847"></a>

**指标项名称：**  KerberosServer服务可用性

**指标项含义**：系统对KerberosServer服务状态进行检查，如果检查结果不正常，则KerberosServer服务不可用。

**恢复指导：**如果该指标项检查结果不正常，原因可能是KerberosServer服务所在节点故障，或者SlapdServer服务不可用。操作人员进行KerberosServer服务恢复时，请尝试如下操作：

1.  检查KerberosServer服务所在节点是否故障。
2.  检查SlapdServer服务是否不可用。

## 服务健康状态<a name="section10332115111848"></a>

**指标项名称：**服务状态

**指标项含义**：系统对KrbServer服务状态进行检查，如果检查结果不正常，则KrbServer服务不可用。

**恢复指导：**如果该指标项检查结果不正常，原因可能是KrbServer服务所在节点故障或者LdapServer服务不可用。详细操作请参见告警ALM-25500处理。

## 检查告警<a name="section44007141111848"></a>

**指标项名称：**告警信息

**指标项含义**：系统对KrbServer服务的告警信息进行检查。如果存在告警信息，则KrbServer服务可能存在异常。

**恢复指导：**如果该指标项检查结果不正常，建议根据告警内容，查看对应的告警资料，并进行相应的处理。

