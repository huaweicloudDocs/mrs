# 在Hue WebUI使用文件浏览器<a name="ZH-CN_TOPIC_0173178163"></a>

## 操作场景<a name="s8e39a2a37ddf4c6ea949563aa39df031"></a>

-   针对MRS 1.8.1之前的集群，MRS集群启用Kerberos认证后，用户需要使用图形化界面管理HDFS中文件时，可以通过Hue完成任务。
-   针对MRS 1.8.1及之后的集群，用户需要使用图形化界面管理HDFS中文件时，可以通过Hue完成任务。

## 前提条件<a name="s73e3da43aeec474bb06ff52f70fa8d6b"></a>

启用Kerberos认证时，MRS集群管理员已分配用户在HDFS中查看、创建、修改和删除文件的权限。具体请参见[创建角色](创建角色.md)。

## 访问“File Browser“<a name="section66894515326"></a>

1.  访问Hue WebUI，然后单击“文件浏览器“。
2.  默认进入当前登录用户的主目录。

    “文件浏览器“将显示目录中的子目录或文件以下信息：

    **表 1**  HDFS文件属性介绍

    <a name="table4344895415333"></a>
    <table><thead align="left"><tr id="row4324098615333"><th class="cellrowborder" valign="top" width="30.259999999999998%" id="mcps1.2.3.1.1"><p id="p5244785615333"><a name="p5244785615333"></a><a name="p5244785615333"></a>属性名</p>
    </th>
    <th class="cellrowborder" valign="top" width="69.74000000000001%" id="mcps1.2.3.1.2"><p id="p2041794715333"><a name="p2041794715333"></a><a name="p2041794715333"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3939615315333"><td class="cellrowborder" valign="top" width="30.259999999999998%" headers="mcps1.2.3.1.1 "><p id="p4862183015333"><a name="p4862183015333"></a><a name="p4862183015333"></a><span class="parmname" id="parmname1285896615333"><a name="parmname1285896615333"></a><a name="parmname1285896615333"></a>“名称”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.74000000000001%" headers="mcps1.2.3.1.2 "><p id="p4605411915333"><a name="p4605411915333"></a><a name="p4605411915333"></a>表示目录或文件的名称。</p>
    </td>
    </tr>
    <tr id="row4062230615333"><td class="cellrowborder" valign="top" width="30.259999999999998%" headers="mcps1.2.3.1.1 "><p id="p3697181115333"><a name="p3697181115333"></a><a name="p3697181115333"></a><span class="parmname" id="parmname1902105915333"><a name="parmname1902105915333"></a><a name="parmname1902105915333"></a>“大小”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.74000000000001%" headers="mcps1.2.3.1.2 "><p id="p4192673415333"><a name="p4192673415333"></a><a name="p4192673415333"></a>表示文件的大小。</p>
    </td>
    </tr>
    <tr id="row4137987115333"><td class="cellrowborder" valign="top" width="30.259999999999998%" headers="mcps1.2.3.1.1 "><p id="p207245315333"><a name="p207245315333"></a><a name="p207245315333"></a><span class="parmname" id="parmname3005643415333"><a name="parmname3005643415333"></a><a name="parmname3005643415333"></a>“用户”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.74000000000001%" headers="mcps1.2.3.1.2 "><p id="p3365104215333"><a name="p3365104215333"></a><a name="p3365104215333"></a>表示目录或文件的属主。</p>
    </td>
    </tr>
    <tr id="row5652215215333"><td class="cellrowborder" valign="top" width="30.259999999999998%" headers="mcps1.2.3.1.1 "><p id="p6343523615333"><a name="p6343523615333"></a><a name="p6343523615333"></a><span class="parmname" id="parmname3687452115333"><a name="parmname3687452115333"></a><a name="parmname3687452115333"></a>“组”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.74000000000001%" headers="mcps1.2.3.1.2 "><p id="p3798050615333"><a name="p3798050615333"></a><a name="p3798050615333"></a>表示目录或文件的属组。</p>
    </td>
    </tr>
    <tr id="row6065221515333"><td class="cellrowborder" valign="top" width="30.259999999999998%" headers="mcps1.2.3.1.1 "><p id="p1489163915333"><a name="p1489163915333"></a><a name="p1489163915333"></a><span class="parmname" id="parmname3893732815333"><a name="parmname3893732815333"></a><a name="parmname3893732815333"></a>“权限”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.74000000000001%" headers="mcps1.2.3.1.2 "><p id="p6537214315333"><a name="p6537214315333"></a><a name="p6537214315333"></a>表示目录或文件的权限设置。</p>
    </td>
    </tr>
    <tr id="row1543296115333"><td class="cellrowborder" valign="top" width="30.259999999999998%" headers="mcps1.2.3.1.1 "><p id="p1388235915333"><a name="p1388235915333"></a><a name="p1388235915333"></a><span class="parmname" id="parmname899902415333"><a name="parmname899902415333"></a><a name="parmname899902415333"></a>“日期”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.74000000000001%" headers="mcps1.2.3.1.2 "><p id="p5072930415333"><a name="p5072930415333"></a><a name="p5072930415333"></a>表示目录或文件创建时间。</p>
    </td>
    </tr>
    </tbody>
    </table>

3.  在搜索框输入关键字，系统会自动搜索当前目录搜索目录或文件。
4.  清空搜索框的内容，系统会重新显示所有目录或文件。

## 执行动作<a name="section62998231540"></a>

1.  在“文件浏览器“，选择一个或多个目录或文件。
2.  单击“操作“，在弹出菜单选择一个操作。
    -   “重命名“：表示重新命名一个目录或文件。
    -   “移动“：表示移动文件，在“移至“选择新的目录并单击“移动“完成移动。
    -   “复制“：表示复制选中的文件或目录。
    -   “下载“：表示下载选中的文件。不支持目录。
    -   “更改权限“：表示修改选中目录或文件的访问权限。
        -   可以为属主、属组和其他用户设置“读取“、“写“和“执行“权限。
        -   “易贴“表示禁止HDFS的管理员、目录属主或文件属主以外的用户在目录中删除或移动文件。
        -   “递归“表示递归设置权限到子目录。

    -   “存储策略“：表示设置目录或文件在HDFS中的存储策略。
    -   “Summary“：表示查看选中文件或目录的HDFS存储信息。


## 删除目录或文件<a name="section2334570615428"></a>

1.  在“文件浏览器“，选择一个或多个目录或文件。
2.  单击“移至垃圾桶“，在“确认删除“中单击“是“确认删除并将文件移动到回收站。

    如果需要直接完全删除文件，单击![](figures/icon_mrs_undo1.jpg)并选择“永久删除“。在“确认删除“中单击“是“确认删除。


## 访问其他目录<a name="section4838881415445"></a>

1.  单击目录名并输入需要访问的目录完整路径，例如“/mr-history/tmp“并按回车键进入目录。

    需要当前登录Hue WebUI的用户拥有其他目录的访问权限。

2.  单击“主页“可进入用户的主目录。
3.  单击“历史记录“可以显示最近访问目录的历史记录，并重新访问。
4.  单击“垃圾桶“可以访问当前目录的回收站空间。

    单击“清空垃圾桶“可清空回收站。


## 上传用户文件<a name="section5192645015514"></a>

1.  在“文件浏览器“，单击“上传“。
2.  选择一个操作。
    -   “文件“：表示上传用户文件到当前用户。
    -   “Zip/Tgz/Bz2 file“：表示上传了一个压缩文件，在弹出框单击“Zip, Tgz or Bz2 file“选择需要上传的压缩文件。系统会自动在HDFS中对文件解压。支持“ZIP“、“TGZ“和“BZ2“格式的压缩文件。


## 创建新文件或者目录<a name="section179653215528"></a>

1.  在“文件浏览器“，单击“新建“。
2.  选择一个操作。
    -   “文件“：表示创建一个文件，输入文件名后单击“创建“完成。
    -   “目录“：表示创建一个目录，输入目录名后单击“创建“完成


