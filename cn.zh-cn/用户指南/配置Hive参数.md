# 配置Hive参数<a name="ZH-CN_TOPIC_0175227799"></a>

当MRS服务中默认的参数配置不足以满足用户需要时，用户可以自定义修改参数配置来适应自身需求。

1.  登录集群详情页面，选择“组件管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的![](figures/zh-cn_image_0207903633.png)进行IAM用户同步）。  
    >-   针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理”。  

2.  选择“Hive \> 服务配置”，设置“参数类别”为“全部配置”，进入Hive配置界面修改参数配置。

    **表 1**  Hive参数说明

    <a name="table430163185120"></a>
    <table><thead align="left"><tr id="row2030218315519"><th class="cellrowborder" valign="top" width="39.24392439243925%" id="mcps1.2.4.1.1"><p id="p13021439512"><a name="p13021439512"></a><a name="p13021439512"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="40.32403240324032%" id="mcps1.2.4.1.2"><p id="p123021739518"><a name="p123021739518"></a><a name="p123021739518"></a>参数说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="20.43204320432043%" id="mcps1.2.4.1.3"><p id="p83026314512"><a name="p83026314512"></a><a name="p83026314512"></a>参数值</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row123021438512"><td class="cellrowborder" valign="top" width="39.24392439243925%" headers="mcps1.2.4.1.1 "><p id="p85771584278"><a name="p85771584278"></a><a name="p85771584278"></a>hive.auto.convert.join</p>
    </td>
    <td class="cellrowborder" valign="top" width="40.32403240324032%" headers="mcps1.2.4.1.2 "><p id="p1793160192912"><a name="p1793160192912"></a><a name="p1793160192912"></a>Hive基于输入文件大小将普通join转为mapjoin的开关。</p>
    <p id="p10578155892715"><a name="p10578155892715"></a><a name="p10578155892715"></a>在使用Hive进行联表查询时，若关联的表无大小表的分别（小表数据&lt;24M），建议将此参数值改为false，此参数设置为true执行联表查询时无法生成新的mapjoin。</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.43204320432043%" headers="mcps1.2.4.1.3 "><p id="p857885811274"><a name="p857885811274"></a><a name="p857885811274"></a>取值范围：</p>
    <a name="ul12578135817278"></a><a name="ul12578135817278"></a><ul id="ul12578135817278"><li>true</li><li>false</li></ul>
    <p id="p0578175817271"><a name="p0578175817271"></a><a name="p0578175817271"></a>默认值为true</p>
    </td>
    </tr>
    </tbody>
    </table>


