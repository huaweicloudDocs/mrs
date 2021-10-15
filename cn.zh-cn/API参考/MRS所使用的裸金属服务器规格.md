# MRS所使用的裸金属服务器规格<a name="mrs_01_9001"></a>

针对不同的应用场景，MRS使用到如下类型的裸金属服务器。

-   本地存储型（D2型）
-   IO优化型（IO2）

## 规格命名规则<a name="sb4b7e819c0a247828fa3bf14fcc9fe66"></a>

AB.C.D

例如m2.8xlarge.8

其中，

-   A表示系列，例如：s表示通用型、c表示计算型、m表示内存型。
-   B表示系列号，例如：s1中的1表示通用型I代，s2中2表示通用型II代。
-   C表示规格，当前系列中的规格大小，例如：medium、large、xlarge。
-   D表示内存、CPU比，以具体数字表示，例如4表示内存和CPU的比值为4。

## 规格<a name="scbc2287cd4b8401f9f303464486921a0"></a>

**表 1**  IO优化型（IO2型）裸金属服务器的规格

<a name="t85e61fc080364f58bce588da3b57bde9"></a>
<table><thead align="left"><tr id="r9ac733fc683c476b82d28b146a615b68"><th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0202149928_p189621387153"><a name="zh-cn_topic_0202149928_p189621387153"></a><a name="zh-cn_topic_0202149928_p189621387153"></a>规格名称/ID</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0202149928_p39625385152"><a name="zh-cn_topic_0202149928_p39625385152"></a><a name="zh-cn_topic_0202149928_p39625385152"></a>CPU</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0202149928_p59627383157"><a name="zh-cn_topic_0202149928_p59627383157"></a><a name="zh-cn_topic_0202149928_p59627383157"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0202149928_p996243811511"><a name="zh-cn_topic_0202149928_p996243811511"></a><a name="zh-cn_topic_0202149928_p996243811511"></a>本地磁盘</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="aa9b645e079de44b7b5db799ab40aa24a"><a name="aa9b645e079de44b7b5db799ab40aa24a"></a><a name="aa9b645e079de44b7b5db799ab40aa24a"></a>扩展配置</p>
</th>
</tr>
</thead>
<tbody><tr id="r45e7e46b1a8d4df39514e7a77de629f3"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.1 "><p id="a98f89f20de734d5aa5bc4c91443a7cf6"><a name="a98f89f20de734d5aa5bc4c91443a7cf6"></a><a name="a98f89f20de734d5aa5bc4c91443a7cf6"></a>physical.io2.xlarge</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0202149928_p640219308158"><a name="zh-cn_topic_0202149928_p640219308158"></a><a name="zh-cn_topic_0202149928_p640219308158"></a>2 * 22 Core Intel Xeon Gold 6161 V5 (2.2 GHz)</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="ab8c606cc53e64354b1e400d0d055999f"><a name="ab8c606cc53e64354b1e400d0d055999f"></a><a name="ab8c606cc53e64354b1e400d0d055999f"></a>384 DDR4 RAM (GB)</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0202149928_p24026306153"><a name="zh-cn_topic_0202149928_p24026306153"></a><a name="zh-cn_topic_0202149928_p24026306153"></a>2 * 800GB SSD RAID 1 + 10 * 800GB SSD</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="a1e3670e470e345e292a9c46e45b82d04"><a name="a1e3670e470e345e292a9c46e45b82d04"></a><a name="a1e3670e470e345e292a9c46e45b82d04"></a>2 x 2 * 10GE</p>
</td>
</tr>
</tbody>
</table>

**表 2**  本地存储型（D2型）裸金属服务器的规格

<a name="t34236dff23d9467290806951f01533a2"></a>
<table><thead align="left"><tr id="r6c2d7d344ace4bb88d357a4e804b547f"><th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.1"><p id="a162a4e55e59e418ea1db1f1c3b1ba068"><a name="a162a4e55e59e418ea1db1f1c3b1ba068"></a><a name="a162a4e55e59e418ea1db1f1c3b1ba068"></a>规格名称/ID</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.2"><p id="a5495f64bba1749f3839254e7beffe138"><a name="a5495f64bba1749f3839254e7beffe138"></a><a name="a5495f64bba1749f3839254e7beffe138"></a>CPU</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.3"><p id="a88a647c040f143a19dcef459db3916ea"><a name="a88a647c040f143a19dcef459db3916ea"></a><a name="a88a647c040f143a19dcef459db3916ea"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.4"><p id="a84d09be23f4f4dada6df28bfd3ea9c33"><a name="a84d09be23f4f4dada6df28bfd3ea9c33"></a><a name="a84d09be23f4f4dada6df28bfd3ea9c33"></a>本地磁盘</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="ac7539d75575d4897b9502901520e7c70"><a name="ac7539d75575d4897b9502901520e7c70"></a><a name="ac7539d75575d4897b9502901520e7c70"></a>扩展配置</p>
</th>
</tr>
</thead>
<tbody><tr id="r7153d7e4adb14e17ac5a9afbd990191e"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.1 "><p id="a22d30a3026534a108366166fb7db1a94"><a name="a22d30a3026534a108366166fb7db1a94"></a><a name="a22d30a3026534a108366166fb7db1a94"></a><span>physical.d2.large</span></p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0202149928_p650306175517"><a name="zh-cn_topic_0202149928_p650306175517"></a><a name="zh-cn_topic_0202149928_p650306175517"></a><span>2 * 12 Core Intel Xeon Gold 5118 V5 (2.3 GHz)</span></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="adf8912dd48e444008b978546ce4645b9"><a name="adf8912dd48e444008b978546ce4645b9"></a><a name="adf8912dd48e444008b978546ce4645b9"></a><span>192 DDR4 RAM (GB)</span></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0202149928_p13501564553"><a name="zh-cn_topic_0202149928_p13501564553"></a><a name="zh-cn_topic_0202149928_p13501564553"></a><span>2 * 600GB SAS System Disk RAID 1 + 12 * 10TB SATA</span></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0202149928_p115004655510"><a name="zh-cn_topic_0202149928_p115004655510"></a><a name="zh-cn_topic_0202149928_p115004655510"></a><span>2 x 2 * 10GE</span></p>
</td>
</tr>
</tbody>
</table>

