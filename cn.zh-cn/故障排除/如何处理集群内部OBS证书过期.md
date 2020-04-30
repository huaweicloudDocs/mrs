# 如何处理集群内部OBS证书过期<a name="ZH-CN_TOPIC_0169495355"></a>

## 用户问题<a name="zh-cn_topic_0137729837_section18305143583116"></a>

用户在MRS集群中访问OBS服务过程中出现证书过期问题。

## 问题现象<a name="zh-cn_topic_0137729837_section117424454313"></a>

用户在MRS集群中访问OBS服务过程中出现证书过期问题，导致访问OBS系统数据失败。

## 原因分析<a name="zh-cn_topic_0137729837_section1237061220324"></a>

OBS系统生成的证书有有效期限制，到达有效期后，服务器端会自动更新证书，从而导致客户端使用老的证书访问OBS系统时出错。

## 处理步骤<a name="zh-cn_topic_0137729837_section520813413313"></a>

通过VNC方式登录集群节点后台，并分别执行如下命令即可。华为云各个Region的配置请参见[表1](#zh-cn_topic_0137729837_table2662184463915)。

```
/opt/Bigdata/jdk/bin/keytool -delete -storepass changeit -alias ${uds_url} -keystore /opt/Bigdata/jdk/jre/lib/security/cacerts || true
```

```
echo | /usr/bin/openssl s_client -connect ${uds_url}:${uds_port} 2>&1 | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > /tmp/obs.pem
```

```
/usr/bin/openssl x509 -in /tmp/obs.pem -text | grep CN
```

```
yes|/opt/Bigdata/jdk/bin/keytool -import -storepass changeit -alias ${uds_url} -keystore /opt/Bigdata/jdk/jre/lib/security/cacerts -file /tmp/obs.pem
```

```
rm -rf /tmp/obs.pem
```

**表 1**  华为云各个Region的配置表

<a name="zh-cn_topic_0137729837_table2662184463915"></a>
<table><thead align="left"><tr id="zh-cn_topic_0137729837_row8664204417398"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0137729837_p13664184463917"><a name="zh-cn_topic_0137729837_p13664184463917"></a><a name="zh-cn_topic_0137729837_p13664184463917"></a>Region</p>
</th>
<th class="cellrowborder" valign="top" width="33.3033303330333%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0137729837_p36641044183917"><a name="zh-cn_topic_0137729837_p36641044183917"></a><a name="zh-cn_topic_0137729837_p36641044183917"></a>uds_url</p>
</th>
<th class="cellrowborder" valign="top" width="33.36333633363336%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0137729837_p4664144203910"><a name="zh-cn_topic_0137729837_p4664144203910"></a><a name="zh-cn_topic_0137729837_p4664144203910"></a>uds_port</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0137729837_row156642441396"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0137729837_p1197013324417"><a name="zh-cn_topic_0137729837_p1197013324417"></a><a name="zh-cn_topic_0137729837_p1197013324417"></a>华北-北京一</p>
</td>
<td class="cellrowborder" valign="top" width="33.3033303330333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0137729837_p12972125465712"><a name="zh-cn_topic_0137729837_p12972125465712"></a><a name="zh-cn_topic_0137729837_p12972125465712"></a>obs.cn-north-1.myhuaweicloud.com</p>
</td>
<td class="cellrowborder" valign="top" width="33.36333633363336%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0137729837_p1697053224114"><a name="zh-cn_topic_0137729837_p1697053224114"></a><a name="zh-cn_topic_0137729837_p1697053224114"></a>443</p>
</td>
</tr>
<tr id="zh-cn_topic_0137729837_row1919819422246"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0137729837_p1198542152413"><a name="zh-cn_topic_0137729837_p1198542152413"></a><a name="zh-cn_topic_0137729837_p1198542152413"></a>华北-北京四</p>
</td>
<td class="cellrowborder" valign="top" width="33.3033303330333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0137729837_p560303135811"><a name="zh-cn_topic_0137729837_p560303135811"></a><a name="zh-cn_topic_0137729837_p560303135811"></a>obs.cn-north-4.myhuaweicloud.com</p>
</td>
<td class="cellrowborder" valign="top" width="33.36333633363336%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0137729837_p19198104216248"><a name="zh-cn_topic_0137729837_p19198104216248"></a><a name="zh-cn_topic_0137729837_p19198104216248"></a>443</p>
</td>
</tr>
<tr id="zh-cn_topic_0137729837_row115568202502"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0137729837_p255662065010"><a name="zh-cn_topic_0137729837_p255662065010"></a><a name="zh-cn_topic_0137729837_p255662065010"></a><span>华东-上海一</span></p>
</td>
<td class="cellrowborder" valign="top" width="33.3033303330333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0137729837_p1755632055017"><a name="zh-cn_topic_0137729837_p1755632055017"></a><a name="zh-cn_topic_0137729837_p1755632055017"></a>obs.cn-east-3.myhuaweicloud.com</p>
</td>
<td class="cellrowborder" valign="top" width="33.36333633363336%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0137729837_p75561920125017"><a name="zh-cn_topic_0137729837_p75561920125017"></a><a name="zh-cn_topic_0137729837_p75561920125017"></a>443</p>
</td>
</tr>
<tr id="zh-cn_topic_0137729837_row3664944153918"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0137729837_p12971163212418"><a name="zh-cn_topic_0137729837_p12971163212418"></a><a name="zh-cn_topic_0137729837_p12971163212418"></a><span>华东-上海二</span></p>
</td>
<td class="cellrowborder" valign="top" width="33.3033303330333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0137729837_p588242011212"><a name="zh-cn_topic_0137729837_p588242011212"></a><a name="zh-cn_topic_0137729837_p588242011212"></a>obs.cn-east-2.myhuaweicloud.com</p>
</td>
<td class="cellrowborder" valign="top" width="33.36333633363336%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0137729837_p159711732154118"><a name="zh-cn_topic_0137729837_p159711732154118"></a><a name="zh-cn_topic_0137729837_p159711732154118"></a>443</p>
</td>
</tr>
<tr id="zh-cn_topic_0137729837_row266411445396"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0137729837_p097115320410"><a name="zh-cn_topic_0137729837_p097115320410"></a><a name="zh-cn_topic_0137729837_p097115320410"></a><span>华南-广州</span></p>
</td>
<td class="cellrowborder" valign="top" width="33.3033303330333%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0137729837_p720917281427"><a name="zh-cn_topic_0137729837_p720917281427"></a><a name="zh-cn_topic_0137729837_p720917281427"></a>obs.cn-south-1.myhuaweicloud.com</p>
</td>
<td class="cellrowborder" valign="top" width="33.36333633363336%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0137729837_p197103234113"><a name="zh-cn_topic_0137729837_p197103234113"></a><a name="zh-cn_topic_0137729837_p197103234113"></a>443</p>
</td>
</tr>
</tbody>
</table>

