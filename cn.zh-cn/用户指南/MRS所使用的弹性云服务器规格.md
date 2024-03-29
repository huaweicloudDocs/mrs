# MRS所使用的弹性云服务器规格<a name="mrs_01_9006"></a>

针对不同的应用场景，MRS使用到如下类型的弹性云服务器。

-   通用计算型（S3型）
-   通用计算增强型（C3型）
-   通用计算增强型（C6型）
-   磁盘增强型（D2型）
-   磁盘增强型（D3型）
-   通用网络增强型（C3ne型）
-   高性能计算型（Hc2）
-   内存优化型（M3）
-   内存优化型（M6）
-   鲲鹏通用计算增强型（KC1型）
-   鲲鹏内存优化型（KM1型）
-   鲲鹏内存优化型（KI1型）
-   超高I/O型（I3型）
-   超高I/O型（IR3型）
-   GPU计算加速型（P1型）

## 规格命名规则<a name="zh-cn_topic_0179742194_section741930611313"></a>

AB.C.D

例如m2.8xlarge.8

其中，

-   A表示系列，例如：s表示通用型、c表示计算型、m表示内存型。
-   B表示系列号，例如：s1中的1表示通用型I代，s2中2表示通用型II代。
-   C表示规格，当前系列中的规格大小，例如：medium、large、xlarge。
-   D表示内存、CPU比，以具体数字表示，例如4表示内存和CPU的比值为4。

## 规格<a name="zh-cn_topic_0179742194_section1399585312355"></a>

**表 1**  通用计算型弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table367241161115"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row118484141119"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p1392144120110"><a name="zh-cn_topic_0179742194_p1392144120110"></a><a name="zh-cn_topic_0179742194_p1392144120110"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p1296184111116"><a name="zh-cn_topic_0179742194_p1296184111116"></a><a name="zh-cn_topic_0179742194_p1296184111116"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p149884171118"><a name="zh-cn_topic_0179742194_p149884171118"></a><a name="zh-cn_topic_0179742194_p149884171118"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p10102241121115"><a name="zh-cn_topic_0179742194_p10102241121115"></a><a name="zh-cn_topic_0179742194_p10102241121115"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p8104154117112"><a name="zh-cn_topic_0179742194_p8104154117112"></a><a name="zh-cn_topic_0179742194_p8104154117112"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row6824183441213"><td class="cellrowborder" rowspan="5" valign="top" width="23%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p13262641141118"><a name="zh-cn_topic_0179742194_p13262641141118"></a><a name="zh-cn_topic_0179742194_p13262641141118"></a>S3型</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p13825934151213"><a name="zh-cn_topic_0179742194_p13825934151213"></a><a name="zh-cn_topic_0179742194_p13825934151213"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p082519344126"><a name="zh-cn_topic_0179742194_p082519344126"></a><a name="zh-cn_topic_0179742194_p082519344126"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1382519342127"><a name="zh-cn_topic_0179742194_p1382519342127"></a><a name="zh-cn_topic_0179742194_p1382519342127"></a>s3.xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p138255348122"><a name="zh-cn_topic_0179742194_p138255348122"></a><a name="zh-cn_topic_0179742194_p138255348122"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1526034121120"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p1426584111112"><a name="zh-cn_topic_0179742194_p1426584111112"></a><a name="zh-cn_topic_0179742194_p1426584111112"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p18267641151119"><a name="zh-cn_topic_0179742194_p18267641151119"></a><a name="zh-cn_topic_0179742194_p18267641151119"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p7276144151114"><a name="zh-cn_topic_0179742194_p7276144151114"></a><a name="zh-cn_topic_0179742194_p7276144151114"></a>s3.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p82781241141113"><a name="zh-cn_topic_0179742194_p82781241141113"></a><a name="zh-cn_topic_0179742194_p82781241141113"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row927914181116"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p5282641141114"><a name="zh-cn_topic_0179742194_p5282641141114"></a><a name="zh-cn_topic_0179742194_p5282641141114"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p828624161118"><a name="zh-cn_topic_0179742194_p828624161118"></a><a name="zh-cn_topic_0179742194_p828624161118"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p128818412119"><a name="zh-cn_topic_0179742194_p128818412119"></a><a name="zh-cn_topic_0179742194_p128818412119"></a>s3.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p52926415112"><a name="zh-cn_topic_0179742194_p52926415112"></a><a name="zh-cn_topic_0179742194_p52926415112"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row429419419110"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p3296154118111"><a name="zh-cn_topic_0179742194_p3296154118111"></a><a name="zh-cn_topic_0179742194_p3296154118111"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p430014120119"><a name="zh-cn_topic_0179742194_p430014120119"></a><a name="zh-cn_topic_0179742194_p430014120119"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1830394111118"><a name="zh-cn_topic_0179742194_p1830394111118"></a><a name="zh-cn_topic_0179742194_p1830394111118"></a>s3.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p4306441141111"><a name="zh-cn_topic_0179742194_p4306441141111"></a><a name="zh-cn_topic_0179742194_p4306441141111"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row830924116119"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p153121419112"><a name="zh-cn_topic_0179742194_p153121419112"></a><a name="zh-cn_topic_0179742194_p153121419112"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1731594114111"><a name="zh-cn_topic_0179742194_p1731594114111"></a><a name="zh-cn_topic_0179742194_p1731594114111"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p53190411111"><a name="zh-cn_topic_0179742194_p53190411111"></a><a name="zh-cn_topic_0179742194_p53190411111"></a>s3.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p73241541141118"><a name="zh-cn_topic_0179742194_p73241541141118"></a><a name="zh-cn_topic_0179742194_p73241541141118"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 2**  通用计算增强型（C3型）弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table3949605220464"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row5755737620464"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p32920979204624"><a name="zh-cn_topic_0179742194_p32920979204624"></a><a name="zh-cn_topic_0179742194_p32920979204624"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p41529665204624"><a name="zh-cn_topic_0179742194_p41529665204624"></a><a name="zh-cn_topic_0179742194_p41529665204624"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p9028760204624"><a name="zh-cn_topic_0179742194_p9028760204624"></a><a name="zh-cn_topic_0179742194_p9028760204624"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p5297585204624"><a name="zh-cn_topic_0179742194_p5297585204624"></a><a name="zh-cn_topic_0179742194_p5297585204624"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p84201252123120"><a name="zh-cn_topic_0179742194_p84201252123120"></a><a name="zh-cn_topic_0179742194_p84201252123120"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row2115659920464"><td class="cellrowborder" rowspan="7" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p1639654719185"><a name="zh-cn_topic_0179742194_p1639654719185"></a><a name="zh-cn_topic_0179742194_p1639654719185"></a>C3型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p54672497204624"><a name="zh-cn_topic_0179742194_p54672497204624"></a><a name="zh-cn_topic_0179742194_p54672497204624"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p66396173204624"><a name="zh-cn_topic_0179742194_p66396173204624"></a><a name="zh-cn_topic_0179742194_p66396173204624"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p9380900204624"><a name="zh-cn_topic_0179742194_p9380900204624"></a><a name="zh-cn_topic_0179742194_p9380900204624"></a>c3.xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p714614176327"><a name="zh-cn_topic_0179742194_p714614176327"></a><a name="zh-cn_topic_0179742194_p714614176327"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1339712614367"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p10361184613360"><a name="zh-cn_topic_0179742194_p10361184613360"></a><a name="zh-cn_topic_0179742194_p10361184613360"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1036104612367"><a name="zh-cn_topic_0179742194_p1036104612367"></a><a name="zh-cn_topic_0179742194_p1036104612367"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p8361104613610"><a name="zh-cn_topic_0179742194_p8361104613610"></a><a name="zh-cn_topic_0179742194_p8361104613610"></a>c3.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p9361114613616"><a name="zh-cn_topic_0179742194_p9361114613616"></a><a name="zh-cn_topic_0179742194_p9361114613616"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row58396907204611"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p15110173204624"><a name="zh-cn_topic_0179742194_p15110173204624"></a><a name="zh-cn_topic_0179742194_p15110173204624"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p15964478204624"><a name="zh-cn_topic_0179742194_p15964478204624"></a><a name="zh-cn_topic_0179742194_p15964478204624"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p18054373204624"><a name="zh-cn_topic_0179742194_p18054373204624"></a><a name="zh-cn_topic_0179742194_p18054373204624"></a>c3.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1160181710322"><a name="zh-cn_topic_0179742194_p1160181710322"></a><a name="zh-cn_topic_0179742194_p1160181710322"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row19288388204611"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p8300597204624"><a name="zh-cn_topic_0179742194_p8300597204624"></a><a name="zh-cn_topic_0179742194_p8300597204624"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1259733204624"><a name="zh-cn_topic_0179742194_p1259733204624"></a><a name="zh-cn_topic_0179742194_p1259733204624"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p34929558204624"><a name="zh-cn_topic_0179742194_p34929558204624"></a><a name="zh-cn_topic_0179742194_p34929558204624"></a>c3.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p11163171763213"><a name="zh-cn_topic_0179742194_p11163171763213"></a><a name="zh-cn_topic_0179742194_p11163171763213"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row39706029204611"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p29388703204624"><a name="zh-cn_topic_0179742194_p29388703204624"></a><a name="zh-cn_topic_0179742194_p29388703204624"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p31674728204624"><a name="zh-cn_topic_0179742194_p31674728204624"></a><a name="zh-cn_topic_0179742194_p31674728204624"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p15516174204624"><a name="zh-cn_topic_0179742194_p15516174204624"></a><a name="zh-cn_topic_0179742194_p15516174204624"></a>c3.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p14657219153217"><a name="zh-cn_topic_0179742194_p14657219153217"></a><a name="zh-cn_topic_0179742194_p14657219153217"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row4280432102715"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p19281183210278"><a name="zh-cn_topic_0179742194_p19281183210278"></a><a name="zh-cn_topic_0179742194_p19281183210278"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p128123211279"><a name="zh-cn_topic_0179742194_p128123211279"></a><a name="zh-cn_topic_0179742194_p128123211279"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p374558192715"><a name="zh-cn_topic_0179742194_p374558192715"></a><a name="zh-cn_topic_0179742194_p374558192715"></a>c3.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p14281153262720"><a name="zh-cn_topic_0179742194_p14281153262720"></a><a name="zh-cn_topic_0179742194_p14281153262720"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row28491536204611"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p42717549204624"><a name="zh-cn_topic_0179742194_p42717549204624"></a><a name="zh-cn_topic_0179742194_p42717549204624"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p37569478204624"><a name="zh-cn_topic_0179742194_p37569478204624"></a><a name="zh-cn_topic_0179742194_p37569478204624"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p23228883204624"><a name="zh-cn_topic_0179742194_p23228883204624"></a><a name="zh-cn_topic_0179742194_p23228883204624"></a>c3.15xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p16664419133218"><a name="zh-cn_topic_0179742194_p16664419133218"></a><a name="zh-cn_topic_0179742194_p16664419133218"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 3**  通用计算增强型（C6型）弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table411191891715"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row311201817172"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p10112018181719"><a name="zh-cn_topic_0179742194_p10112018181719"></a><a name="zh-cn_topic_0179742194_p10112018181719"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p2011121811173"><a name="zh-cn_topic_0179742194_p2011121811173"></a><a name="zh-cn_topic_0179742194_p2011121811173"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p1611818161715"><a name="zh-cn_topic_0179742194_p1611818161715"></a><a name="zh-cn_topic_0179742194_p1611818161715"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p91161851716"><a name="zh-cn_topic_0179742194_p91161851716"></a><a name="zh-cn_topic_0179742194_p91161851716"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p101261811171"><a name="zh-cn_topic_0179742194_p101261811171"></a><a name="zh-cn_topic_0179742194_p101261811171"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row11121918131713"><td class="cellrowborder" rowspan="9" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p112191881716"><a name="zh-cn_topic_0179742194_p112191881716"></a><a name="zh-cn_topic_0179742194_p112191881716"></a>C6型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p212518181719"><a name="zh-cn_topic_0179742194_p212518181719"></a><a name="zh-cn_topic_0179742194_p212518181719"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p312131841719"><a name="zh-cn_topic_0179742194_p312131841719"></a><a name="zh-cn_topic_0179742194_p312131841719"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1712818131711"><a name="zh-cn_topic_0179742194_p1712818131711"></a><a name="zh-cn_topic_0179742194_p1712818131711"></a>c6.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p111291851716"><a name="zh-cn_topic_0179742194_p111291851716"></a><a name="zh-cn_topic_0179742194_p111291851716"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row141214189172"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p912191881717"><a name="zh-cn_topic_0179742194_p912191881717"></a><a name="zh-cn_topic_0179742194_p912191881717"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p31215184178"><a name="zh-cn_topic_0179742194_p31215184178"></a><a name="zh-cn_topic_0179742194_p31215184178"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1923613583201"><a name="zh-cn_topic_0179742194_p1923613583201"></a><a name="zh-cn_topic_0179742194_p1923613583201"></a>c6.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1412111814177"><a name="zh-cn_topic_0179742194_p1412111814177"></a><a name="zh-cn_topic_0179742194_p1412111814177"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1912111816175"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p91219182173"><a name="zh-cn_topic_0179742194_p91219182173"></a><a name="zh-cn_topic_0179742194_p91219182173"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p131210187171"><a name="zh-cn_topic_0179742194_p131210187171"></a><a name="zh-cn_topic_0179742194_p131210187171"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1626385818209"><a name="zh-cn_topic_0179742194_p1626385818209"></a><a name="zh-cn_topic_0179742194_p1626385818209"></a>c6.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p31291871712"><a name="zh-cn_topic_0179742194_p31291871712"></a><a name="zh-cn_topic_0179742194_p31291871712"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row712718101714"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p9121918151715"><a name="zh-cn_topic_0179742194_p9121918151715"></a><a name="zh-cn_topic_0179742194_p9121918151715"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p19121018201710"><a name="zh-cn_topic_0179742194_p19121018201710"></a><a name="zh-cn_topic_0179742194_p19121018201710"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p72931858132018"><a name="zh-cn_topic_0179742194_p72931858132018"></a><a name="zh-cn_topic_0179742194_p72931858132018"></a>c6.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p11121918181715"><a name="zh-cn_topic_0179742194_p11121918181715"></a><a name="zh-cn_topic_0179742194_p11121918181715"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row16121186175"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p913818191716"><a name="zh-cn_topic_0179742194_p913818191716"></a><a name="zh-cn_topic_0179742194_p913818191716"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p513131881711"><a name="zh-cn_topic_0179742194_p513131881711"></a><a name="zh-cn_topic_0179742194_p513131881711"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p133191158102012"><a name="zh-cn_topic_0179742194_p133191158102012"></a><a name="zh-cn_topic_0179742194_p133191158102012"></a>c6.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p201312183176"><a name="zh-cn_topic_0179742194_p201312183176"></a><a name="zh-cn_topic_0179742194_p201312183176"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1513418131712"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p20131518131719"><a name="zh-cn_topic_0179742194_p20131518131719"></a><a name="zh-cn_topic_0179742194_p20131518131719"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1913818151717"><a name="zh-cn_topic_0179742194_p1913818151717"></a><a name="zh-cn_topic_0179742194_p1913818151717"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p183451658182010"><a name="zh-cn_topic_0179742194_p183451658182010"></a><a name="zh-cn_topic_0179742194_p183451658182010"></a>c6.8xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p9131118141712"><a name="zh-cn_topic_0179742194_p9131118141712"></a><a name="zh-cn_topic_0179742194_p9131118141712"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row131311188175"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p813131811175"><a name="zh-cn_topic_0179742194_p813131811175"></a><a name="zh-cn_topic_0179742194_p813131811175"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1613191811710"><a name="zh-cn_topic_0179742194_p1613191811710"></a><a name="zh-cn_topic_0179742194_p1613191811710"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1837219582205"><a name="zh-cn_topic_0179742194_p1837219582205"></a><a name="zh-cn_topic_0179742194_p1837219582205"></a>c6.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1413418151717"><a name="zh-cn_topic_0179742194_p1413418151717"></a><a name="zh-cn_topic_0179742194_p1413418151717"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row796192511917"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p13961182531913"><a name="zh-cn_topic_0179742194_p13961182531913"></a><a name="zh-cn_topic_0179742194_p13961182531913"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p2961425181912"><a name="zh-cn_topic_0179742194_p2961425181912"></a><a name="zh-cn_topic_0179742194_p2961425181912"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p14400175802019"><a name="zh-cn_topic_0179742194_p14400175802019"></a><a name="zh-cn_topic_0179742194_p14400175802019"></a>c6.16xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p105993882011"><a name="zh-cn_topic_0179742194_p105993882011"></a><a name="zh-cn_topic_0179742194_p105993882011"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row196071326111916"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p26083267191"><a name="zh-cn_topic_0179742194_p26083267191"></a><a name="zh-cn_topic_0179742194_p26083267191"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p9608142615197"><a name="zh-cn_topic_0179742194_p9608142615197"></a><a name="zh-cn_topic_0179742194_p9608142615197"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p942725814206"><a name="zh-cn_topic_0179742194_p942725814206"></a><a name="zh-cn_topic_0179742194_p942725814206"></a>c6.16xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p5306129112013"><a name="zh-cn_topic_0179742194_p5306129112013"></a><a name="zh-cn_topic_0179742194_p5306129112013"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 4**  磁盘增强型型弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table47541937112515"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row1775413371257"><th class="cellrowborder" valign="top" width="18.17818218178182%" id="mcps1.2.7.1.1"><p id="zh-cn_topic_0179742194_p17228105016252"><a name="zh-cn_topic_0179742194_p17228105016252"></a><a name="zh-cn_topic_0179742194_p17228105016252"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="13.638636136386362%" id="mcps1.2.7.1.2"><p id="zh-cn_topic_0179742194_p123165013254"><a name="zh-cn_topic_0179742194_p123165013254"></a><a name="zh-cn_topic_0179742194_p123165013254"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="13.638636136386362%" id="mcps1.2.7.1.3"><p id="zh-cn_topic_0179742194_p7236185013252"><a name="zh-cn_topic_0179742194_p7236185013252"></a><a name="zh-cn_topic_0179742194_p7236185013252"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="27.267273272672732%" id="mcps1.2.7.1.4"><p id="zh-cn_topic_0179742194_p18237155062514"><a name="zh-cn_topic_0179742194_p18237155062514"></a><a name="zh-cn_topic_0179742194_p18237155062514"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="13.638636136386362%" id="mcps1.2.7.1.5"><p id="zh-cn_topic_0179742194_p724035017257"><a name="zh-cn_topic_0179742194_p724035017257"></a><a name="zh-cn_topic_0179742194_p724035017257"></a>虚拟化类型</p>
</th>
<th class="cellrowborder" valign="top" width="13.638636136386362%" id="mcps1.2.7.1.6"><p id="zh-cn_topic_0179742194_p1624105092519"><a name="zh-cn_topic_0179742194_p1624105092519"></a><a name="zh-cn_topic_0179742194_p1624105092519"></a>本地盘（GB）</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row974834394812"><td class="cellrowborder" rowspan="3" valign="top" width="18.17818218178182%" headers="mcps1.2.7.1.1 "><p id="zh-cn_topic_0179742194_p9760548192919"><a name="zh-cn_topic_0179742194_p9760548192919"></a><a name="zh-cn_topic_0179742194_p9760548192919"></a>D2型</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.2 "><p id="zh-cn_topic_0179742194_p12750124311482"><a name="zh-cn_topic_0179742194_p12750124311482"></a><a name="zh-cn_topic_0179742194_p12750124311482"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.3 "><p id="zh-cn_topic_0179742194_p0750164314813"><a name="zh-cn_topic_0179742194_p0750164314813"></a><a name="zh-cn_topic_0179742194_p0750164314813"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="27.267273272672732%" headers="mcps1.2.7.1.4 "><p id="zh-cn_topic_0179742194_p1175054394818"><a name="zh-cn_topic_0179742194_p1175054394818"></a><a name="zh-cn_topic_0179742194_p1175054394818"></a>d2.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.5 "><p id="zh-cn_topic_0179742194_p1875013430483"><a name="zh-cn_topic_0179742194_p1875013430483"></a><a name="zh-cn_topic_0179742194_p1875013430483"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.6 "><p id="zh-cn_topic_0179742194_p17750443104811"><a name="zh-cn_topic_0179742194_p17750443104811"></a><a name="zh-cn_topic_0179742194_p17750443104811"></a>4×1800</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row14967171717297"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="zh-cn_topic_0179742194_p1492123262911"><a name="zh-cn_topic_0179742194_p1492123262911"></a><a name="zh-cn_topic_0179742194_p1492123262911"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="zh-cn_topic_0179742194_p18434144113294"><a name="zh-cn_topic_0179742194_p18434144113294"></a><a name="zh-cn_topic_0179742194_p18434144113294"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="zh-cn_topic_0179742194_p196727215299"><a name="zh-cn_topic_0179742194_p196727215299"></a><a name="zh-cn_topic_0179742194_p196727215299"></a>d2.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="zh-cn_topic_0179742194_p10967117172915"><a name="zh-cn_topic_0179742194_p10967117172915"></a><a name="zh-cn_topic_0179742194_p10967117172915"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="zh-cn_topic_0179742194_p169678175293"><a name="zh-cn_topic_0179742194_p169678175293"></a><a name="zh-cn_topic_0179742194_p169678175293"></a>8×1800</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row575615372253"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="zh-cn_topic_0179742194_p692123252911"><a name="zh-cn_topic_0179742194_p692123252911"></a><a name="zh-cn_topic_0179742194_p692123252911"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="zh-cn_topic_0179742194_p13434174116295"><a name="zh-cn_topic_0179742194_p13434174116295"></a><a name="zh-cn_topic_0179742194_p13434174116295"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="zh-cn_topic_0179742194_p1667222172917"><a name="zh-cn_topic_0179742194_p1667222172917"></a><a name="zh-cn_topic_0179742194_p1667222172917"></a>d2.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="zh-cn_topic_0179742194_p10756133715250"><a name="zh-cn_topic_0179742194_p10756133715250"></a><a name="zh-cn_topic_0179742194_p10756133715250"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="zh-cn_topic_0179742194_p1675663717258"><a name="zh-cn_topic_0179742194_p1675663717258"></a><a name="zh-cn_topic_0179742194_p1675663717258"></a>16×1800</p>
</td>
</tr>
<tr id="row11239134132819"><td class="cellrowborder" rowspan="4" valign="top" width="18.17818218178182%" headers="mcps1.2.7.1.1 "><p id="p31021947131216"><a name="p31021947131216"></a><a name="p31021947131216"></a>D3型</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.2 "><p id="p1324004112811"><a name="p1324004112811"></a><a name="p1324004112811"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.3 "><p id="p72405452810"><a name="p72405452810"></a><a name="p72405452810"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="27.267273272672732%" headers="mcps1.2.7.1.4 "><p id="p8240642281"><a name="p8240642281"></a><a name="p8240642281"></a>d3.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.5 "><p id="p1424012412289"><a name="p1424012412289"></a><a name="p1424012412289"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.6 "><p id="p324010472813"><a name="p324010472813"></a><a name="p324010472813"></a>4 × 1800</p>
</td>
</tr>
<tr id="row125009612283"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="p35002617286"><a name="p35002617286"></a><a name="p35002617286"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="p05003612816"><a name="p05003612816"></a><a name="p05003612816"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="p150019662813"><a name="p150019662813"></a><a name="p150019662813"></a>d3.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="p85001668282"><a name="p85001668282"></a><a name="p85001668282"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="p1350166122810"><a name="p1350166122810"></a><a name="p1350166122810"></a>8 × 1800</p>
</td>
</tr>
<tr id="row719315011242"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="p519450192418"><a name="p519450192418"></a><a name="p519450192418"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="p151941505244"><a name="p151941505244"></a><a name="p151941505244"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="p18195500249"><a name="p18195500249"></a><a name="p18195500249"></a>d3.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="p4195405249"><a name="p4195405249"></a><a name="p4195405249"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="p18195140142419"><a name="p18195140142419"></a><a name="p18195140142419"></a>16 × 1800</p>
</td>
</tr>
<tr id="row0388189112812"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="p03885920286"><a name="p03885920286"></a><a name="p03885920286"></a>56</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="p338969102819"><a name="p338969102819"></a><a name="p338969102819"></a>560</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="p1038913922814"><a name="p1038913922814"></a><a name="p1038913922814"></a>d3.14xlarge.10.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="p17389191280"><a name="p17389191280"></a><a name="p17389191280"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="p23899916282"><a name="p23899916282"></a><a name="p23899916282"></a>28 × 1800</p>
</td>
</tr>
</tbody>
</table>

**表 5**  通用网络增强型（C3ne型）弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table11476142712139"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row248302717130"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p18485182714134"><a name="zh-cn_topic_0179742194_p18485182714134"></a><a name="zh-cn_topic_0179742194_p18485182714134"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p6486327141310"><a name="zh-cn_topic_0179742194_p6486327141310"></a><a name="zh-cn_topic_0179742194_p6486327141310"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p1548752701319"><a name="zh-cn_topic_0179742194_p1548752701319"></a><a name="zh-cn_topic_0179742194_p1548752701319"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p144891327201312"><a name="zh-cn_topic_0179742194_p144891327201312"></a><a name="zh-cn_topic_0179742194_p144891327201312"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p8491182781311"><a name="zh-cn_topic_0179742194_p8491182781311"></a><a name="zh-cn_topic_0179742194_p8491182781311"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row19592290395"><td class="cellrowborder" rowspan="7" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p18577182810127"><a name="zh-cn_topic_0179742194_p18577182810127"></a><a name="zh-cn_topic_0179742194_p18577182810127"></a>C3ne型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p16960192919392"><a name="zh-cn_topic_0179742194_p16960192919392"></a><a name="zh-cn_topic_0179742194_p16960192919392"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p796082910391"><a name="zh-cn_topic_0179742194_p796082910391"></a><a name="zh-cn_topic_0179742194_p796082910391"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p19609298391"><a name="zh-cn_topic_0179742194_p19609298391"></a><a name="zh-cn_topic_0179742194_p19609298391"></a>c3ne.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p79601729193912"><a name="zh-cn_topic_0179742194_p79601729193912"></a><a name="zh-cn_topic_0179742194_p79601729193912"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row13366357164315"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p336615713438"><a name="zh-cn_topic_0179742194_p336615713438"></a><a name="zh-cn_topic_0179742194_p336615713438"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p8366857194320"><a name="zh-cn_topic_0179742194_p8366857194320"></a><a name="zh-cn_topic_0179742194_p8366857194320"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p236645714431"><a name="zh-cn_topic_0179742194_p236645714431"></a><a name="zh-cn_topic_0179742194_p236645714431"></a>c3ne.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1366195712438"><a name="zh-cn_topic_0179742194_p1366195712438"></a><a name="zh-cn_topic_0179742194_p1366195712438"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row44931727151314"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p10334247131610"><a name="zh-cn_topic_0179742194_p10334247131610"></a><a name="zh-cn_topic_0179742194_p10334247131610"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1133444771614"><a name="zh-cn_topic_0179742194_p1133444771614"></a><a name="zh-cn_topic_0179742194_p1133444771614"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p649832715135"><a name="zh-cn_topic_0179742194_p649832715135"></a><a name="zh-cn_topic_0179742194_p649832715135"></a>c3ne.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p3500627141315"><a name="zh-cn_topic_0179742194_p3500627141315"></a><a name="zh-cn_topic_0179742194_p3500627141315"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row15500827171318"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p2033214721612"><a name="zh-cn_topic_0179742194_p2033214721612"></a><a name="zh-cn_topic_0179742194_p2033214721612"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p10331174719160"><a name="zh-cn_topic_0179742194_p10331174719160"></a><a name="zh-cn_topic_0179742194_p10331174719160"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p2095019446162"><a name="zh-cn_topic_0179742194_p2095019446162"></a><a name="zh-cn_topic_0179742194_p2095019446162"></a>c3ne.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p550712761320"><a name="zh-cn_topic_0179742194_p550712761320"></a><a name="zh-cn_topic_0179742194_p550712761320"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row65084277136"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p11331184712166"><a name="zh-cn_topic_0179742194_p11331184712166"></a><a name="zh-cn_topic_0179742194_p11331184712166"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p83309476165"><a name="zh-cn_topic_0179742194_p83309476165"></a><a name="zh-cn_topic_0179742194_p83309476165"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p16950134421617"><a name="zh-cn_topic_0179742194_p16950134421617"></a><a name="zh-cn_topic_0179742194_p16950134421617"></a>c3ne.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p25131927161318"><a name="zh-cn_topic_0179742194_p25131927161318"></a><a name="zh-cn_topic_0179742194_p25131927161318"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row0515192701316"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p732911474164"><a name="zh-cn_topic_0179742194_p732911474164"></a><a name="zh-cn_topic_0179742194_p732911474164"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p143271447121619"><a name="zh-cn_topic_0179742194_p143271447121619"></a><a name="zh-cn_topic_0179742194_p143271447121619"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p109491644121618"><a name="zh-cn_topic_0179742194_p109491644121618"></a><a name="zh-cn_topic_0179742194_p109491644121618"></a>c3ne.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p12522102751311"><a name="zh-cn_topic_0179742194_p12522102751311"></a><a name="zh-cn_topic_0179742194_p12522102751311"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row6523142718132"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p1232604711613"><a name="zh-cn_topic_0179742194_p1232604711613"></a><a name="zh-cn_topic_0179742194_p1232604711613"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p232584751612"><a name="zh-cn_topic_0179742194_p232584751612"></a><a name="zh-cn_topic_0179742194_p232584751612"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p17947144411168"><a name="zh-cn_topic_0179742194_p17947144411168"></a><a name="zh-cn_topic_0179742194_p17947144411168"></a>c3ne.15xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p19528627131314"><a name="zh-cn_topic_0179742194_p19528627131314"></a><a name="zh-cn_topic_0179742194_p19528627131314"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 6**  高性能计算型（Hc2）弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table0407254151418"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row1443016544141"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p74386548148"><a name="zh-cn_topic_0179742194_p74386548148"></a><a name="zh-cn_topic_0179742194_p74386548148"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p14441195451411"><a name="zh-cn_topic_0179742194_p14441195451411"></a><a name="zh-cn_topic_0179742194_p14441195451411"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p14446185417144"><a name="zh-cn_topic_0179742194_p14446185417144"></a><a name="zh-cn_topic_0179742194_p14446185417144"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p9451145415145"><a name="zh-cn_topic_0179742194_p9451145415145"></a><a name="zh-cn_topic_0179742194_p9451145415145"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p245645461416"><a name="zh-cn_topic_0179742194_p245645461416"></a><a name="zh-cn_topic_0179742194_p245645461416"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row19460105414141"><td class="cellrowborder" rowspan="3" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p6465154111411"><a name="zh-cn_topic_0179742194_p6465154111411"></a><a name="zh-cn_topic_0179742194_p6465154111411"></a>Hc2型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1472294521710"><a name="zh-cn_topic_0179742194_p1472294521710"></a><a name="zh-cn_topic_0179742194_p1472294521710"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1072024561716"><a name="zh-cn_topic_0179742194_p1072024561716"></a><a name="zh-cn_topic_0179742194_p1072024561716"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p7477165413140"><a name="zh-cn_topic_0179742194_p7477165413140"></a><a name="zh-cn_topic_0179742194_p7477165413140"></a>hc2.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p164811954111418"><a name="zh-cn_topic_0179742194_p164811954111418"></a><a name="zh-cn_topic_0179742194_p164811954111418"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row11482145411412"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p2719124511171"><a name="zh-cn_topic_0179742194_p2719124511171"></a><a name="zh-cn_topic_0179742194_p2719124511171"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p07181545131713"><a name="zh-cn_topic_0179742194_p07181545131713"></a><a name="zh-cn_topic_0179742194_p07181545131713"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1349585421419"><a name="zh-cn_topic_0179742194_p1349585421419"></a><a name="zh-cn_topic_0179742194_p1349585421419"></a>hc2.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p5497135420141"><a name="zh-cn_topic_0179742194_p5497135420141"></a><a name="zh-cn_topic_0179742194_p5497135420141"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row150045421411"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p13717174512179"><a name="zh-cn_topic_0179742194_p13717174512179"></a><a name="zh-cn_topic_0179742194_p13717174512179"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p2712174551710"><a name="zh-cn_topic_0179742194_p2712174551710"></a><a name="zh-cn_topic_0179742194_p2712174551710"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1151485410140"><a name="zh-cn_topic_0179742194_p1151485410140"></a><a name="zh-cn_topic_0179742194_p1151485410140"></a>hc2.8xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p052175411143"><a name="zh-cn_topic_0179742194_p052175411143"></a><a name="zh-cn_topic_0179742194_p052175411143"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 7**  内存优化型弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table11173155712141"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row11191105718140"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p17196457201410"><a name="zh-cn_topic_0179742194_p17196457201410"></a><a name="zh-cn_topic_0179742194_p17196457201410"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p20199175711411"><a name="zh-cn_topic_0179742194_p20199175711411"></a><a name="zh-cn_topic_0179742194_p20199175711411"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p720319574148"><a name="zh-cn_topic_0179742194_p720319574148"></a><a name="zh-cn_topic_0179742194_p720319574148"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p7208185781418"><a name="zh-cn_topic_0179742194_p7208185781418"></a><a name="zh-cn_topic_0179742194_p7208185781418"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p32111457141410"><a name="zh-cn_topic_0179742194_p32111457141410"></a><a name="zh-cn_topic_0179742194_p32111457141410"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row1421565771419"><td class="cellrowborder" rowspan="6" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p9220165771411"><a name="zh-cn_topic_0179742194_p9220165771411"></a><a name="zh-cn_topic_0179742194_p9220165771411"></a>M3型</p>
<p id="zh-cn_topic_0179742194_p372265701618"><a name="zh-cn_topic_0179742194_p372265701618"></a><a name="zh-cn_topic_0179742194_p372265701618"></a></p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p39872121918"><a name="zh-cn_topic_0179742194_p39872121918"></a><a name="zh-cn_topic_0179742194_p39872121918"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p19986101151912"><a name="zh-cn_topic_0179742194_p19986101151912"></a><a name="zh-cn_topic_0179742194_p19986101151912"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p823315714148"><a name="zh-cn_topic_0179742194_p823315714148"></a><a name="zh-cn_topic_0179742194_p823315714148"></a>m3.large.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p122361457121416"><a name="zh-cn_topic_0179742194_p122361457121416"></a><a name="zh-cn_topic_0179742194_p122361457121416"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row123712571147"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p8985131101914"><a name="zh-cn_topic_0179742194_p8985131101914"></a><a name="zh-cn_topic_0179742194_p8985131101914"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p10983711199"><a name="zh-cn_topic_0179742194_p10983711199"></a><a name="zh-cn_topic_0179742194_p10983711199"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p124965713146"><a name="zh-cn_topic_0179742194_p124965713146"></a><a name="zh-cn_topic_0179742194_p124965713146"></a>m3.xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p225245791416"><a name="zh-cn_topic_0179742194_p225245791416"></a><a name="zh-cn_topic_0179742194_p225245791416"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row7254105771412"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p1198221141916"><a name="zh-cn_topic_0179742194_p1198221141916"></a><a name="zh-cn_topic_0179742194_p1198221141916"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p798212112199"><a name="zh-cn_topic_0179742194_p798212112199"></a><a name="zh-cn_topic_0179742194_p798212112199"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p192787188184"><a name="zh-cn_topic_0179742194_p192787188184"></a><a name="zh-cn_topic_0179742194_p192787188184"></a>m3.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p5269135719141"><a name="zh-cn_topic_0179742194_p5269135719141"></a><a name="zh-cn_topic_0179742194_p5269135719141"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row19272135731414"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p59811111917"><a name="zh-cn_topic_0179742194_p59811111917"></a><a name="zh-cn_topic_0179742194_p59811111917"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p197919121919"><a name="zh-cn_topic_0179742194_p197919121919"></a><a name="zh-cn_topic_0179742194_p197919121919"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p122831057161419"><a name="zh-cn_topic_0179742194_p122831057161419"></a><a name="zh-cn_topic_0179742194_p122831057161419"></a>m3.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p12871657101413"><a name="zh-cn_topic_0179742194_p12871657101413"></a><a name="zh-cn_topic_0179742194_p12871657101413"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row22891957151413"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p897841191913"><a name="zh-cn_topic_0179742194_p897841191913"></a><a name="zh-cn_topic_0179742194_p897841191913"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p49755131913"><a name="zh-cn_topic_0179742194_p49755131913"></a><a name="zh-cn_topic_0179742194_p49755131913"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1430295711147"><a name="zh-cn_topic_0179742194_p1430295711147"></a><a name="zh-cn_topic_0179742194_p1430295711147"></a>m3.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p19306357121419"><a name="zh-cn_topic_0179742194_p19306357121419"></a><a name="zh-cn_topic_0179742194_p19306357121419"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row18722155711165"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p27227578167"><a name="zh-cn_topic_0179742194_p27227578167"></a><a name="zh-cn_topic_0179742194_p27227578167"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p18722135751619"><a name="zh-cn_topic_0179742194_p18722135751619"></a><a name="zh-cn_topic_0179742194_p18722135751619"></a>512</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p167221657151619"><a name="zh-cn_topic_0179742194_p167221657151619"></a><a name="zh-cn_topic_0179742194_p167221657151619"></a>m3.15xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1172295715169"><a name="zh-cn_topic_0179742194_p1172295715169"></a><a name="zh-cn_topic_0179742194_p1172295715169"></a>KVM</p>
</td>
</tr>
<tr id="row2427123141213"><td class="cellrowborder" rowspan="6" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="p144284237124"><a name="p144284237124"></a><a name="p144284237124"></a>M6型</p>
<p id="p7674520152010"><a name="p7674520152010"></a><a name="p7674520152010"></a></p>
<p id="p181715231209"><a name="p181715231209"></a><a name="p181715231209"></a></p>
<p id="p050412258201"><a name="p050412258201"></a><a name="p050412258201"></a></p>
<p id="p145751827122013"><a name="p145751827122013"></a><a name="p145751827122013"></a></p>
<p id="p18870182932019"><a name="p18870182932019"></a><a name="p18870182932019"></a></p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="p542852314123"><a name="p542852314123"></a><a name="p542852314123"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="p11428202311213"><a name="p11428202311213"></a><a name="p11428202311213"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="p17428123131211"><a name="p17428123131211"></a><a name="p17428123131211"></a>m6.xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="p14428172331216"><a name="p14428172331216"></a><a name="p14428172331216"></a>KVM</p>
</td>
</tr>
<tr id="row116741202208"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p0674172019205"><a name="p0674172019205"></a><a name="p0674172019205"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p136741120102017"><a name="p136741120102017"></a><a name="p136741120102017"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p5674142032014"><a name="p5674142032014"></a><a name="p5674142032014"></a>m6.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p14674132015202"><a name="p14674132015202"></a><a name="p14674132015202"></a>KVM</p>
</td>
</tr>
<tr id="row51714237201"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p617122312019"><a name="p617122312019"></a><a name="p617122312019"></a>12</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p717102315207"><a name="p717102315207"></a><a name="p717102315207"></a>96</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p6171112352016"><a name="p6171112352016"></a><a name="p6171112352016"></a>m6.3xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p1817152312201"><a name="p1817152312201"></a><a name="p1817152312201"></a>KVM</p>
</td>
</tr>
<tr id="row15503162562018"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p6504102514200"><a name="p6504102514200"></a><a name="p6504102514200"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p550412254203"><a name="p550412254203"></a><a name="p550412254203"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p9504152511208"><a name="p9504152511208"></a><a name="p9504152511208"></a>m6.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p85040255202"><a name="p85040255202"></a><a name="p85040255202"></a>KVM</p>
</td>
</tr>
<tr id="row1575727192019"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p19575162752018"><a name="p19575162752018"></a><a name="p19575162752018"></a>24</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p11575182712208"><a name="p11575182712208"></a><a name="p11575182712208"></a>192</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p20575127112012"><a name="p20575127112012"></a><a name="p20575127112012"></a>m6.6xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p185751927172011"><a name="p185751927172011"></a><a name="p185751927172011"></a>KVM</p>
</td>
</tr>
<tr id="row58701729112015"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p1870112942015"><a name="p1870112942015"></a><a name="p1870112942015"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p487016296200"><a name="p487016296200"></a><a name="p487016296200"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p208701829102014"><a name="p208701829102014"></a><a name="p208701829102014"></a>m6.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p78701729182018"><a name="p78701729182018"></a><a name="p78701729182018"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 8**  鲲鹏通用计算增强型（KC1型）弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table1082234920820"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row168220491582"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p1982214491815"><a name="zh-cn_topic_0179742194_p1982214491815"></a><a name="zh-cn_topic_0179742194_p1982214491815"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p13822164916815"><a name="zh-cn_topic_0179742194_p13822164916815"></a><a name="zh-cn_topic_0179742194_p13822164916815"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p208221349784"><a name="zh-cn_topic_0179742194_p208221349784"></a><a name="zh-cn_topic_0179742194_p208221349784"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p68221049482"><a name="zh-cn_topic_0179742194_p68221049482"></a><a name="zh-cn_topic_0179742194_p68221049482"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p1822114920812"><a name="zh-cn_topic_0179742194_p1822114920812"></a><a name="zh-cn_topic_0179742194_p1822114920812"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row017951013384"><td class="cellrowborder" rowspan="8" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p7823349786"><a name="zh-cn_topic_0179742194_p7823349786"></a><a name="zh-cn_topic_0179742194_p7823349786"></a>KC1型</p>
<p id="zh-cn_topic_0179742194_p26172146484"><a name="zh-cn_topic_0179742194_p26172146484"></a><a name="zh-cn_topic_0179742194_p26172146484"></a></p>
<p id="zh-cn_topic_0179742194_p3371815154817"><a name="zh-cn_topic_0179742194_p3371815154817"></a><a name="zh-cn_topic_0179742194_p3371815154817"></a></p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p4180510193816"><a name="zh-cn_topic_0179742194_p4180510193816"></a><a name="zh-cn_topic_0179742194_p4180510193816"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1180171073811"><a name="zh-cn_topic_0179742194_p1180171073811"></a><a name="zh-cn_topic_0179742194_p1180171073811"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p10398165312388"><a name="zh-cn_topic_0179742194_p10398165312388"></a><a name="zh-cn_topic_0179742194_p10398165312388"></a>kc1.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p141809106386"><a name="zh-cn_topic_0179742194_p141809106386"></a><a name="zh-cn_topic_0179742194_p141809106386"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row20893101913385"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p15894141919389"><a name="zh-cn_topic_0179742194_p15894141919389"></a><a name="zh-cn_topic_0179742194_p15894141919389"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p16894619133817"><a name="zh-cn_topic_0179742194_p16894619133817"></a><a name="zh-cn_topic_0179742194_p16894619133817"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1275845412388"><a name="zh-cn_topic_0179742194_p1275845412388"></a><a name="zh-cn_topic_0179742194_p1275845412388"></a>kc1.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p18941919163815"><a name="zh-cn_topic_0179742194_p18941919163815"></a><a name="zh-cn_topic_0179742194_p18941919163815"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row13336122073817"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p9336102010388"><a name="zh-cn_topic_0179742194_p9336102010388"></a><a name="zh-cn_topic_0179742194_p9336102010388"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1336202016389"><a name="zh-cn_topic_0179742194_p1336202016389"></a><a name="zh-cn_topic_0179742194_p1336202016389"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p8950055133810"><a name="zh-cn_topic_0179742194_p8950055133810"></a><a name="zh-cn_topic_0179742194_p8950055133810"></a>kc1.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p63361520123810"><a name="zh-cn_topic_0179742194_p63361520123810"></a><a name="zh-cn_topic_0179742194_p63361520123810"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1682394911818"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p1976925105017"><a name="zh-cn_topic_0179742194_p1976925105017"></a><a name="zh-cn_topic_0179742194_p1976925105017"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p196264271504"><a name="zh-cn_topic_0179742194_p196264271504"></a><a name="zh-cn_topic_0179742194_p196264271504"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p782310499810"><a name="zh-cn_topic_0179742194_p782310499810"></a><a name="zh-cn_topic_0179742194_p782310499810"></a>kc1.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p78233491284"><a name="zh-cn_topic_0179742194_p78233491284"></a><a name="zh-cn_topic_0179742194_p78233491284"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row128244491483"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p1975122575011"><a name="zh-cn_topic_0179742194_p1975122575011"></a><a name="zh-cn_topic_0179742194_p1975122575011"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1362562716507"><a name="zh-cn_topic_0179742194_p1362562716507"></a><a name="zh-cn_topic_0179742194_p1362562716507"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1382464918812"><a name="zh-cn_topic_0179742194_p1382464918812"></a><a name="zh-cn_topic_0179742194_p1382464918812"></a>kc1.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1282434918818"><a name="zh-cn_topic_0179742194_p1282434918818"></a><a name="zh-cn_topic_0179742194_p1282434918818"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1382418491581"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p12974192514508"><a name="zh-cn_topic_0179742194_p12974192514508"></a><a name="zh-cn_topic_0179742194_p12974192514508"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p19623027135020"><a name="zh-cn_topic_0179742194_p19623027135020"></a><a name="zh-cn_topic_0179742194_p19623027135020"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p178243493818"><a name="zh-cn_topic_0179742194_p178243493818"></a><a name="zh-cn_topic_0179742194_p178243493818"></a>kc1.8xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p108248499811"><a name="zh-cn_topic_0179742194_p108248499811"></a><a name="zh-cn_topic_0179742194_p108248499811"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row18616141417481"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p106171214124817"><a name="zh-cn_topic_0179742194_p106171214124817"></a><a name="zh-cn_topic_0179742194_p106171214124817"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p2061761434819"><a name="zh-cn_topic_0179742194_p2061761434819"></a><a name="zh-cn_topic_0179742194_p2061761434819"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p13617414104813"><a name="zh-cn_topic_0179742194_p13617414104813"></a><a name="zh-cn_topic_0179742194_p13617414104813"></a>kc1.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p18617161434815"><a name="zh-cn_topic_0179742194_p18617161434815"></a><a name="zh-cn_topic_0179742194_p18617161434815"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row737115159489"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p203711415194814"><a name="zh-cn_topic_0179742194_p203711415194814"></a><a name="zh-cn_topic_0179742194_p203711415194814"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p9371515124815"><a name="zh-cn_topic_0179742194_p9371515124815"></a><a name="zh-cn_topic_0179742194_p9371515124815"></a>120</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p173711115164817"><a name="zh-cn_topic_0179742194_p173711115164817"></a><a name="zh-cn_topic_0179742194_p173711115164817"></a>kc1.15xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p337116156483"><a name="zh-cn_topic_0179742194_p337116156483"></a><a name="zh-cn_topic_0179742194_p337116156483"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 9**  鲲鹏内存优化型（KM1型）弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table13912373476"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row99283710477"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p3926371471"><a name="zh-cn_topic_0179742194_p3926371471"></a><a name="zh-cn_topic_0179742194_p3926371471"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p993183734711"><a name="zh-cn_topic_0179742194_p993183734711"></a><a name="zh-cn_topic_0179742194_p993183734711"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p693143734714"><a name="zh-cn_topic_0179742194_p693143734714"></a><a name="zh-cn_topic_0179742194_p693143734714"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p149353718473"><a name="zh-cn_topic_0179742194_p149353718473"></a><a name="zh-cn_topic_0179742194_p149353718473"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p1793133711471"><a name="zh-cn_topic_0179742194_p1793133711471"></a><a name="zh-cn_topic_0179742194_p1793133711471"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row29363714719"><td class="cellrowborder" rowspan="5" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p18941837174711"><a name="zh-cn_topic_0179742194_p18941837174711"></a><a name="zh-cn_topic_0179742194_p18941837174711"></a>KM1型</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p167327354521"><a name="zh-cn_topic_0179742194_p167327354521"></a><a name="zh-cn_topic_0179742194_p167327354521"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p2073183518522"><a name="zh-cn_topic_0179742194_p2073183518522"></a><a name="zh-cn_topic_0179742194_p2073183518522"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1094113774717"><a name="zh-cn_topic_0179742194_p1094113774717"></a><a name="zh-cn_topic_0179742194_p1094113774717"></a>km1.xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p494163714474"><a name="zh-cn_topic_0179742194_p494163714474"></a><a name="zh-cn_topic_0179742194_p494163714474"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row99493720477"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p107311035185210"><a name="zh-cn_topic_0179742194_p107311035185210"></a><a name="zh-cn_topic_0179742194_p107311035185210"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1573010356527"><a name="zh-cn_topic_0179742194_p1573010356527"></a><a name="zh-cn_topic_0179742194_p1573010356527"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p89453794719"><a name="zh-cn_topic_0179742194_p89453794719"></a><a name="zh-cn_topic_0179742194_p89453794719"></a>km1.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p994103754718"><a name="zh-cn_topic_0179742194_p994103754718"></a><a name="zh-cn_topic_0179742194_p994103754718"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row394113774711"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p19729735165220"><a name="zh-cn_topic_0179742194_p19729735165220"></a><a name="zh-cn_topic_0179742194_p19729735165220"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p972873514523"><a name="zh-cn_topic_0179742194_p972873514523"></a><a name="zh-cn_topic_0179742194_p972873514523"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p995103784715"><a name="zh-cn_topic_0179742194_p995103784715"></a><a name="zh-cn_topic_0179742194_p995103784715"></a>km1.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p2095193715471"><a name="zh-cn_topic_0179742194_p2095193715471"></a><a name="zh-cn_topic_0179742194_p2095193715471"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row195203716479"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p10728173525219"><a name="zh-cn_topic_0179742194_p10728173525219"></a><a name="zh-cn_topic_0179742194_p10728173525219"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p17271035195213"><a name="zh-cn_topic_0179742194_p17271035195213"></a><a name="zh-cn_topic_0179742194_p17271035195213"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p15958377477"><a name="zh-cn_topic_0179742194_p15958377477"></a><a name="zh-cn_topic_0179742194_p15958377477"></a>km1.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1495437174712"><a name="zh-cn_topic_0179742194_p1495437174712"></a><a name="zh-cn_topic_0179742194_p1495437174712"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row169543710474"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p3726133535211"><a name="zh-cn_topic_0179742194_p3726133535211"></a><a name="zh-cn_topic_0179742194_p3726133535211"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p157251435175213"><a name="zh-cn_topic_0179742194_p157251435175213"></a><a name="zh-cn_topic_0179742194_p157251435175213"></a>480</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p19951370475"><a name="zh-cn_topic_0179742194_p19951370475"></a><a name="zh-cn_topic_0179742194_p19951370475"></a>km1.15xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1796113715472"><a name="zh-cn_topic_0179742194_p1796113715472"></a><a name="zh-cn_topic_0179742194_p1796113715472"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 10**  鲲鹏超高I/O型（KI1型）弹性云服务器的规格

<a name="table261121919297"></a>
<table><thead align="left"><tr id="row186219196292"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="p8621719152911"><a name="p8621719152911"></a><a name="p8621719152911"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="p262111911290"><a name="p262111911290"></a><a name="p262111911290"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="p1663419162917"><a name="p1663419162917"></a><a name="p1663419162917"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="p76341910292"><a name="p76341910292"></a><a name="p76341910292"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="p163141911292"><a name="p163141911292"></a><a name="p163141911292"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="row1563181916297"><td class="cellrowborder" rowspan="5" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="p863719122920"><a name="p863719122920"></a><a name="p863719122920"></a>KI1型</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="p186361910291"><a name="p186361910291"></a><a name="p186361910291"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="p1363619182917"><a name="p1363619182917"></a><a name="p1363619182917"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="p1463151918293"><a name="p1463151918293"></a><a name="p1463151918293"></a>ki1.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p96361962912"><a name="p96361962912"></a><a name="p96361962912"></a>KVM</p>
</td>
</tr>
<tr id="row46319199295"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p13645195299"><a name="p13645195299"></a><a name="p13645195299"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p1064141992911"><a name="p1064141992911"></a><a name="p1064141992911"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p136416192296"><a name="p136416192296"></a><a name="p136416192296"></a>ki1.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p116416194299"><a name="p116416194299"></a><a name="p116416194299"></a>KVM</p>
</td>
</tr>
<tr id="row1642194292"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p126441962912"><a name="p126441962912"></a><a name="p126441962912"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p764191922910"><a name="p764191922910"></a><a name="p764191922910"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p36461917296"><a name="p36461917296"></a><a name="p36461917296"></a>ki1.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p66441992914"><a name="p66441992914"></a><a name="p66441992914"></a>KVM</p>
</td>
</tr>
<tr id="row1664101952920"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p764131911296"><a name="p764131911296"></a><a name="p764131911296"></a>48</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p7646197298"><a name="p7646197298"></a><a name="p7646197298"></a>192</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p156531911299"><a name="p156531911299"></a><a name="p156531911299"></a>ki1.12xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p26510194290"><a name="p26510194290"></a><a name="p26510194290"></a>KVM</p>
</td>
</tr>
<tr id="row86511199291"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p96521972911"><a name="p96521972911"></a><a name="p96521972911"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p106517198299"><a name="p106517198299"></a><a name="p106517198299"></a>228</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p865219192914"><a name="p865219192914"></a><a name="p865219192914"></a>ki1.16xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p1651819142916"><a name="p1651819142916"></a><a name="p1651819142916"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 11**  超高I/O型弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table14808135715918"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row208101557135914"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p10810125735911"><a name="zh-cn_topic_0179742194_p10810125735911"></a><a name="zh-cn_topic_0179742194_p10810125735911"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p581015572599"><a name="zh-cn_topic_0179742194_p581015572599"></a><a name="zh-cn_topic_0179742194_p581015572599"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p28101257125915"><a name="zh-cn_topic_0179742194_p28101257125915"></a><a name="zh-cn_topic_0179742194_p28101257125915"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p1481011575592"><a name="zh-cn_topic_0179742194_p1481011575592"></a><a name="zh-cn_topic_0179742194_p1481011575592"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p128101357115916"><a name="zh-cn_topic_0179742194_p128101357115916"></a><a name="zh-cn_topic_0179742194_p128101357115916"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row18810357105919"><td class="cellrowborder" rowspan="4" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p1681005718598"><a name="zh-cn_topic_0179742194_p1681005718598"></a><a name="zh-cn_topic_0179742194_p1681005718598"></a>I3型</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p19810145717596"><a name="zh-cn_topic_0179742194_p19810145717596"></a><a name="zh-cn_topic_0179742194_p19810145717596"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1581013571599"><a name="zh-cn_topic_0179742194_p1581013571599"></a><a name="zh-cn_topic_0179742194_p1581013571599"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p1981015711590"><a name="zh-cn_topic_0179742194_p1981015711590"></a><a name="zh-cn_topic_0179742194_p1981015711590"></a>i3.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p15810105712590"><a name="zh-cn_topic_0179742194_p15810105712590"></a><a name="zh-cn_topic_0179742194_p15810105712590"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1581075714598"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p6811125719599"><a name="zh-cn_topic_0179742194_p6811125719599"></a><a name="zh-cn_topic_0179742194_p6811125719599"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p108111257155917"><a name="zh-cn_topic_0179742194_p108111257155917"></a><a name="zh-cn_topic_0179742194_p108111257155917"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p181155714594"><a name="zh-cn_topic_0179742194_p181155714594"></a><a name="zh-cn_topic_0179742194_p181155714594"></a>i3.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p981115577599"><a name="zh-cn_topic_0179742194_p981115577599"></a><a name="zh-cn_topic_0179742194_p981115577599"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row11811357155915"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p5811857145918"><a name="zh-cn_topic_0179742194_p5811857145918"></a><a name="zh-cn_topic_0179742194_p5811857145918"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p108115571597"><a name="zh-cn_topic_0179742194_p108115571597"></a><a name="zh-cn_topic_0179742194_p108115571597"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p138111357165912"><a name="zh-cn_topic_0179742194_p138111357165912"></a><a name="zh-cn_topic_0179742194_p138111357165912"></a>i3.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p681155775916"><a name="zh-cn_topic_0179742194_p681155775916"></a><a name="zh-cn_topic_0179742194_p681155775916"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row081135710592"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p281117572598"><a name="zh-cn_topic_0179742194_p281117572598"></a><a name="zh-cn_topic_0179742194_p281117572598"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p2811145717594"><a name="zh-cn_topic_0179742194_p2811145717594"></a><a name="zh-cn_topic_0179742194_p2811145717594"></a>512</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p5811185725910"><a name="zh-cn_topic_0179742194_p5811185725910"></a><a name="zh-cn_topic_0179742194_p5811185725910"></a>i3.15xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p16811185725918"><a name="zh-cn_topic_0179742194_p16811185725918"></a><a name="zh-cn_topic_0179742194_p16811185725918"></a>KVM</p>
</td>
</tr>
<tr id="row29241856102513"><td class="cellrowborder" rowspan="4" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="p292418569254"><a name="p292418569254"></a><a name="p292418569254"></a>IR3型</p>
<p id="p2801165816263"><a name="p2801165816263"></a><a name="p2801165816263"></a></p>
<p id="p7388215275"><a name="p7388215275"></a><a name="p7388215275"></a></p>
<p id="p6380173152718"><a name="p6380173152718"></a><a name="p6380173152718"></a></p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="p1292415564258"><a name="p1292415564258"></a><a name="p1292415564258"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="p15925125610250"><a name="p15925125610250"></a><a name="p15925125610250"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="p1892545611257"><a name="p1892545611257"></a><a name="p1892545611257"></a>ir3.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p15925155622512"><a name="p15925155622512"></a><a name="p15925155622512"></a>KVM</p>
</td>
</tr>
<tr id="row1680185819267"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p680195842615"><a name="p680195842615"></a><a name="p680195842615"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p580155882613"><a name="p580155882613"></a><a name="p580155882613"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p1880117583264"><a name="p1880117583264"></a><a name="p1880117583264"></a>ir3.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p7801155822612"><a name="p7801155822612"></a><a name="p7801155822612"></a>KVM</p>
</td>
</tr>
<tr id="row133881118272"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p1938818117273"><a name="p1938818117273"></a><a name="p1938818117273"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p2038816102718"><a name="p2038816102718"></a><a name="p2038816102718"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p153886172718"><a name="p153886172718"></a><a name="p153886172718"></a>ir3.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p15388201182717"><a name="p15388201182717"></a><a name="p15388201182717"></a>KVM</p>
</td>
</tr>
<tr id="row17379038275"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p133801030276"><a name="p133801030276"></a><a name="p133801030276"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="p19380337275"><a name="p19380337275"></a><a name="p19380337275"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p838013342717"><a name="p838013342717"></a><a name="p838013342717"></a>ir3.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p63806362717"><a name="p63806362717"></a><a name="p63806362717"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 12**  GPU计算加速型（P1型）弹性云服务器的规格

<a name="zh-cn_topic_0179742194_table1420535714162"></a>
<table><thead align="left"><tr id="zh-cn_topic_0179742194_row120614576162"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0179742194_p1320615761617"><a name="zh-cn_topic_0179742194_p1320615761617"></a><a name="zh-cn_topic_0179742194_p1320615761617"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0179742194_p122068577162"><a name="zh-cn_topic_0179742194_p122068577162"></a><a name="zh-cn_topic_0179742194_p122068577162"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0179742194_p11206105731612"><a name="zh-cn_topic_0179742194_p11206105731612"></a><a name="zh-cn_topic_0179742194_p11206105731612"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0179742194_p2206155751614"><a name="zh-cn_topic_0179742194_p2206155751614"></a><a name="zh-cn_topic_0179742194_p2206155751614"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0179742194_p13206135710161"><a name="zh-cn_topic_0179742194_p13206135710161"></a><a name="zh-cn_topic_0179742194_p13206135710161"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0179742194_row1120765721619"><td class="cellrowborder" rowspan="3" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p1620765791610"><a name="zh-cn_topic_0179742194_p1620765791610"></a><a name="zh-cn_topic_0179742194_p1620765791610"></a>P1型</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p1220710578166"><a name="zh-cn_topic_0179742194_p1220710578166"></a><a name="zh-cn_topic_0179742194_p1220710578166"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1820725711163"><a name="zh-cn_topic_0179742194_p1820725711163"></a><a name="zh-cn_topic_0179742194_p1820725711163"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p11207257171618"><a name="zh-cn_topic_0179742194_p11207257171618"></a><a name="zh-cn_topic_0179742194_p11207257171618"></a>p1.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0179742194_p1320745721611"><a name="zh-cn_topic_0179742194_p1320745721611"></a><a name="zh-cn_topic_0179742194_p1320745721611"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1207205711619"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p13207205713161"><a name="zh-cn_topic_0179742194_p13207205713161"></a><a name="zh-cn_topic_0179742194_p13207205713161"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p122071157181610"><a name="zh-cn_topic_0179742194_p122071157181610"></a><a name="zh-cn_topic_0179742194_p122071157181610"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p020711576169"><a name="zh-cn_topic_0179742194_p020711576169"></a><a name="zh-cn_topic_0179742194_p020711576169"></a>p1.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p32088572166"><a name="zh-cn_topic_0179742194_p32088572166"></a><a name="zh-cn_topic_0179742194_p32088572166"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0179742194_row1220875713168"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0179742194_p320885717160"><a name="zh-cn_topic_0179742194_p320885717160"></a><a name="zh-cn_topic_0179742194_p320885717160"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0179742194_p14208165731613"><a name="zh-cn_topic_0179742194_p14208165731613"></a><a name="zh-cn_topic_0179742194_p14208165731613"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0179742194_p1420885731613"><a name="zh-cn_topic_0179742194_p1420885731613"></a><a name="zh-cn_topic_0179742194_p1420885731613"></a>p1.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0179742194_p102089572164"><a name="zh-cn_topic_0179742194_p102089572164"></a><a name="zh-cn_topic_0179742194_p102089572164"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

