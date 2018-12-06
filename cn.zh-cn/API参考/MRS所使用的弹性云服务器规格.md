# MRS所使用的弹性云服务器规格<a name="ZH-CN_TOPIC_0126150156"></a>

针对不同的应用场景，MRS使用到如下类型的弹性云服务器。

-   通用计算型（S1型）
-   通用计算型（S2型）
-   通用计算型（S3型）
-   通用计算型（C2型）
-   通用计算增强型（C3型）
-   磁盘增强型（D2型）
-   通用网络增强型（C3ne型）

## 规格命名规则<a name="zh-cn_topic_0114912370_section741930611313"></a>

AB.C.D

例如m2.8xlarge.8

其中，

-   A表示系列，例如：s表示通用型、c表示计算型、m表示内存型。
-   B表示系列号，例如：s1中的1表示通用型I代，s2中2表示通用型II代。
-   C表示规格，当前系列中的规格大小，例如：medium、large、xlarge。
-   D表示内存、CPU比，以具体数字表示，例如4表示内存和CPU的比值为4。

## 规格<a name="zh-cn_topic_0114912370_section1399585312355"></a>

**表 1**  通用计算型弹性云服务器的规格

<a name="zh-cn_topic_0114912370_table66778917103035"></a>
<table><thead align="left"><tr id="zh-cn_topic_0114912370_row21254511103035"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0114912370_p52972653162927"><a name="zh-cn_topic_0114912370_p52972653162927"></a><a name="zh-cn_topic_0114912370_p52972653162927"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0114912370_p62926494162927"><a name="zh-cn_topic_0114912370_p62926494162927"></a><a name="zh-cn_topic_0114912370_p62926494162927"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0114912370_p63881219162927"><a name="zh-cn_topic_0114912370_p63881219162927"></a><a name="zh-cn_topic_0114912370_p63881219162927"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0114912370_p6996228162927"><a name="zh-cn_topic_0114912370_p6996228162927"></a><a name="zh-cn_topic_0114912370_p6996228162927"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0114912370_p19167123116295"><a name="zh-cn_topic_0114912370_p19167123116295"></a><a name="zh-cn_topic_0114912370_p19167123116295"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0114912370_row8532241591"><td class="cellrowborder" rowspan="3" valign="top" width="23%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p3534747915"><a name="zh-cn_topic_0114912370_p3534747915"></a><a name="zh-cn_topic_0114912370_p3534747915"></a>S1型</p>
<p id="zh-cn_topic_0114912370_p15824165112920"><a name="zh-cn_topic_0114912370_p15824165112920"></a><a name="zh-cn_topic_0114912370_p15824165112920"></a></p>
<p id="zh-cn_topic_0114912370_p114844523910"><a name="zh-cn_topic_0114912370_p114844523910"></a><a name="zh-cn_topic_0114912370_p114844523910"></a></p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p1253410414911"><a name="zh-cn_topic_0114912370_p1253410414911"></a><a name="zh-cn_topic_0114912370_p1253410414911"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p1553419411912"><a name="zh-cn_topic_0114912370_p1553419411912"></a><a name="zh-cn_topic_0114912370_p1553419411912"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p553411413913"><a name="zh-cn_topic_0114912370_p553411413913"></a><a name="zh-cn_topic_0114912370_p553411413913"></a>s1.xlarge</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0114912370_p612815911919"><a name="zh-cn_topic_0114912370_p612815911919"></a><a name="zh-cn_topic_0114912370_p612815911919"></a>XEN</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row98249514915"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p18241651791"><a name="zh-cn_topic_0114912370_p18241651791"></a><a name="zh-cn_topic_0114912370_p18241651791"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p13824125111919"><a name="zh-cn_topic_0114912370_p13824125111919"></a><a name="zh-cn_topic_0114912370_p13824125111919"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p168244514915"><a name="zh-cn_topic_0114912370_p168244514915"></a><a name="zh-cn_topic_0114912370_p168244514915"></a>s1.4xlarge</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p17814459790"><a name="zh-cn_topic_0114912370_p17814459790"></a><a name="zh-cn_topic_0114912370_p17814459790"></a>XEN</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row34841252894"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p34847521293"><a name="zh-cn_topic_0114912370_p34847521293"></a><a name="zh-cn_topic_0114912370_p34847521293"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p174841952997"><a name="zh-cn_topic_0114912370_p174841952997"></a><a name="zh-cn_topic_0114912370_p174841952997"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p184840524912"><a name="zh-cn_topic_0114912370_p184840524912"></a><a name="zh-cn_topic_0114912370_p184840524912"></a>s1.8xlarge</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p1950414018107"><a name="zh-cn_topic_0114912370_p1950414018107"></a><a name="zh-cn_topic_0114912370_p1950414018107"></a>XEN</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row9271195762811"><td class="cellrowborder" rowspan="5" valign="top" width="23%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p122721457102811"><a name="zh-cn_topic_0114912370_p122721457102811"></a><a name="zh-cn_topic_0114912370_p122721457102811"></a>S2型</p>
<p id="zh-cn_topic_0114912370_p743413376293"><a name="zh-cn_topic_0114912370_p743413376293"></a><a name="zh-cn_topic_0114912370_p743413376293"></a></p>
<p id="zh-cn_topic_0114912370_p19827154022911"><a name="zh-cn_topic_0114912370_p19827154022911"></a><a name="zh-cn_topic_0114912370_p19827154022911"></a></p>
<p id="zh-cn_topic_0114912370_p2980174872918"><a name="zh-cn_topic_0114912370_p2980174872918"></a><a name="zh-cn_topic_0114912370_p2980174872918"></a></p>
<p id="zh-cn_topic_0114912370_p6652134319299"><a name="zh-cn_topic_0114912370_p6652134319299"></a><a name="zh-cn_topic_0114912370_p6652134319299"></a></p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p24361830183112"><a name="zh-cn_topic_0114912370_p24361830183112"></a><a name="zh-cn_topic_0114912370_p24361830183112"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p927205782811"><a name="zh-cn_topic_0114912370_p927205782811"></a><a name="zh-cn_topic_0114912370_p927205782811"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p1327265712812"><a name="zh-cn_topic_0114912370_p1327265712812"></a><a name="zh-cn_topic_0114912370_p1327265712812"></a>s2.xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0114912370_p6272145722810"><a name="zh-cn_topic_0114912370_p6272145722810"></a><a name="zh-cn_topic_0114912370_p6272145722810"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row6434123717299"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p45301738183113"><a name="zh-cn_topic_0114912370_p45301738183113"></a><a name="zh-cn_topic_0114912370_p45301738183113"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p8434437132910"><a name="zh-cn_topic_0114912370_p8434437132910"></a><a name="zh-cn_topic_0114912370_p8434437132910"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p1150661153213"><a name="zh-cn_topic_0114912370_p1150661153213"></a><a name="zh-cn_topic_0114912370_p1150661153213"></a>s2.2xlarge.2</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p1443493716290"><a name="zh-cn_topic_0114912370_p1443493716290"></a><a name="zh-cn_topic_0114912370_p1443493716290"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row2827114011296"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p1798214520311"><a name="zh-cn_topic_0114912370_p1798214520311"></a><a name="zh-cn_topic_0114912370_p1798214520311"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p0827124013293"><a name="zh-cn_topic_0114912370_p0827124013293"></a><a name="zh-cn_topic_0114912370_p0827124013293"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p14505161193220"><a name="zh-cn_topic_0114912370_p14505161193220"></a><a name="zh-cn_topic_0114912370_p14505161193220"></a>s2.4xlarge.2</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p782704042913"><a name="zh-cn_topic_0114912370_p782704042913"></a><a name="zh-cn_topic_0114912370_p782704042913"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row19980164832913"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p0900651113118"><a name="zh-cn_topic_0114912370_p0900651113118"></a><a name="zh-cn_topic_0114912370_p0900651113118"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p149801148102918"><a name="zh-cn_topic_0114912370_p149801148102918"></a><a name="zh-cn_topic_0114912370_p149801148102918"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p050214112321"><a name="zh-cn_topic_0114912370_p050214112321"></a><a name="zh-cn_topic_0114912370_p050214112321"></a>s2.4xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p1980948162912"><a name="zh-cn_topic_0114912370_p1980948162912"></a><a name="zh-cn_topic_0114912370_p1980948162912"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row176521443172916"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p139561600328"><a name="zh-cn_topic_0114912370_p139561600328"></a><a name="zh-cn_topic_0114912370_p139561600328"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p1265294302911"><a name="zh-cn_topic_0114912370_p1265294302911"></a><a name="zh-cn_topic_0114912370_p1265294302911"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p711501763110"><a name="zh-cn_topic_0114912370_p711501763110"></a><a name="zh-cn_topic_0114912370_p711501763110"></a>s2.8xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p10653543192920"><a name="zh-cn_topic_0114912370_p10653543192920"></a><a name="zh-cn_topic_0114912370_p10653543192920"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row164571325903"><td class="cellrowborder" rowspan="4" valign="top" width="23%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p10188451512"><a name="zh-cn_topic_0114912370_p10188451512"></a><a name="zh-cn_topic_0114912370_p10188451512"></a>S3型</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p72667511316"><a name="zh-cn_topic_0114912370_p72667511316"></a><a name="zh-cn_topic_0114912370_p72667511316"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p192694512113"><a name="zh-cn_topic_0114912370_p192694512113"></a><a name="zh-cn_topic_0114912370_p192694512113"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p182748510114"><a name="zh-cn_topic_0114912370_p182748510114"></a><a name="zh-cn_topic_0114912370_p182748510114"></a>s3.2xlarge.2</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0114912370_p32787510117"><a name="zh-cn_topic_0114912370_p32787510117"></a><a name="zh-cn_topic_0114912370_p32787510117"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row136049301908"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p19286451118"><a name="zh-cn_topic_0114912370_p19286451118"></a><a name="zh-cn_topic_0114912370_p19286451118"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p132901651817"><a name="zh-cn_topic_0114912370_p132901651817"></a><a name="zh-cn_topic_0114912370_p132901651817"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p1429320519115"><a name="zh-cn_topic_0114912370_p1429320519115"></a><a name="zh-cn_topic_0114912370_p1429320519115"></a>s3.4xlarge.2</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p152968511111"><a name="zh-cn_topic_0114912370_p152968511111"></a><a name="zh-cn_topic_0114912370_p152968511111"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row14459525505"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p193448511014"><a name="zh-cn_topic_0114912370_p193448511014"></a><a name="zh-cn_topic_0114912370_p193448511014"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p93482512115"><a name="zh-cn_topic_0114912370_p93482512115"></a><a name="zh-cn_topic_0114912370_p93482512115"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p6353105114118"><a name="zh-cn_topic_0114912370_p6353105114118"></a><a name="zh-cn_topic_0114912370_p6353105114118"></a>s3.xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p163577511015"><a name="zh-cn_topic_0114912370_p163577511015"></a><a name="zh-cn_topic_0114912370_p163577511015"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row34273588017"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p173841511713"><a name="zh-cn_topic_0114912370_p173841511713"></a><a name="zh-cn_topic_0114912370_p173841511713"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p138815120119"><a name="zh-cn_topic_0114912370_p138815120119"></a><a name="zh-cn_topic_0114912370_p138815120119"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p143951351811"><a name="zh-cn_topic_0114912370_p143951351811"></a><a name="zh-cn_topic_0114912370_p143951351811"></a>s3.4xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p43981518110"><a name="zh-cn_topic_0114912370_p43981518110"></a><a name="zh-cn_topic_0114912370_p43981518110"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row104412047125812"><td class="cellrowborder" rowspan="2" valign="top" width="23%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p14916958185820"><a name="zh-cn_topic_0114912370_p14916958185820"></a><a name="zh-cn_topic_0114912370_p14916958185820"></a>C2型</p>
<p id="zh-cn_topic_0114912370_p1994945818583"><a name="zh-cn_topic_0114912370_p1994945818583"></a><a name="zh-cn_topic_0114912370_p1994945818583"></a></p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p19917358145817"><a name="zh-cn_topic_0114912370_p19917358145817"></a><a name="zh-cn_topic_0114912370_p19917358145817"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p09209585583"><a name="zh-cn_topic_0114912370_p09209585583"></a><a name="zh-cn_topic_0114912370_p09209585583"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p5921115812583"><a name="zh-cn_topic_0114912370_p5921115812583"></a><a name="zh-cn_topic_0114912370_p5921115812583"></a>c2.2xlarge</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0114912370_p1292285815813"><a name="zh-cn_topic_0114912370_p1292285815813"></a><a name="zh-cn_topic_0114912370_p1292285815813"></a>XEN</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row85771564580"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p49261758205816"><a name="zh-cn_topic_0114912370_p49261758205816"></a><a name="zh-cn_topic_0114912370_p49261758205816"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p1992865825811"><a name="zh-cn_topic_0114912370_p1992865825811"></a><a name="zh-cn_topic_0114912370_p1992865825811"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p59301758125810"><a name="zh-cn_topic_0114912370_p59301758125810"></a><a name="zh-cn_topic_0114912370_p59301758125810"></a>c2.4xlarge</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p179311858145812"><a name="zh-cn_topic_0114912370_p179311858145812"></a><a name="zh-cn_topic_0114912370_p179311858145812"></a>XEN</p>
</td>
</tr>
</tbody>
</table>

**表 2**  通用计算增强型（C3型）弹性云服务器的规格

<a name="zh-cn_topic_0114912370_table3949605220464"></a>
<table><thead align="left"><tr id="zh-cn_topic_0114912370_row5755737620464"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0114912370_p32920979204624"><a name="zh-cn_topic_0114912370_p32920979204624"></a><a name="zh-cn_topic_0114912370_p32920979204624"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0114912370_p41529665204624"><a name="zh-cn_topic_0114912370_p41529665204624"></a><a name="zh-cn_topic_0114912370_p41529665204624"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0114912370_p9028760204624"><a name="zh-cn_topic_0114912370_p9028760204624"></a><a name="zh-cn_topic_0114912370_p9028760204624"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0114912370_p5297585204624"><a name="zh-cn_topic_0114912370_p5297585204624"></a><a name="zh-cn_topic_0114912370_p5297585204624"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0114912370_p84201252123120"><a name="zh-cn_topic_0114912370_p84201252123120"></a><a name="zh-cn_topic_0114912370_p84201252123120"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0114912370_row2115659920464"><td class="cellrowborder" rowspan="7" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p1639654719185"><a name="zh-cn_topic_0114912370_p1639654719185"></a><a name="zh-cn_topic_0114912370_p1639654719185"></a>C3型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p54672497204624"><a name="zh-cn_topic_0114912370_p54672497204624"></a><a name="zh-cn_topic_0114912370_p54672497204624"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p66396173204624"><a name="zh-cn_topic_0114912370_p66396173204624"></a><a name="zh-cn_topic_0114912370_p66396173204624"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p9380900204624"><a name="zh-cn_topic_0114912370_p9380900204624"></a><a name="zh-cn_topic_0114912370_p9380900204624"></a>c3.xlarge.2</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0114912370_p714614176327"><a name="zh-cn_topic_0114912370_p714614176327"></a><a name="zh-cn_topic_0114912370_p714614176327"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row1339712614367"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p10361184613360"><a name="zh-cn_topic_0114912370_p10361184613360"></a><a name="zh-cn_topic_0114912370_p10361184613360"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p1036104612367"><a name="zh-cn_topic_0114912370_p1036104612367"></a><a name="zh-cn_topic_0114912370_p1036104612367"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p8361104613610"><a name="zh-cn_topic_0114912370_p8361104613610"></a><a name="zh-cn_topic_0114912370_p8361104613610"></a>c3.4xlarge.2</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p9361114613616"><a name="zh-cn_topic_0114912370_p9361114613616"></a><a name="zh-cn_topic_0114912370_p9361114613616"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row58396907204611"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p15110173204624"><a name="zh-cn_topic_0114912370_p15110173204624"></a><a name="zh-cn_topic_0114912370_p15110173204624"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p15964478204624"><a name="zh-cn_topic_0114912370_p15964478204624"></a><a name="zh-cn_topic_0114912370_p15964478204624"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p18054373204624"><a name="zh-cn_topic_0114912370_p18054373204624"></a><a name="zh-cn_topic_0114912370_p18054373204624"></a>c3.xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p1160181710322"><a name="zh-cn_topic_0114912370_p1160181710322"></a><a name="zh-cn_topic_0114912370_p1160181710322"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row19288388204611"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p8300597204624"><a name="zh-cn_topic_0114912370_p8300597204624"></a><a name="zh-cn_topic_0114912370_p8300597204624"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p1259733204624"><a name="zh-cn_topic_0114912370_p1259733204624"></a><a name="zh-cn_topic_0114912370_p1259733204624"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p34929558204624"><a name="zh-cn_topic_0114912370_p34929558204624"></a><a name="zh-cn_topic_0114912370_p34929558204624"></a>c3.2xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p11163171763213"><a name="zh-cn_topic_0114912370_p11163171763213"></a><a name="zh-cn_topic_0114912370_p11163171763213"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row39706029204611"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p29388703204624"><a name="zh-cn_topic_0114912370_p29388703204624"></a><a name="zh-cn_topic_0114912370_p29388703204624"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p31674728204624"><a name="zh-cn_topic_0114912370_p31674728204624"></a><a name="zh-cn_topic_0114912370_p31674728204624"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p15516174204624"><a name="zh-cn_topic_0114912370_p15516174204624"></a><a name="zh-cn_topic_0114912370_p15516174204624"></a>c3.4xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p14657219153217"><a name="zh-cn_topic_0114912370_p14657219153217"></a><a name="zh-cn_topic_0114912370_p14657219153217"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row4280432102715"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p19281183210278"><a name="zh-cn_topic_0114912370_p19281183210278"></a><a name="zh-cn_topic_0114912370_p19281183210278"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p128123211279"><a name="zh-cn_topic_0114912370_p128123211279"></a><a name="zh-cn_topic_0114912370_p128123211279"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p374558192715"><a name="zh-cn_topic_0114912370_p374558192715"></a><a name="zh-cn_topic_0114912370_p374558192715"></a>c3.8xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p14281153262720"><a name="zh-cn_topic_0114912370_p14281153262720"></a><a name="zh-cn_topic_0114912370_p14281153262720"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row28491536204611"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p42717549204624"><a name="zh-cn_topic_0114912370_p42717549204624"></a><a name="zh-cn_topic_0114912370_p42717549204624"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p37569478204624"><a name="zh-cn_topic_0114912370_p37569478204624"></a><a name="zh-cn_topic_0114912370_p37569478204624"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p23228883204624"><a name="zh-cn_topic_0114912370_p23228883204624"></a><a name="zh-cn_topic_0114912370_p23228883204624"></a>c3.15xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p16664419133218"><a name="zh-cn_topic_0114912370_p16664419133218"></a><a name="zh-cn_topic_0114912370_p16664419133218"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 3**  D2型弹性云服务器的规格

<a name="zh-cn_topic_0114912370_table47541937112515"></a>
<table><thead align="left"><tr id="zh-cn_topic_0114912370_row1775413371257"><th class="cellrowborder" valign="top" width="13%" id="mcps1.2.8.1.1"><p id="zh-cn_topic_0114912370_p17228105016252"><a name="zh-cn_topic_0114912370_p17228105016252"></a><a name="zh-cn_topic_0114912370_p17228105016252"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="8%" id="mcps1.2.8.1.2"><p id="zh-cn_topic_0114912370_p123165013254"><a name="zh-cn_topic_0114912370_p123165013254"></a><a name="zh-cn_topic_0114912370_p123165013254"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="11%" id="mcps1.2.8.1.3"><p id="zh-cn_topic_0114912370_p7236185013252"><a name="zh-cn_topic_0114912370_p7236185013252"></a><a name="zh-cn_topic_0114912370_p7236185013252"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.8.1.4"><p id="zh-cn_topic_0114912370_p18237155062514"><a name="zh-cn_topic_0114912370_p18237155062514"></a><a name="zh-cn_topic_0114912370_p18237155062514"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="11%" id="mcps1.2.8.1.5"><p id="zh-cn_topic_0114912370_p724035017257"><a name="zh-cn_topic_0114912370_p724035017257"></a><a name="zh-cn_topic_0114912370_p724035017257"></a>虚拟化类型</p>
</th>
<th class="cellrowborder" valign="top" width="13%" id="mcps1.2.8.1.6"><p id="zh-cn_topic_0114912370_p1624105092519"><a name="zh-cn_topic_0114912370_p1624105092519"></a><a name="zh-cn_topic_0114912370_p1624105092519"></a>本地盘（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="28.999999999999996%" id="mcps1.2.8.1.7"><p id="zh-cn_topic_0114912370_p9205101061511"><a name="zh-cn_topic_0114912370_p9205101061511"></a><a name="zh-cn_topic_0114912370_p9205101061511"></a>硬件配置</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0114912370_row974834394812"><td class="cellrowborder" rowspan="3" valign="top" width="13%" headers="mcps1.2.8.1.1 "><p id="zh-cn_topic_0114912370_p9760548192919"><a name="zh-cn_topic_0114912370_p9760548192919"></a><a name="zh-cn_topic_0114912370_p9760548192919"></a>D2型</p>
</td>
<td class="cellrowborder" valign="top" width="8%" headers="mcps1.2.8.1.2 "><p id="zh-cn_topic_0114912370_p12750124311482"><a name="zh-cn_topic_0114912370_p12750124311482"></a><a name="zh-cn_topic_0114912370_p12750124311482"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="11%" headers="mcps1.2.8.1.3 "><p id="zh-cn_topic_0114912370_p0750164314813"><a name="zh-cn_topic_0114912370_p0750164314813"></a><a name="zh-cn_topic_0114912370_p0750164314813"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.8.1.4 "><p id="zh-cn_topic_0114912370_p1175054394818"><a name="zh-cn_topic_0114912370_p1175054394818"></a><a name="zh-cn_topic_0114912370_p1175054394818"></a>d2.2xlarge.8</p>
</td>
<td class="cellrowborder" valign="top" width="11%" headers="mcps1.2.8.1.5 "><p id="zh-cn_topic_0114912370_p1875013430483"><a name="zh-cn_topic_0114912370_p1875013430483"></a><a name="zh-cn_topic_0114912370_p1875013430483"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.8.1.6 "><p id="zh-cn_topic_0114912370_p17750443104811"><a name="zh-cn_topic_0114912370_p17750443104811"></a><a name="zh-cn_topic_0114912370_p17750443104811"></a>4×1800</p>
</td>
<td class="cellrowborder" rowspan="3" valign="top" width="28.999999999999996%" headers="mcps1.2.8.1.7 "><p id="zh-cn_topic_0114912370_p449920318167"><a name="zh-cn_topic_0114912370_p449920318167"></a><a name="zh-cn_topic_0114912370_p449920318167"></a>CPU：Intel&reg; Xeon&reg; Gold 6151 Processor v5</p>
<p id="zh-cn_topic_0114912370_p676115981618"><a name="zh-cn_topic_0114912370_p676115981618"></a><a name="zh-cn_topic_0114912370_p676115981618"></a>Memory：20×32GB</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row14967171717297"><td class="cellrowborder" valign="top" headers="mcps1.2.8.1.1 "><p id="zh-cn_topic_0114912370_p1492123262911"><a name="zh-cn_topic_0114912370_p1492123262911"></a><a name="zh-cn_topic_0114912370_p1492123262911"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.8.1.2 "><p id="zh-cn_topic_0114912370_p18434144113294"><a name="zh-cn_topic_0114912370_p18434144113294"></a><a name="zh-cn_topic_0114912370_p18434144113294"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.8.1.3 "><p id="zh-cn_topic_0114912370_p196727215299"><a name="zh-cn_topic_0114912370_p196727215299"></a><a name="zh-cn_topic_0114912370_p196727215299"></a>d2.4xlarge.8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.8.1.4 "><p id="zh-cn_topic_0114912370_p10967117172915"><a name="zh-cn_topic_0114912370_p10967117172915"></a><a name="zh-cn_topic_0114912370_p10967117172915"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.8.1.5 "><p id="zh-cn_topic_0114912370_p169678175293"><a name="zh-cn_topic_0114912370_p169678175293"></a><a name="zh-cn_topic_0114912370_p169678175293"></a>8×1800</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row575615372253"><td class="cellrowborder" valign="top" headers="mcps1.2.8.1.1 "><p id="zh-cn_topic_0114912370_p692123252911"><a name="zh-cn_topic_0114912370_p692123252911"></a><a name="zh-cn_topic_0114912370_p692123252911"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.8.1.2 "><p id="zh-cn_topic_0114912370_p13434174116295"><a name="zh-cn_topic_0114912370_p13434174116295"></a><a name="zh-cn_topic_0114912370_p13434174116295"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.8.1.3 "><p id="zh-cn_topic_0114912370_p1667222172917"><a name="zh-cn_topic_0114912370_p1667222172917"></a><a name="zh-cn_topic_0114912370_p1667222172917"></a>d2.8xlarge.8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.8.1.4 "><p id="zh-cn_topic_0114912370_p10756133715250"><a name="zh-cn_topic_0114912370_p10756133715250"></a><a name="zh-cn_topic_0114912370_p10756133715250"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.8.1.5 "><p id="zh-cn_topic_0114912370_p1675663717258"><a name="zh-cn_topic_0114912370_p1675663717258"></a><a name="zh-cn_topic_0114912370_p1675663717258"></a>16×1800</p>
</td>
</tr>
</tbody>
</table>

**表 4**  通用网络增强型（C3ne型）弹性云服务器的规格

<a name="zh-cn_topic_0114912370_table11476142712139"></a>
<table><thead align="left"><tr id="zh-cn_topic_0114912370_row248302717130"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0114912370_p18485182714134"><a name="zh-cn_topic_0114912370_p18485182714134"></a><a name="zh-cn_topic_0114912370_p18485182714134"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0114912370_p6486327141310"><a name="zh-cn_topic_0114912370_p6486327141310"></a><a name="zh-cn_topic_0114912370_p6486327141310"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0114912370_p1548752701319"><a name="zh-cn_topic_0114912370_p1548752701319"></a><a name="zh-cn_topic_0114912370_p1548752701319"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0114912370_p144891327201312"><a name="zh-cn_topic_0114912370_p144891327201312"></a><a name="zh-cn_topic_0114912370_p144891327201312"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0114912370_p8491182781311"><a name="zh-cn_topic_0114912370_p8491182781311"></a><a name="zh-cn_topic_0114912370_p8491182781311"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0114912370_row19592290395"><td class="cellrowborder" rowspan="7" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p18577182810127"><a name="zh-cn_topic_0114912370_p18577182810127"></a><a name="zh-cn_topic_0114912370_p18577182810127"></a>C3ne型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p16960192919392"><a name="zh-cn_topic_0114912370_p16960192919392"></a><a name="zh-cn_topic_0114912370_p16960192919392"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p796082910391"><a name="zh-cn_topic_0114912370_p796082910391"></a><a name="zh-cn_topic_0114912370_p796082910391"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p19609298391"><a name="zh-cn_topic_0114912370_p19609298391"></a><a name="zh-cn_topic_0114912370_p19609298391"></a>c3ne.2xlarge.2</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0114912370_p79601729193912"><a name="zh-cn_topic_0114912370_p79601729193912"></a><a name="zh-cn_topic_0114912370_p79601729193912"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row13366357164315"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p336615713438"><a name="zh-cn_topic_0114912370_p336615713438"></a><a name="zh-cn_topic_0114912370_p336615713438"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p8366857194320"><a name="zh-cn_topic_0114912370_p8366857194320"></a><a name="zh-cn_topic_0114912370_p8366857194320"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p236645714431"><a name="zh-cn_topic_0114912370_p236645714431"></a><a name="zh-cn_topic_0114912370_p236645714431"></a>c3ne.xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p1366195712438"><a name="zh-cn_topic_0114912370_p1366195712438"></a><a name="zh-cn_topic_0114912370_p1366195712438"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row44931727151314"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p10334247131610"><a name="zh-cn_topic_0114912370_p10334247131610"></a><a name="zh-cn_topic_0114912370_p10334247131610"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p1133444771614"><a name="zh-cn_topic_0114912370_p1133444771614"></a><a name="zh-cn_topic_0114912370_p1133444771614"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p649832715135"><a name="zh-cn_topic_0114912370_p649832715135"></a><a name="zh-cn_topic_0114912370_p649832715135"></a>c3ne.2xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p3500627141315"><a name="zh-cn_topic_0114912370_p3500627141315"></a><a name="zh-cn_topic_0114912370_p3500627141315"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row15500827171318"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p2033214721612"><a name="zh-cn_topic_0114912370_p2033214721612"></a><a name="zh-cn_topic_0114912370_p2033214721612"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p10331174719160"><a name="zh-cn_topic_0114912370_p10331174719160"></a><a name="zh-cn_topic_0114912370_p10331174719160"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p2095019446162"><a name="zh-cn_topic_0114912370_p2095019446162"></a><a name="zh-cn_topic_0114912370_p2095019446162"></a>c3ne.4xlarge.2</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p550712761320"><a name="zh-cn_topic_0114912370_p550712761320"></a><a name="zh-cn_topic_0114912370_p550712761320"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row65084277136"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p11331184712166"><a name="zh-cn_topic_0114912370_p11331184712166"></a><a name="zh-cn_topic_0114912370_p11331184712166"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p83309476165"><a name="zh-cn_topic_0114912370_p83309476165"></a><a name="zh-cn_topic_0114912370_p83309476165"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p16950134421617"><a name="zh-cn_topic_0114912370_p16950134421617"></a><a name="zh-cn_topic_0114912370_p16950134421617"></a>c3ne.4xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p25131927161318"><a name="zh-cn_topic_0114912370_p25131927161318"></a><a name="zh-cn_topic_0114912370_p25131927161318"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row0515192701316"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p732911474164"><a name="zh-cn_topic_0114912370_p732911474164"></a><a name="zh-cn_topic_0114912370_p732911474164"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p143271447121619"><a name="zh-cn_topic_0114912370_p143271447121619"></a><a name="zh-cn_topic_0114912370_p143271447121619"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p109491644121618"><a name="zh-cn_topic_0114912370_p109491644121618"></a><a name="zh-cn_topic_0114912370_p109491644121618"></a>c3ne.8xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p12522102751311"><a name="zh-cn_topic_0114912370_p12522102751311"></a><a name="zh-cn_topic_0114912370_p12522102751311"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0114912370_row6523142718132"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0114912370_p1232604711613"><a name="zh-cn_topic_0114912370_p1232604711613"></a><a name="zh-cn_topic_0114912370_p1232604711613"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0114912370_p232584751612"><a name="zh-cn_topic_0114912370_p232584751612"></a><a name="zh-cn_topic_0114912370_p232584751612"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0114912370_p17947144411168"><a name="zh-cn_topic_0114912370_p17947144411168"></a><a name="zh-cn_topic_0114912370_p17947144411168"></a>c3ne.15xlarge.4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0114912370_p19528627131314"><a name="zh-cn_topic_0114912370_p19528627131314"></a><a name="zh-cn_topic_0114912370_p19528627131314"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

