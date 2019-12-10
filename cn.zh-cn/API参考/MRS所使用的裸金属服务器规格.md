# MRS所使用的裸金属服务器规格<a name="ZH-CN_TOPIC_0202208976"></a>

针对不同的应用场景，MRS使用到如下类型的裸金属服务器。

-   本地存储型（D2型）
-   IO优化型（IO2）

## 规格命名规则<a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_section741930611313"></a>

AB.C.D

例如m2.8xlarge.8

其中，

-   A表示系列，例如：s表示通用型、c表示计算型、m表示内存型。
-   B表示系列号，例如：s1中的1表示通用型I代，s2中2表示通用型II代。
-   C表示规格，当前系列中的规格大小，例如：medium、large、xlarge。
-   D表示内存、CPU比，以具体数字表示，例如4表示内存和CPU的比值为4。

## 规格<a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_section1399585312355"></a>

**表 1**  本地存储型（D2型）裸金属服务器的规格

<a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_table24263593453"></a>
<table><thead align="left"><tr id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_row20450165974514"><th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0202149928_p189621387153"><a name="zh-cn_topic_0202149928_p189621387153"></a><a name="zh-cn_topic_0202149928_p189621387153"></a>规格名称/ID</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0202149928_p39625385152"><a name="zh-cn_topic_0202149928_p39625385152"></a><a name="zh-cn_topic_0202149928_p39625385152"></a>CPU</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0202149928_p59627383157"><a name="zh-cn_topic_0202149928_p59627383157"></a><a name="zh-cn_topic_0202149928_p59627383157"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0202149928_p996243811511"><a name="zh-cn_topic_0202149928_p996243811511"></a><a name="zh-cn_topic_0202149928_p996243811511"></a>本地磁盘</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0202149928_p1696263821518"><a name="zh-cn_topic_0202149928_p1696263821518"></a><a name="zh-cn_topic_0202149928_p1696263821518"></a>扩展配置</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_row548012592452"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0202149928_p12402183013158"><a name="zh-cn_topic_0202149928_p12402183013158"></a><a name="zh-cn_topic_0202149928_p12402183013158"></a>physical.io2.xlarge</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0202149928_p640219308158"><a name="zh-cn_topic_0202149928_p640219308158"></a><a name="zh-cn_topic_0202149928_p640219308158"></a>2 * 22 Core Intel Xeon Gold 6161 V5 (2.2 GHz)</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0202149928_p194021430151513"><a name="zh-cn_topic_0202149928_p194021430151513"></a><a name="zh-cn_topic_0202149928_p194021430151513"></a>384 DDR4 RAM (GB)</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0202149928_p24026306153"><a name="zh-cn_topic_0202149928_p24026306153"></a><a name="zh-cn_topic_0202149928_p24026306153"></a>2 * 800GB SSD RAID 1 + 10 * 800GB SSD</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0202149928_p1140213307154"><a name="zh-cn_topic_0202149928_p1140213307154"></a><a name="zh-cn_topic_0202149928_p1140213307154"></a>2 x 2 * 10GE</p>
</td>
</tr>
</tbody>
</table>

**表 2**  本地存储型（D2型）裸金属服务器的规格

<a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_table66778917103035"></a>
<table><thead align="left"><tr id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_row21254511103035"><th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p52972653162927"><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p52972653162927"></a><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p52972653162927"></a>规格名称/ID</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p62926494162927"><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p62926494162927"></a><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p62926494162927"></a>CPU</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p63881219162927"><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p63881219162927"></a><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p63881219162927"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p6996228162927"><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p6996228162927"></a><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p6996228162927"></a>本地磁盘</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p19167123116295"><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p19167123116295"></a><a name="zh-cn_topic_0202149928_zh-cn_topic_0179742194_p19167123116295"></a>扩展配置</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0202149928_zh-cn_topic_0179742194_row8532241591"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0202149928_p1850713675514"><a name="zh-cn_topic_0202149928_p1850713675514"></a><a name="zh-cn_topic_0202149928_p1850713675514"></a><span>physical.d2.large</span></p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0202149928_p650306175517"><a name="zh-cn_topic_0202149928_p650306175517"></a><a name="zh-cn_topic_0202149928_p650306175517"></a><span>2 * 12 Core Intel Xeon Gold 5118 V5 (2.3 GHz)</span></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0202149928_p1550236175514"><a name="zh-cn_topic_0202149928_p1550236175514"></a><a name="zh-cn_topic_0202149928_p1550236175514"></a><span>192 DDR4 RAM (GB)</span></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0202149928_p13501564553"><a name="zh-cn_topic_0202149928_p13501564553"></a><a name="zh-cn_topic_0202149928_p13501564553"></a><span>2 * 600GB SAS System Disk RAID 1 + 12 * 10TB SATA</span></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0202149928_p115004655510"><a name="zh-cn_topic_0202149928_p115004655510"></a><a name="zh-cn_topic_0202149928_p115004655510"></a><span>2 x 2 * 10GE</span></p>
</td>
</tr>
</tbody>
</table>

