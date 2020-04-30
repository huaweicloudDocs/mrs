# 使用AK/SK获取MRS集群主机列表接口时提示用户无权限“User do not have right to access cluster”<a name="ZH-CN_TOPIC_0242024827"></a>

## 用户问题<a name="section18305143583116"></a>

使用AK/SK获取MRS集群主机列表/v1.1/<project\_id\>/clusters/<cluster\_id\>/hosts接口时，提示用户无权限“**User do not have right to access cluster**”

## 原因分析<a name="section1237061220324"></a>

客户使用AK/SK获取MRS集群主机列表时，请求头中未填充project\_id等参数导致云服务解析token的project\_id与集群的project\_id不符合提示无权限.。

## 处理步骤<a name="section31942855213"></a>

在使用AK/SK认证方式调用接口前，请参见[表1](#table34654407475)收集对应信息，详细的签名方法和SDK使用方法请参见[API签名指南](https://support.huaweicloud.com/devg-apisign/api-sign-provide.html)。

在构造API请求前，我们需要获取以下信息，包括组成请求URL的Endpoint和URI，用于签名和认证的AK/SK，用于区分租户的项目ID。

**表 1**  表1 信息收集项

<a name="table34654407475"></a>
<table><thead align="left"></thead>
<tbody><tr id="row13522184016478"><td class="cellrowborder" valign="top" width="23.400000000000002%"><p id="p9522154064716"><a name="p9522154064716"></a><a name="p9522154064716"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="76.6%"><p id="p3522144054720"><a name="p3522144054720"></a><a name="p3522144054720"></a>地区与终端节点，即云服务在不同Region有不同的访问域名。</p>
<p id="p452215403477"><a name="p452215403477"></a><a name="p452215403477"></a>获取方式请参考<a href="https://developer.huaweicloud.com/endpoint?MRS" target="_blank" rel="noopener noreferrer">终端节点及区域</a>。</p>
</td>
</tr>
<tr id="row45222040174711"><td class="cellrowborder" valign="top" width="23.400000000000002%"><p id="p1352254015478"><a name="p1352254015478"></a><a name="p1352254015478"></a>Project_Id</p>
</td>
<td class="cellrowborder" valign="top" width="76.6%"><p id="p15221940184718"><a name="p15221940184718"></a><a name="p15221940184718"></a>项目ID，在大多数API接口调用时需要配置在uri中，用以识别不同的项目。</p>
</td>
</tr>
<tr id="row1752217405473"><td class="cellrowborder" valign="top" width="23.400000000000002%"><p id="p1452234024718"><a name="p1452234024718"></a><a name="p1452234024718"></a>AK/SK</p>
</td>
<td class="cellrowborder" valign="top" width="76.6%"><p id="p1752218408478"><a name="p1752218408478"></a><a name="p1752218408478"></a>访问密钥对，包含密钥ID与密钥。AK/SK用于对请求内容进行签名。</p>
</td>
</tr>
<tr id="row7522940154714"><td class="cellrowborder" valign="top" width="23.400000000000002%"><p id="p75221440174716"><a name="p75221440174716"></a><a name="p75221440174716"></a>URI</p>
</td>
<td class="cellrowborder" valign="top" width="76.6%"><p id="p3522740134716"><a name="p3522740134716"></a><a name="p3522740134716"></a>API接口的调用路径及参数。</p>
<p id="p35221540104719"><a name="p35221540104719"></a><a name="p35221540104719"></a>请参考各云服务的详细接口章节获取，MRS的接口请参考<a href="https://support.huaweicloud.com/api-mrs/mrs_02_0007.html" target="_blank" rel="noopener noreferrer">API概览</a>。</p>
</td>
</tr>
<tr id="row4522134017476"><td class="cellrowborder" valign="top" width="23.400000000000002%"><p id="p352213401473"><a name="p352213401473"></a><a name="p352213401473"></a>X-Domain-Id</p>
</td>
<td class="cellrowborder" valign="top" width="76.6%"><p id="p115221640104716"><a name="p115221640104716"></a><a name="p115221640104716"></a>账号ID，用途：</p>
<a name="ul652274084712"></a><a name="ul652274084712"></a><ul id="ul652274084712"><li>Token认证方式下获取Token。</li><li>AK/SK认证方式下，全局服务的接口调用，需在请求消息头中配置X-Domain-Id。</li></ul>
</td>
</tr>
<tr id="row752214014474"><td class="cellrowborder" valign="top" width="23.400000000000002%"><p id="p0522440194711"><a name="p0522440194711"></a><a name="p0522440194711"></a>X-Project-Id</p>
</td>
<td class="cellrowborder" valign="top" width="76.6%"><p id="p252224044713"><a name="p252224044713"></a><a name="p252224044713"></a>子项目ID，在多项目场景中使用。如果云服务资源创建在子项目中，AK/SK认证方式下，操作该资源的接口调用需要在请求消息头中携带X-Project-Id。</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：**   
>[表1](#table34654407475)中参数的获取方式请参见[API签名指南](https://support.huaweicloud.com/devg-apisign/api-sign-provide.html)。  

