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

## 规格命名规则<a name="section741930611313"></a>

AB.C.D

例如m2.8xlarge.8

其中，

-   A表示系列，例如：s表示通用型、c表示计算型、m表示内存型。
-   B表示系列号，例如：s1中的1表示通用型I代，s2中2表示通用型II代。
-   C表示规格，当前系列中的规格大小，例如：medium、large、xlarge。
-   D表示内存、CPU比，以具体数字表示，例如4表示内存和CPU的比值为4。

## 规格<a name="section1399585312355"></a>

**表 1**  通用计算型弹性云服务器的规格

<a name="tcd38be0eaa3344d598e51b2e4aec0664"></a>
<table><thead align="left"><tr id="raa686957db654aaa953a8fa41c41d2e2"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.6.1.1"><p id="aab78eca7da7f4880bf549e747372c98e"><a name="aab78eca7da7f4880bf549e747372c98e"></a><a name="aab78eca7da7f4880bf549e747372c98e"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23%" id="mcps1.2.6.1.2"><p id="a04a6ba7df69b44a9869919a9ebcf53fd"><a name="a04a6ba7df69b44a9869919a9ebcf53fd"></a><a name="a04a6ba7df69b44a9869919a9ebcf53fd"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.6.1.3"><p id="abe32edd5ef88411a9af49d35057feab7"><a name="abe32edd5ef88411a9af49d35057feab7"></a><a name="abe32edd5ef88411a9af49d35057feab7"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="21%" id="mcps1.2.6.1.4"><p id="af53b94488f424003820358080b3ba6f0"><a name="af53b94488f424003820358080b3ba6f0"></a><a name="af53b94488f424003820358080b3ba6f0"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12%" id="mcps1.2.6.1.5"><p id="a0d3ebfafe57447caa7a74e19604e8b70"><a name="a0d3ebfafe57447caa7a74e19604e8b70"></a><a name="a0d3ebfafe57447caa7a74e19604e8b70"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="rbfe1b75f66b7434fb593e62c82a344f9"><td class="cellrowborder" rowspan="5" valign="top" width="23%" headers="mcps1.2.6.1.1 "><p id="a0d2113fa64874aceacf1490431c0f1a4"><a name="a0d2113fa64874aceacf1490431c0f1a4"></a><a name="a0d2113fa64874aceacf1490431c0f1a4"></a>S3型</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.6.1.2 "><p id="a00abdcd4c45e4acfba0a152e526a97ec"><a name="a00abdcd4c45e4acfba0a152e526a97ec"></a><a name="a00abdcd4c45e4acfba0a152e526a97ec"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.3 "><p id="a13600b1a9f1940cc9379be1e9931dd19"><a name="a13600b1a9f1940cc9379be1e9931dd19"></a><a name="a13600b1a9f1940cc9379be1e9931dd19"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="21%" headers="mcps1.2.6.1.4 "><p id="a153388230ec6435684015341b83e7a84"><a name="a153388230ec6435684015341b83e7a84"></a><a name="a153388230ec6435684015341b83e7a84"></a>s3.xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.6.1.5 "><p id="ac22fdd0cf0a2425bbe4f75964c65829d"><a name="ac22fdd0cf0a2425bbe4f75964c65829d"></a><a name="ac22fdd0cf0a2425bbe4f75964c65829d"></a>KVM</p>
</td>
</tr>
<tr id="r15b31e288e564541aab77374137da163"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="af4633071f6a1462685a99c65db95e3d9"><a name="af4633071f6a1462685a99c65db95e3d9"></a><a name="af4633071f6a1462685a99c65db95e3d9"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a455634b21f934b98ad3863f2421ad799"><a name="a455634b21f934b98ad3863f2421ad799"></a><a name="a455634b21f934b98ad3863f2421ad799"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a81ca798226bf4d12a4190dea2bbd4456"><a name="a81ca798226bf4d12a4190dea2bbd4456"></a><a name="a81ca798226bf4d12a4190dea2bbd4456"></a>s3.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a908594591ad248c2869c054017abfe96"><a name="a908594591ad248c2869c054017abfe96"></a><a name="a908594591ad248c2869c054017abfe96"></a>KVM</p>
</td>
</tr>
<tr id="rebe7443260624202adb83677549fe6fd"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a80176b3b6c47446abc04c277042a7d36"><a name="a80176b3b6c47446abc04c277042a7d36"></a><a name="a80176b3b6c47446abc04c277042a7d36"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="af1494536766149daaf8a355e07a41828"><a name="af1494536766149daaf8a355e07a41828"></a><a name="af1494536766149daaf8a355e07a41828"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a7a726f6f666e488dbd049829d1f31a50"><a name="a7a726f6f666e488dbd049829d1f31a50"></a><a name="a7a726f6f666e488dbd049829d1f31a50"></a>s3.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="aa45abbcff32d4fa288383480d75fb385"><a name="aa45abbcff32d4fa288383480d75fb385"></a><a name="aa45abbcff32d4fa288383480d75fb385"></a>KVM</p>
</td>
</tr>
<tr id="re693e2e9b3384c9c8f1ae5daac9042ea"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ab16b375559d94e93bc2f652e3f068cd4"><a name="ab16b375559d94e93bc2f652e3f068cd4"></a><a name="ab16b375559d94e93bc2f652e3f068cd4"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a8e2df9e1ff8041a6b5feba13d3906648"><a name="a8e2df9e1ff8041a6b5feba13d3906648"></a><a name="a8e2df9e1ff8041a6b5feba13d3906648"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="adf57619f64254404973645a753ed73f2"><a name="adf57619f64254404973645a753ed73f2"></a><a name="adf57619f64254404973645a753ed73f2"></a>s3.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="ad1ab0b69d61e4a008a0ddc6ea25ebe93"><a name="ad1ab0b69d61e4a008a0ddc6ea25ebe93"></a><a name="ad1ab0b69d61e4a008a0ddc6ea25ebe93"></a>KVM</p>
</td>
</tr>
<tr id="r64081f12b5a4466da692e4dcfe2d3aa7"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a102218a974ea4d6c8889502c904184ac"><a name="a102218a974ea4d6c8889502c904184ac"></a><a name="a102218a974ea4d6c8889502c904184ac"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a620e8c0edde5474f9f8db82e259edbbe"><a name="a620e8c0edde5474f9f8db82e259edbbe"></a><a name="a620e8c0edde5474f9f8db82e259edbbe"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a287433c62fa54ef9851fff63df0e0aa9"><a name="a287433c62fa54ef9851fff63df0e0aa9"></a><a name="a287433c62fa54ef9851fff63df0e0aa9"></a>s3.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a366718877e5f44cd848d87885058e62e"><a name="a366718877e5f44cd848d87885058e62e"></a><a name="a366718877e5f44cd848d87885058e62e"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 2**  通用计算增强型（C3型）弹性云服务器的规格

<a name="t6d396a6fe7ee474b9c566647f7a30f79"></a>
<table><thead align="left"><tr id="r20b85517a0ee4d059f038c3b53ee352d"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="a96e10e3a409a472286b7e3ce16d9f3fa"><a name="a96e10e3a409a472286b7e3ce16d9f3fa"></a><a name="a96e10e3a409a472286b7e3ce16d9f3fa"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="acbbd8d30c1de4e2f9ad6a7eecc3f61ee"><a name="acbbd8d30c1de4e2f9ad6a7eecc3f61ee"></a><a name="acbbd8d30c1de4e2f9ad6a7eecc3f61ee"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="a8623d6c86d8d494d8bd79d59e07de84e"><a name="a8623d6c86d8d494d8bd79d59e07de84e"></a><a name="a8623d6c86d8d494d8bd79d59e07de84e"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="a2268bb9c633b4082a8b0077f8136c398"><a name="a2268bb9c633b4082a8b0077f8136c398"></a><a name="a2268bb9c633b4082a8b0077f8136c398"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="a5cd841eb6ba64eca9258e9c71726f9c9"><a name="a5cd841eb6ba64eca9258e9c71726f9c9"></a><a name="a5cd841eb6ba64eca9258e9c71726f9c9"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="re3228f0b9b8c427e93c519f747d60e75"><td class="cellrowborder" rowspan="7" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="aaf6bc4398cfa46ce8971c7f076499fce"><a name="aaf6bc4398cfa46ce8971c7f076499fce"></a><a name="aaf6bc4398cfa46ce8971c7f076499fce"></a>C3型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="a3c9a47316fcb4d23b4f76d3e2b556176"><a name="a3c9a47316fcb4d23b4f76d3e2b556176"></a><a name="a3c9a47316fcb4d23b4f76d3e2b556176"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="ad014ac021e3c48e2b7637bf1e034e593"><a name="ad014ac021e3c48e2b7637bf1e034e593"></a><a name="ad014ac021e3c48e2b7637bf1e034e593"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="a83f4092bfc2c48aa90cbd9c85d8ebde9"><a name="a83f4092bfc2c48aa90cbd9c85d8ebde9"></a><a name="a83f4092bfc2c48aa90cbd9c85d8ebde9"></a>c3.xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="af837b46286524b1aa4530e6546b10853"><a name="af837b46286524b1aa4530e6546b10853"></a><a name="af837b46286524b1aa4530e6546b10853"></a>KVM</p>
</td>
</tr>
<tr id="r444611be5b3f49009f7aef27ee2c863f"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a85a24198699e42f5bfd8ced2b5f52016"><a name="a85a24198699e42f5bfd8ced2b5f52016"></a><a name="a85a24198699e42f5bfd8ced2b5f52016"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a5766776561854ab2a44aef33fdf1bb10"><a name="a5766776561854ab2a44aef33fdf1bb10"></a><a name="a5766776561854ab2a44aef33fdf1bb10"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="ab083b59dab8b43998a9ca76d3d0398a4"><a name="ab083b59dab8b43998a9ca76d3d0398a4"></a><a name="ab083b59dab8b43998a9ca76d3d0398a4"></a>c3.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a91cec5825d0041daac0a94a694e0de3a"><a name="a91cec5825d0041daac0a94a694e0de3a"></a><a name="a91cec5825d0041daac0a94a694e0de3a"></a>KVM</p>
</td>
</tr>
<tr id="r5fb3ae0398ba49b0a56843cf6cc2d43e"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="afd34df7bc05f4efe85a100f9f82793ad"><a name="afd34df7bc05f4efe85a100f9f82793ad"></a><a name="afd34df7bc05f4efe85a100f9f82793ad"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ac29d2fc7ff884654ba6ebd390ab49d2d"><a name="ac29d2fc7ff884654ba6ebd390ab49d2d"></a><a name="ac29d2fc7ff884654ba6ebd390ab49d2d"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="aa5457d34154f446dae77d9cdbfc976d9"><a name="aa5457d34154f446dae77d9cdbfc976d9"></a><a name="aa5457d34154f446dae77d9cdbfc976d9"></a>c3.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a24b17e507c464811b705c0220da17c6c"><a name="a24b17e507c464811b705c0220da17c6c"></a><a name="a24b17e507c464811b705c0220da17c6c"></a>KVM</p>
</td>
</tr>
<tr id="r1bdf742d94fe424ab27a0cbb9b842475"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a0bd9160bffe04c96bb182f07bf975f86"><a name="a0bd9160bffe04c96bb182f07bf975f86"></a><a name="a0bd9160bffe04c96bb182f07bf975f86"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a1e88ce61ff074142997ac68565613cfd"><a name="a1e88ce61ff074142997ac68565613cfd"></a><a name="a1e88ce61ff074142997ac68565613cfd"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="add1bbe9f837547df80b11371d2fc2a5b"><a name="add1bbe9f837547df80b11371d2fc2a5b"></a><a name="add1bbe9f837547df80b11371d2fc2a5b"></a>c3.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a397bd693c9554b39b9c67a9eadcfac3c"><a name="a397bd693c9554b39b9c67a9eadcfac3c"></a><a name="a397bd693c9554b39b9c67a9eadcfac3c"></a>KVM</p>
</td>
</tr>
<tr id="r434d70b34d154938adee6a65ddc0680a"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="aaf1ee0d24d4249cd830caf0395ad9870"><a name="aaf1ee0d24d4249cd830caf0395ad9870"></a><a name="aaf1ee0d24d4249cd830caf0395ad9870"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a62fba3331de14c85aecbfb1280d72e62"><a name="a62fba3331de14c85aecbfb1280d72e62"></a><a name="a62fba3331de14c85aecbfb1280d72e62"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a3ecd86b73cff4ea9bb83df4591f3a911"><a name="a3ecd86b73cff4ea9bb83df4591f3a911"></a><a name="a3ecd86b73cff4ea9bb83df4591f3a911"></a>c3.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a50f9a6759ff744e996aceb2e62320903"><a name="a50f9a6759ff744e996aceb2e62320903"></a><a name="a50f9a6759ff744e996aceb2e62320903"></a>KVM</p>
</td>
</tr>
<tr id="r63211794a7ff44738fa57816441007cb"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ae6e2f363f7f74d7ebde65a8c5f12d3d7"><a name="ae6e2f363f7f74d7ebde65a8c5f12d3d7"></a><a name="ae6e2f363f7f74d7ebde65a8c5f12d3d7"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ac04792fdb1c34043974adc5fcbad0dee"><a name="ac04792fdb1c34043974adc5fcbad0dee"></a><a name="ac04792fdb1c34043974adc5fcbad0dee"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a1f64f383f6474d9f814ccb1e864302b9"><a name="a1f64f383f6474d9f814ccb1e864302b9"></a><a name="a1f64f383f6474d9f814ccb1e864302b9"></a>c3.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="ad3e7540caaab4228971f94eb266b043a"><a name="ad3e7540caaab4228971f94eb266b043a"></a><a name="ad3e7540caaab4228971f94eb266b043a"></a>KVM</p>
</td>
</tr>
<tr id="rb06cfb144f0641c180e10d045b61b492"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a0084472c369b4c40a84ad3fd009b5061"><a name="a0084472c369b4c40a84ad3fd009b5061"></a><a name="a0084472c369b4c40a84ad3fd009b5061"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="aba9c0f5fc96146bbb27a39940ce02faa"><a name="aba9c0f5fc96146bbb27a39940ce02faa"></a><a name="aba9c0f5fc96146bbb27a39940ce02faa"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a384730a6ed8f4a05bcec169a25f9b2ca"><a name="a384730a6ed8f4a05bcec169a25f9b2ca"></a><a name="a384730a6ed8f4a05bcec169a25f9b2ca"></a>c3.15xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="ab8eaaaec15cf40218c3935ae599f4f41"><a name="ab8eaaaec15cf40218c3935ae599f4f41"></a><a name="ab8eaaaec15cf40218c3935ae599f4f41"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 3**  通用计算增强型（C6型）弹性云服务器的规格

<a name="t088ca85d6bc44f39a501d12952f18ac7"></a>
<table><thead align="left"><tr id="r7f17cbc9f94847dd8a8ba14bc82b61a1"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="a5e402a6975fe4339bebdd5eb159cbdd0"><a name="a5e402a6975fe4339bebdd5eb159cbdd0"></a><a name="a5e402a6975fe4339bebdd5eb159cbdd0"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="ad6219165a4d443b09b4c7716fd9f18dc"><a name="ad6219165a4d443b09b4c7716fd9f18dc"></a><a name="ad6219165a4d443b09b4c7716fd9f18dc"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="acb3a4da62e1a40c78e518d7e8a452f73"><a name="acb3a4da62e1a40c78e518d7e8a452f73"></a><a name="acb3a4da62e1a40c78e518d7e8a452f73"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="ab422bf517e8043b4b5277f00c09f65dd"><a name="ab422bf517e8043b4b5277f00c09f65dd"></a><a name="ab422bf517e8043b4b5277f00c09f65dd"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="a7b202f0a4ba849d5af1cef153959ac7d"><a name="a7b202f0a4ba849d5af1cef153959ac7d"></a><a name="a7b202f0a4ba849d5af1cef153959ac7d"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="r39b08fcefccc418d9738153e707260cc"><td class="cellrowborder" rowspan="9" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="aad097c9639b7409c8584a8ca441bcd14"><a name="aad097c9639b7409c8584a8ca441bcd14"></a><a name="aad097c9639b7409c8584a8ca441bcd14"></a>C6型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="a6e5be023b66440619184fa557ee08580"><a name="a6e5be023b66440619184fa557ee08580"></a><a name="a6e5be023b66440619184fa557ee08580"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="afb2f80dd6587417a982d7cd805beb37c"><a name="afb2f80dd6587417a982d7cd805beb37c"></a><a name="afb2f80dd6587417a982d7cd805beb37c"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="a83a910865d5348019b67806fa5a6635b"><a name="a83a910865d5348019b67806fa5a6635b"></a><a name="a83a910865d5348019b67806fa5a6635b"></a>c6.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="a511bd5b5b36d4dc8ad42a30c6b3b6005"><a name="a511bd5b5b36d4dc8ad42a30c6b3b6005"></a><a name="a511bd5b5b36d4dc8ad42a30c6b3b6005"></a>KVM</p>
</td>
</tr>
<tr id="rd5036ef055564775b57195bffb9e3d03"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="aa36af005c95740efb889d921a77f4280"><a name="aa36af005c95740efb889d921a77f4280"></a><a name="aa36af005c95740efb889d921a77f4280"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="aa0c0f5141a7447fdb2a0b9f15ab11663"><a name="aa0c0f5141a7447fdb2a0b9f15ab11663"></a><a name="aa0c0f5141a7447fdb2a0b9f15ab11663"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="aa75d8de7d9ef4bd7925ac114b2b1841b"><a name="aa75d8de7d9ef4bd7925ac114b2b1841b"></a><a name="aa75d8de7d9ef4bd7925ac114b2b1841b"></a>c6.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a726389906fd34d498454741ff7db9d38"><a name="a726389906fd34d498454741ff7db9d38"></a><a name="a726389906fd34d498454741ff7db9d38"></a>KVM</p>
</td>
</tr>
<tr id="r903c4e6530ab45f9995d4bdaf8dfd1d4"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a3fbb4bbf4c0c491289112bc0759cfbc0"><a name="a3fbb4bbf4c0c491289112bc0759cfbc0"></a><a name="a3fbb4bbf4c0c491289112bc0759cfbc0"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="aa082e7437b5e4e20ba5782243e142a5e"><a name="aa082e7437b5e4e20ba5782243e142a5e"></a><a name="aa082e7437b5e4e20ba5782243e142a5e"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a906e4dc9df744a7a85e49ccb3c1ffe0d"><a name="a906e4dc9df744a7a85e49ccb3c1ffe0d"></a><a name="a906e4dc9df744a7a85e49ccb3c1ffe0d"></a>c6.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="aae00774c327c4fedb0fe3fed35804b67"><a name="aae00774c327c4fedb0fe3fed35804b67"></a><a name="aae00774c327c4fedb0fe3fed35804b67"></a>KVM</p>
</td>
</tr>
<tr id="re244dca304394ec39e5f5b8a8ce5dff8"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="abc00125114b04e58b49a3101fe2a11d1"><a name="abc00125114b04e58b49a3101fe2a11d1"></a><a name="abc00125114b04e58b49a3101fe2a11d1"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a18328149818842bfb09fa66a8d2b4add"><a name="a18328149818842bfb09fa66a8d2b4add"></a><a name="a18328149818842bfb09fa66a8d2b4add"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a5d58620ad33f4015abf1d0223c05eaca"><a name="a5d58620ad33f4015abf1d0223c05eaca"></a><a name="a5d58620ad33f4015abf1d0223c05eaca"></a>c6.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a57eb1cf91893454aa2a9d2146a3bcdc4"><a name="a57eb1cf91893454aa2a9d2146a3bcdc4"></a><a name="a57eb1cf91893454aa2a9d2146a3bcdc4"></a>KVM</p>
</td>
</tr>
<tr id="r4e40e0621227469493b11f28e659293d"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="acf1e41f744ed49c9ab8b400ddb213fd4"><a name="acf1e41f744ed49c9ab8b400ddb213fd4"></a><a name="acf1e41f744ed49c9ab8b400ddb213fd4"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a94fa31bc362a401483864b1a857fca9d"><a name="a94fa31bc362a401483864b1a857fca9d"></a><a name="a94fa31bc362a401483864b1a857fca9d"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="ab6f75981d83a4a62bd28bdc6a051061b"><a name="ab6f75981d83a4a62bd28bdc6a051061b"></a><a name="ab6f75981d83a4a62bd28bdc6a051061b"></a>c6.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a5a2cb2d67807456599468284349834f0"><a name="a5a2cb2d67807456599468284349834f0"></a><a name="a5a2cb2d67807456599468284349834f0"></a>KVM</p>
</td>
</tr>
<tr id="r19c17951f4924f94a595b7ed037f3ec4"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="af09d527a7d4542c9a76bcd11902f72b4"><a name="af09d527a7d4542c9a76bcd11902f72b4"></a><a name="af09d527a7d4542c9a76bcd11902f72b4"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a646594e599854f449cfb091481f4c0a5"><a name="a646594e599854f449cfb091481f4c0a5"></a><a name="a646594e599854f449cfb091481f4c0a5"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a924fcb1f1b7a49c894b76b8a3c2e4862"><a name="a924fcb1f1b7a49c894b76b8a3c2e4862"></a><a name="a924fcb1f1b7a49c894b76b8a3c2e4862"></a>c6.8xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a24996032c5524b6f99e86e929f9c35f4"><a name="a24996032c5524b6f99e86e929f9c35f4"></a><a name="a24996032c5524b6f99e86e929f9c35f4"></a>KVM</p>
</td>
</tr>
<tr id="r53dca7f3df8745f980105f715dc2961c"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a51fe3bc5d40146b6a63f53c3c3868214"><a name="a51fe3bc5d40146b6a63f53c3c3868214"></a><a name="a51fe3bc5d40146b6a63f53c3c3868214"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a9af730ade79e47db8a8dec7eb6d47ccb"><a name="a9af730ade79e47db8a8dec7eb6d47ccb"></a><a name="a9af730ade79e47db8a8dec7eb6d47ccb"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a9aae5678499e4becb7afec2b4604b097"><a name="a9aae5678499e4becb7afec2b4604b097"></a><a name="a9aae5678499e4becb7afec2b4604b097"></a>c6.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a2312f2f1c2cc41aaa65f2d30cfe32034"><a name="a2312f2f1c2cc41aaa65f2d30cfe32034"></a><a name="a2312f2f1c2cc41aaa65f2d30cfe32034"></a>KVM</p>
</td>
</tr>
<tr id="re2bc6b924fc34f39b1d4a985401b6440"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a97bd8a8a032a471c90504e5a8c073308"><a name="a97bd8a8a032a471c90504e5a8c073308"></a><a name="a97bd8a8a032a471c90504e5a8c073308"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a78b148952e5045808e27efc136eaca70"><a name="a78b148952e5045808e27efc136eaca70"></a><a name="a78b148952e5045808e27efc136eaca70"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a713e81711d584d72acfc9b80456b49d3"><a name="a713e81711d584d72acfc9b80456b49d3"></a><a name="a713e81711d584d72acfc9b80456b49d3"></a>c6.16xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a27d5e969c1e34e8080ba0bee0cb8f34f"><a name="a27d5e969c1e34e8080ba0bee0cb8f34f"></a><a name="a27d5e969c1e34e8080ba0bee0cb8f34f"></a>KVM</p>
</td>
</tr>
<tr id="rfef3fe5244204f319c36d734232124bf"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a32a6cc822ff349c69a24675dc8788af8"><a name="a32a6cc822ff349c69a24675dc8788af8"></a><a name="a32a6cc822ff349c69a24675dc8788af8"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ab0f73ad739fa4028add1a7abcf6cd155"><a name="ab0f73ad739fa4028add1a7abcf6cd155"></a><a name="ab0f73ad739fa4028add1a7abcf6cd155"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a9e8a669329c14aa29c07c44c03301848"><a name="a9e8a669329c14aa29c07c44c03301848"></a><a name="a9e8a669329c14aa29c07c44c03301848"></a>c6.16xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a250806d0bb114c74b05ff25c03a6cd18"><a name="a250806d0bb114c74b05ff25c03a6cd18"></a><a name="a250806d0bb114c74b05ff25c03a6cd18"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 4**  磁盘增强型型弹性云服务器的规格

<a name="t11ec54d208f74b81a701e00cbe266f6e"></a>
<table><thead align="left"><tr id="r6f844a0315ea40cb806688ca7d600dd0"><th class="cellrowborder" valign="top" width="18.17818218178182%" id="mcps1.2.7.1.1"><p id="afc1818d7e4154364b2e65aa079efa1f1"><a name="afc1818d7e4154364b2e65aa079efa1f1"></a><a name="afc1818d7e4154364b2e65aa079efa1f1"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="13.638636136386362%" id="mcps1.2.7.1.2"><p id="a2b60c444c9a443ddaab7f5cc90d89def"><a name="a2b60c444c9a443ddaab7f5cc90d89def"></a><a name="a2b60c444c9a443ddaab7f5cc90d89def"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="13.638636136386362%" id="mcps1.2.7.1.3"><p id="adff3cc271f584d44aeba19cd35297d46"><a name="adff3cc271f584d44aeba19cd35297d46"></a><a name="adff3cc271f584d44aeba19cd35297d46"></a>内存（GB）</p>
</th>
<th class="cellrowborder" valign="top" width="27.267273272672732%" id="mcps1.2.7.1.4"><p id="a32ff0e937968464e8600b39398a09b9c"><a name="a32ff0e937968464e8600b39398a09b9c"></a><a name="a32ff0e937968464e8600b39398a09b9c"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="13.638636136386362%" id="mcps1.2.7.1.5"><p id="a65c63765f16541d0a2469b7b109b67fb"><a name="a65c63765f16541d0a2469b7b109b67fb"></a><a name="a65c63765f16541d0a2469b7b109b67fb"></a>虚拟化类型</p>
</th>
<th class="cellrowborder" valign="top" width="13.638636136386362%" id="mcps1.2.7.1.6"><p id="aa997941156054b729deb7973d19ae798"><a name="aa997941156054b729deb7973d19ae798"></a><a name="aa997941156054b729deb7973d19ae798"></a>本地盘（GB）</p>
</th>
</tr>
</thead>
<tbody><tr id="rc7051f00343e472ea6eeb148ccb9f4da"><td class="cellrowborder" rowspan="3" valign="top" width="18.17818218178182%" headers="mcps1.2.7.1.1 "><p id="a38ab2a4e387e422e9fc2bd0a1fcd6b6c"><a name="a38ab2a4e387e422e9fc2bd0a1fcd6b6c"></a><a name="a38ab2a4e387e422e9fc2bd0a1fcd6b6c"></a>D2型</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.2 "><p id="a6a7e45546f0543209e70c4379507e483"><a name="a6a7e45546f0543209e70c4379507e483"></a><a name="a6a7e45546f0543209e70c4379507e483"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.3 "><p id="a55d01d5627ec47aab626cc7a935ddc88"><a name="a55d01d5627ec47aab626cc7a935ddc88"></a><a name="a55d01d5627ec47aab626cc7a935ddc88"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="27.267273272672732%" headers="mcps1.2.7.1.4 "><p id="aed70c6aa1f1240de9d61bf17714d5a16"><a name="aed70c6aa1f1240de9d61bf17714d5a16"></a><a name="aed70c6aa1f1240de9d61bf17714d5a16"></a>d2.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.5 "><p id="a9304b6bbd8f9436c91456a73c8ed4382"><a name="a9304b6bbd8f9436c91456a73c8ed4382"></a><a name="a9304b6bbd8f9436c91456a73c8ed4382"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.6 "><p id="add12067a9d3044ad93105e4a485836ad"><a name="add12067a9d3044ad93105e4a485836ad"></a><a name="add12067a9d3044ad93105e4a485836ad"></a>4×1800</p>
</td>
</tr>
<tr id="r77cdeb104e5a4a23b076f33c97712337"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="a2f0613f4f27442479f36a1c8a6a88547"><a name="a2f0613f4f27442479f36a1c8a6a88547"></a><a name="a2f0613f4f27442479f36a1c8a6a88547"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="af7cade169f8c433a97617bbf51a4780d"><a name="af7cade169f8c433a97617bbf51a4780d"></a><a name="af7cade169f8c433a97617bbf51a4780d"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="a54e48bee01464ae287aa89f51195b8a3"><a name="a54e48bee01464ae287aa89f51195b8a3"></a><a name="a54e48bee01464ae287aa89f51195b8a3"></a>d2.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="a1d07a6af123f4bc2bff093001c08374e"><a name="a1d07a6af123f4bc2bff093001c08374e"></a><a name="a1d07a6af123f4bc2bff093001c08374e"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="a48b139dcbf2a4ad08e820be71eed7d66"><a name="a48b139dcbf2a4ad08e820be71eed7d66"></a><a name="a48b139dcbf2a4ad08e820be71eed7d66"></a>8×1800</p>
</td>
</tr>
<tr id="re3c6b758053a4b6391ef34f193e9416c"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="a43995e05e818443483b98d7c84e6fabd"><a name="a43995e05e818443483b98d7c84e6fabd"></a><a name="a43995e05e818443483b98d7c84e6fabd"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="a21b77d3e0753459795eba821277ad1d2"><a name="a21b77d3e0753459795eba821277ad1d2"></a><a name="a21b77d3e0753459795eba821277ad1d2"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="a8a322930ae0f489889ea6ddc35f08e76"><a name="a8a322930ae0f489889ea6ddc35f08e76"></a><a name="a8a322930ae0f489889ea6ddc35f08e76"></a>d2.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="aab052b31653744cca317742eefe4c504"><a name="aab052b31653744cca317742eefe4c504"></a><a name="aab052b31653744cca317742eefe4c504"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="a2f2ed6763e004aefb35c1f59f88cd6a2"><a name="a2f2ed6763e004aefb35c1f59f88cd6a2"></a><a name="a2f2ed6763e004aefb35c1f59f88cd6a2"></a>16×1800</p>
</td>
</tr>
<tr id="r6333e34aa8ff44e29cca7e27aa4e8f0b"><td class="cellrowborder" rowspan="4" valign="top" width="18.17818218178182%" headers="mcps1.2.7.1.1 "><p id="a6e6bf468365145999c927fd4c68049a4"><a name="a6e6bf468365145999c927fd4c68049a4"></a><a name="a6e6bf468365145999c927fd4c68049a4"></a>D3型</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.2 "><p id="a33460022f2f14214a6c1bc067530936b"><a name="a33460022f2f14214a6c1bc067530936b"></a><a name="a33460022f2f14214a6c1bc067530936b"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.3 "><p id="zh-cn_topic_0264269293_p72405452810"><a name="zh-cn_topic_0264269293_p72405452810"></a><a name="zh-cn_topic_0264269293_p72405452810"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="27.267273272672732%" headers="mcps1.2.7.1.4 "><p id="zh-cn_topic_0264269293_p8240642281"><a name="zh-cn_topic_0264269293_p8240642281"></a><a name="zh-cn_topic_0264269293_p8240642281"></a>d3.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.5 "><p id="a4ae3b198d11f47bcac661ba39091192f"><a name="a4ae3b198d11f47bcac661ba39091192f"></a><a name="a4ae3b198d11f47bcac661ba39091192f"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" width="13.638636136386362%" headers="mcps1.2.7.1.6 "><p id="zh-cn_topic_0264269293_p324010472813"><a name="zh-cn_topic_0264269293_p324010472813"></a><a name="zh-cn_topic_0264269293_p324010472813"></a>4 × 1800</p>
</td>
</tr>
<tr id="r31f8948a0b3a4bd5bb20a4ee25a6a8a7"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="zh-cn_topic_0264269293_p35002617286"><a name="zh-cn_topic_0264269293_p35002617286"></a><a name="zh-cn_topic_0264269293_p35002617286"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="zh-cn_topic_0264269293_p05003612816"><a name="zh-cn_topic_0264269293_p05003612816"></a><a name="zh-cn_topic_0264269293_p05003612816"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="zh-cn_topic_0264269293_p150019662813"><a name="zh-cn_topic_0264269293_p150019662813"></a><a name="zh-cn_topic_0264269293_p150019662813"></a>d3.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="zh-cn_topic_0264269293_p85001668282"><a name="zh-cn_topic_0264269293_p85001668282"></a><a name="zh-cn_topic_0264269293_p85001668282"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="a9c71dd082a054a5a954ee50106a9cda3"><a name="a9c71dd082a054a5a954ee50106a9cda3"></a><a name="a9c71dd082a054a5a954ee50106a9cda3"></a>8 × 1800</p>
</td>
</tr>
<tr id="rd8fb42e4da0e4f2894874c0e63aa43cb"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="zh-cn_topic_0264269293_p519450192418"><a name="zh-cn_topic_0264269293_p519450192418"></a><a name="zh-cn_topic_0264269293_p519450192418"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="zh-cn_topic_0264269293_p151941505244"><a name="zh-cn_topic_0264269293_p151941505244"></a><a name="zh-cn_topic_0264269293_p151941505244"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="zh-cn_topic_0264269293_p18195500249"><a name="zh-cn_topic_0264269293_p18195500249"></a><a name="zh-cn_topic_0264269293_p18195500249"></a>d3.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="zh-cn_topic_0264269293_p4195405249"><a name="zh-cn_topic_0264269293_p4195405249"></a><a name="zh-cn_topic_0264269293_p4195405249"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="a47a7b71251b348afafb3ad0339723a8e"><a name="a47a7b71251b348afafb3ad0339723a8e"></a><a name="a47a7b71251b348afafb3ad0339723a8e"></a>16 × 1800</p>
</td>
</tr>
<tr id="ree60ff5cdbfc45ad91e0ca96e05b4c44"><td class="cellrowborder" valign="top" headers="mcps1.2.7.1.1 "><p id="zh-cn_topic_0264269293_p03885920286"><a name="zh-cn_topic_0264269293_p03885920286"></a><a name="zh-cn_topic_0264269293_p03885920286"></a>56</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.2 "><p id="zh-cn_topic_0264269293_p338969102819"><a name="zh-cn_topic_0264269293_p338969102819"></a><a name="zh-cn_topic_0264269293_p338969102819"></a>560</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.3 "><p id="a2374fd94f2954702a240f587ddf2b65b"><a name="a2374fd94f2954702a240f587ddf2b65b"></a><a name="a2374fd94f2954702a240f587ddf2b65b"></a>d3.14xlarge.10.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.4 "><p id="zh-cn_topic_0264269293_p17389191280"><a name="zh-cn_topic_0264269293_p17389191280"></a><a name="zh-cn_topic_0264269293_p17389191280"></a>KVM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.7.1.5 "><p id="zh-cn_topic_0264269293_p23899916282"><a name="zh-cn_topic_0264269293_p23899916282"></a><a name="zh-cn_topic_0264269293_p23899916282"></a>28 × 1800</p>
</td>
</tr>
</tbody>
</table>

**表 5**  通用网络增强型（C3ne型）弹性云服务器的规格

<a name="tc8d44c4f60954a209057a339e2b27b1a"></a>
<table><thead align="left"><tr id="r9006c2f2dd2840b89165ee3aa1feb294"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="a325fd143d6404c54b9846c4ef2a9d896"><a name="a325fd143d6404c54b9846c4ef2a9d896"></a><a name="a325fd143d6404c54b9846c4ef2a9d896"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="a00ed8e81b3ae4cbc8461cbd1521e1a57"><a name="a00ed8e81b3ae4cbc8461cbd1521e1a57"></a><a name="a00ed8e81b3ae4cbc8461cbd1521e1a57"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="aecf8959e49aa411aaf803183bd89ebe9"><a name="aecf8959e49aa411aaf803183bd89ebe9"></a><a name="aecf8959e49aa411aaf803183bd89ebe9"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="a031a03ee314e40cb949ca4926bf44746"><a name="a031a03ee314e40cb949ca4926bf44746"></a><a name="a031a03ee314e40cb949ca4926bf44746"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="a7f1ca21727f34d5aadae1622614cec43"><a name="a7f1ca21727f34d5aadae1622614cec43"></a><a name="a7f1ca21727f34d5aadae1622614cec43"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="r60e7e621f53d4a13b1cd30bb09f866c5"><td class="cellrowborder" rowspan="7" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="a829a4e11c10249c9969c0736e0467a3e"><a name="a829a4e11c10249c9969c0736e0467a3e"></a><a name="a829a4e11c10249c9969c0736e0467a3e"></a>C3ne型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="ad1c9da27a1db4e6bbe440ec8a79cda25"><a name="ad1c9da27a1db4e6bbe440ec8a79cda25"></a><a name="ad1c9da27a1db4e6bbe440ec8a79cda25"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="a2c4c2bbffdab49eda688c02a7975140b"><a name="a2c4c2bbffdab49eda688c02a7975140b"></a><a name="a2c4c2bbffdab49eda688c02a7975140b"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="a583c7a64fab046e0b734acb5568d08a8"><a name="a583c7a64fab046e0b734acb5568d08a8"></a><a name="a583c7a64fab046e0b734acb5568d08a8"></a>c3ne.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="a2ad5df19ded644b2be1cfde5eb745dfb"><a name="a2ad5df19ded644b2be1cfde5eb745dfb"></a><a name="a2ad5df19ded644b2be1cfde5eb745dfb"></a>KVM</p>
</td>
</tr>
<tr id="r72387b8dd0294d6888a97f96aee8ebff"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a78af08a6b2974844a6ddcc44ac992941"><a name="a78af08a6b2974844a6ddcc44ac992941"></a><a name="a78af08a6b2974844a6ddcc44ac992941"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="af5df7a28ecf4418094fe53bf0cc93a39"><a name="af5df7a28ecf4418094fe53bf0cc93a39"></a><a name="af5df7a28ecf4418094fe53bf0cc93a39"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a02be9f9244e54a0187f526486273f6e1"><a name="a02be9f9244e54a0187f526486273f6e1"></a><a name="a02be9f9244e54a0187f526486273f6e1"></a>c3ne.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="abe33f993cb244e8688aa227f386da54e"><a name="abe33f993cb244e8688aa227f386da54e"></a><a name="abe33f993cb244e8688aa227f386da54e"></a>KVM</p>
</td>
</tr>
<tr id="r488ce68096ca496b978c5576b10616ab"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="abc20965a002b4aeab68cf93ac8a6aced"><a name="abc20965a002b4aeab68cf93ac8a6aced"></a><a name="abc20965a002b4aeab68cf93ac8a6aced"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a2738ee89c9264393a0c822bbe2cfcb29"><a name="a2738ee89c9264393a0c822bbe2cfcb29"></a><a name="a2738ee89c9264393a0c822bbe2cfcb29"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a35bd346965354b268015ab0106ad6a63"><a name="a35bd346965354b268015ab0106ad6a63"></a><a name="a35bd346965354b268015ab0106ad6a63"></a>c3ne.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a3e46fd43cad044c6853b2603e3e1fa53"><a name="a3e46fd43cad044c6853b2603e3e1fa53"></a><a name="a3e46fd43cad044c6853b2603e3e1fa53"></a>KVM</p>
</td>
</tr>
<tr id="re96b1ddf19b049db97b6823234599619"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a7845794121734f499eff3639f584e09c"><a name="a7845794121734f499eff3639f584e09c"></a><a name="a7845794121734f499eff3639f584e09c"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ac930bfd7806e482598487eda34659fb1"><a name="ac930bfd7806e482598487eda34659fb1"></a><a name="ac930bfd7806e482598487eda34659fb1"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a1f0d2b4f3d8e46899491ad63c7da4e11"><a name="a1f0d2b4f3d8e46899491ad63c7da4e11"></a><a name="a1f0d2b4f3d8e46899491ad63c7da4e11"></a>c3ne.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a24480e5c785d43feb28517d1390ab02b"><a name="a24480e5c785d43feb28517d1390ab02b"></a><a name="a24480e5c785d43feb28517d1390ab02b"></a>KVM</p>
</td>
</tr>
<tr id="r12672ab0b916493d8892caf604f7f362"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a784aa7a4d7ef4098b5f334fd57e57e3c"><a name="a784aa7a4d7ef4098b5f334fd57e57e3c"></a><a name="a784aa7a4d7ef4098b5f334fd57e57e3c"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ad67c142b8e5f4540acefd8f62714d743"><a name="ad67c142b8e5f4540acefd8f62714d743"></a><a name="ad67c142b8e5f4540acefd8f62714d743"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a57bb37a37f1847aa8b2ff03f877f5ae6"><a name="a57bb37a37f1847aa8b2ff03f877f5ae6"></a><a name="a57bb37a37f1847aa8b2ff03f877f5ae6"></a>c3ne.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a58d269e7bcad4824abd26c80adaa03d6"><a name="a58d269e7bcad4824abd26c80adaa03d6"></a><a name="a58d269e7bcad4824abd26c80adaa03d6"></a>KVM</p>
</td>
</tr>
<tr id="r84582abaadac40bea4b783438623b867"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ae79704ac6cb94d9e9667a09fbb21f761"><a name="ae79704ac6cb94d9e9667a09fbb21f761"></a><a name="ae79704ac6cb94d9e9667a09fbb21f761"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a542b66b43ce2400cb3f96a15f46758bb"><a name="a542b66b43ce2400cb3f96a15f46758bb"></a><a name="a542b66b43ce2400cb3f96a15f46758bb"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="aaaaf2b30cd9847beac85aa58a7fa1283"><a name="aaaaf2b30cd9847beac85aa58a7fa1283"></a><a name="aaaaf2b30cd9847beac85aa58a7fa1283"></a>c3ne.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a6f9be9e5972f4e6c8c8c1b87ade8fac0"><a name="a6f9be9e5972f4e6c8c8c1b87ade8fac0"></a><a name="a6f9be9e5972f4e6c8c8c1b87ade8fac0"></a>KVM</p>
</td>
</tr>
<tr id="r6ff732ed01bb4e8fb978be78d82ef264"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a1b6549778de5417da40881f0f13bfabb"><a name="a1b6549778de5417da40881f0f13bfabb"></a><a name="a1b6549778de5417da40881f0f13bfabb"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ae24df54b4779490997ca9165641fc2d4"><a name="ae24df54b4779490997ca9165641fc2d4"></a><a name="ae24df54b4779490997ca9165641fc2d4"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="ad09baac3e64a4ee98e903b70ed2fb49f"><a name="ad09baac3e64a4ee98e903b70ed2fb49f"></a><a name="ad09baac3e64a4ee98e903b70ed2fb49f"></a>c3ne.15xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a3fdccda101f74c1a80dfafae2ff53561"><a name="a3fdccda101f74c1a80dfafae2ff53561"></a><a name="a3fdccda101f74c1a80dfafae2ff53561"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 6**  高性能计算型（Hc2）弹性云服务器的规格

<a name="tec6d0b922dc64372a168a9e75844d9a7"></a>
<table><thead align="left"><tr id="r1a24c79f77e34422bea40002bf93b273"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="aa6b3c34505e242928e772667f8ec056b"><a name="aa6b3c34505e242928e772667f8ec056b"></a><a name="aa6b3c34505e242928e772667f8ec056b"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="aef541c1d0afc41d39158ac71fee4d311"><a name="aef541c1d0afc41d39158ac71fee4d311"></a><a name="aef541c1d0afc41d39158ac71fee4d311"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="a4ecf2f5147da44f2941d93c326627da0"><a name="a4ecf2f5147da44f2941d93c326627da0"></a><a name="a4ecf2f5147da44f2941d93c326627da0"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="a3cfe2f33c4d643ba89c81a7a7a0074c9"><a name="a3cfe2f33c4d643ba89c81a7a7a0074c9"></a><a name="a3cfe2f33c4d643ba89c81a7a7a0074c9"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="aff7c4bd6ee8b43c89ef4e86daa9241d6"><a name="aff7c4bd6ee8b43c89ef4e86daa9241d6"></a><a name="aff7c4bd6ee8b43c89ef4e86daa9241d6"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="r5f244d32e67b4c51879b3d0dced3af7f"><td class="cellrowborder" rowspan="3" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="ac3557ac773124a3d9aadf8f27423da02"><a name="ac3557ac773124a3d9aadf8f27423da02"></a><a name="ac3557ac773124a3d9aadf8f27423da02"></a>Hc2型</p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="a355712183d5a4bbf874b1b4b9e60dabd"><a name="a355712183d5a4bbf874b1b4b9e60dabd"></a><a name="a355712183d5a4bbf874b1b4b9e60dabd"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="a03657ffaca534cca84cf9e7536c8c481"><a name="a03657ffaca534cca84cf9e7536c8c481"></a><a name="a03657ffaca534cca84cf9e7536c8c481"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="a81916b9730264266968774c5a0a79add"><a name="a81916b9730264266968774c5a0a79add"></a><a name="a81916b9730264266968774c5a0a79add"></a>hc2.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="a3e6f402283d24fc38b1e543136b5712b"><a name="a3e6f402283d24fc38b1e543136b5712b"></a><a name="a3e6f402283d24fc38b1e543136b5712b"></a>KVM</p>
</td>
</tr>
<tr id="r2789e4b3ccf04d528ed4981a42f09a73"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a54c2f6ee304848fbac9886dd41033533"><a name="a54c2f6ee304848fbac9886dd41033533"></a><a name="a54c2f6ee304848fbac9886dd41033533"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a83bb638898554ce6a6cc062bdf6765b4"><a name="a83bb638898554ce6a6cc062bdf6765b4"></a><a name="a83bb638898554ce6a6cc062bdf6765b4"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="af632c867955f491496779d0e001a5cc3"><a name="af632c867955f491496779d0e001a5cc3"></a><a name="af632c867955f491496779d0e001a5cc3"></a>hc2.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a6f1a8e79aa4641ce99d87b34f55c6e08"><a name="a6f1a8e79aa4641ce99d87b34f55c6e08"></a><a name="a6f1a8e79aa4641ce99d87b34f55c6e08"></a>KVM</p>
</td>
</tr>
<tr id="r7cadc90da5b44ba0b65940e76151781d"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a3abf243525034ed390737e23dea7acdf"><a name="a3abf243525034ed390737e23dea7acdf"></a><a name="a3abf243525034ed390737e23dea7acdf"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a17c577ce394a4cd2a09c5b23b4227b0e"><a name="a17c577ce394a4cd2a09c5b23b4227b0e"></a><a name="a17c577ce394a4cd2a09c5b23b4227b0e"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a26129a1f9cc543778f37b071bc65beae"><a name="a26129a1f9cc543778f37b071bc65beae"></a><a name="a26129a1f9cc543778f37b071bc65beae"></a>hc2.8xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a234d328f568d44c88a383ddb06b8257f"><a name="a234d328f568d44c88a383ddb06b8257f"></a><a name="a234d328f568d44c88a383ddb06b8257f"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 7**  内存优化型弹性云服务器的规格

<a name="t2edbe9ee6ac640abad3fff46a54ff1ad"></a>
<table><thead align="left"><tr id="r94b20b655ed4411e9e10712e9b68ded7"><th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.1"><p id="ac5c5301a45fc4ff28d3bbc31d629b7e6"><a name="ac5c5301a45fc4ff28d3bbc31d629b7e6"></a><a name="ac5c5301a45fc4ff28d3bbc31d629b7e6"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.232323232323235%" id="mcps1.2.6.1.2"><p id="a78dff19f661b4722b8a9f0264c16f8d8"><a name="a78dff19f661b4722b8a9f0264c16f8d8"></a><a name="a78dff19f661b4722b8a9f0264c16f8d8"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="19.191919191919194%" id="mcps1.2.6.1.3"><p id="a0458f48f06ef4715a093d7530714a0f1"><a name="a0458f48f06ef4715a093d7530714a0f1"></a><a name="a0458f48f06ef4715a093d7530714a0f1"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.6.1.4"><p id="a903bfc682b24455da4ff07f4bb7a8e97"><a name="a903bfc682b24455da4ff07f4bb7a8e97"></a><a name="a903bfc682b24455da4ff07f4bb7a8e97"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.121212121212121%" id="mcps1.2.6.1.5"><p id="a39eb89d0b1ad46ac8c407bcbdddf78ed"><a name="a39eb89d0b1ad46ac8c407bcbdddf78ed"></a><a name="a39eb89d0b1ad46ac8c407bcbdddf78ed"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="r8bcadfa4e5a649cbb7d2cf74fcc8001b"><td class="cellrowborder" rowspan="6" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="aa71c9aa235f543a88b93af1274f89e46"><a name="aa71c9aa235f543a88b93af1274f89e46"></a><a name="aa71c9aa235f543a88b93af1274f89e46"></a>M3型</p>
<p id="a143645326c2a41f9bc7336fed34f3fe7"><a name="a143645326c2a41f9bc7336fed34f3fe7"></a><a name="a143645326c2a41f9bc7336fed34f3fe7"></a></p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="a157a04572afd48f7b1e43829652f7800"><a name="a157a04572afd48f7b1e43829652f7800"></a><a name="a157a04572afd48f7b1e43829652f7800"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="a3b8f6228fcf94981b170b843de656d58"><a name="a3b8f6228fcf94981b170b843de656d58"></a><a name="a3b8f6228fcf94981b170b843de656d58"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="a5d9820a75e984a26a4777e87f7883b67"><a name="a5d9820a75e984a26a4777e87f7883b67"></a><a name="a5d9820a75e984a26a4777e87f7883b67"></a>m3.large.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="a897ae5a9b975405d98ef3a41d546631a"><a name="a897ae5a9b975405d98ef3a41d546631a"></a><a name="a897ae5a9b975405d98ef3a41d546631a"></a>KVM</p>
</td>
</tr>
<tr id="r659c265e9a824cef80ad6d181fb160af"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a146e1d99c1914123bd6439e320539a2a"><a name="a146e1d99c1914123bd6439e320539a2a"></a><a name="a146e1d99c1914123bd6439e320539a2a"></a>4</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a77007bb1fc5a48f6aeb001ffc89fbd52"><a name="a77007bb1fc5a48f6aeb001ffc89fbd52"></a><a name="a77007bb1fc5a48f6aeb001ffc89fbd52"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a265e78c135f74a2db18a8d01ead75d9f"><a name="a265e78c135f74a2db18a8d01ead75d9f"></a><a name="a265e78c135f74a2db18a8d01ead75d9f"></a>m3.xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a8ba5b6eba81a470b9a61f76a8ca78195"><a name="a8ba5b6eba81a470b9a61f76a8ca78195"></a><a name="a8ba5b6eba81a470b9a61f76a8ca78195"></a>KVM</p>
</td>
</tr>
<tr id="re3f8f8948084464884d5985273599266"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a4e45d765b5b3436cb0ec294504937ef0"><a name="a4e45d765b5b3436cb0ec294504937ef0"></a><a name="a4e45d765b5b3436cb0ec294504937ef0"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a652a9d437d3746e5acc0e4f755b7cacb"><a name="a652a9d437d3746e5acc0e4f755b7cacb"></a><a name="a652a9d437d3746e5acc0e4f755b7cacb"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="aff58cbe006544a4e9fd0c4768f9ec9cd"><a name="aff58cbe006544a4e9fd0c4768f9ec9cd"></a><a name="aff58cbe006544a4e9fd0c4768f9ec9cd"></a>m3.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a6aa34becc4d34423bbc69e3e5baefa3c"><a name="a6aa34becc4d34423bbc69e3e5baefa3c"></a><a name="a6aa34becc4d34423bbc69e3e5baefa3c"></a>KVM</p>
</td>
</tr>
<tr id="rd81f01229c074ab3b37e22844be037de"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a1b56c5643ec4419dacf295e1f48ab83f"><a name="a1b56c5643ec4419dacf295e1f48ab83f"></a><a name="a1b56c5643ec4419dacf295e1f48ab83f"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ae23a9ea626f84c5eb4b5963743ec7891"><a name="ae23a9ea626f84c5eb4b5963743ec7891"></a><a name="ae23a9ea626f84c5eb4b5963743ec7891"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a3492e97e424345debc12c8ba9563d273"><a name="a3492e97e424345debc12c8ba9563d273"></a><a name="a3492e97e424345debc12c8ba9563d273"></a>m3.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a47b81d3f632b420c980bd1cdc6b0b12d"><a name="a47b81d3f632b420c980bd1cdc6b0b12d"></a><a name="a47b81d3f632b420c980bd1cdc6b0b12d"></a>KVM</p>
</td>
</tr>
<tr id="r8029af34749d48c4b06197369983b5a2"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ab9de8aaf84db42bc9f7f721f0bae0743"><a name="ab9de8aaf84db42bc9f7f721f0bae0743"></a><a name="ab9de8aaf84db42bc9f7f721f0bae0743"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a7d2c4cbae96f49989b7534dfd0eb8f73"><a name="a7d2c4cbae96f49989b7534dfd0eb8f73"></a><a name="a7d2c4cbae96f49989b7534dfd0eb8f73"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a7f30e519b46143dfb18853dbaf24c94f"><a name="a7f30e519b46143dfb18853dbaf24c94f"></a><a name="a7f30e519b46143dfb18853dbaf24c94f"></a>m3.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="ab7c7941446fe4b9aaad0a30b76b8d757"><a name="ab7c7941446fe4b9aaad0a30b76b8d757"></a><a name="ab7c7941446fe4b9aaad0a30b76b8d757"></a>KVM</p>
</td>
</tr>
<tr id="r9347fff55537415a801eb71aac5ce92c"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a118bfa57d7d749ca874f9dedac083139"><a name="a118bfa57d7d749ca874f9dedac083139"></a><a name="a118bfa57d7d749ca874f9dedac083139"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a7a8e216e455d405092b5342047cd0942"><a name="a7a8e216e455d405092b5342047cd0942"></a><a name="a7a8e216e455d405092b5342047cd0942"></a>512</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a3247cbfe3357428b88ecd2c5acabfaa4"><a name="a3247cbfe3357428b88ecd2c5acabfaa4"></a><a name="a3247cbfe3357428b88ecd2c5acabfaa4"></a>m3.15xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="aef4246e3c8914a1fb39fd15738c1c51f"><a name="aef4246e3c8914a1fb39fd15738c1c51f"></a><a name="aef4246e3c8914a1fb39fd15738c1c51f"></a>KVM</p>
</td>
</tr>
<tr id="r36cbba59896241ebb8131fb3a65a921b"><td class="cellrowborder" rowspan="6" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p144284237124"><a name="zh-cn_topic_0264269293_p144284237124"></a><a name="zh-cn_topic_0264269293_p144284237124"></a>M6型</p>
<p id="ace3277765d2342fc85c366fc81303078"><a name="ace3277765d2342fc85c366fc81303078"></a><a name="ace3277765d2342fc85c366fc81303078"></a></p>
<p id="zh-cn_topic_0264269293_p181715231209"><a name="zh-cn_topic_0264269293_p181715231209"></a><a name="zh-cn_topic_0264269293_p181715231209"></a></p>
<p id="zh-cn_topic_0264269293_p050412258201"><a name="zh-cn_topic_0264269293_p050412258201"></a><a name="zh-cn_topic_0264269293_p050412258201"></a></p>
<p id="a42de62b079da4d8da8f74869c874d360"><a name="a42de62b079da4d8da8f74869c874d360"></a><a name="a42de62b079da4d8da8f74869c874d360"></a></p>
<p id="ad127ed2c187746a3ab07095a6b6c39ef"><a name="ad127ed2c187746a3ab07095a6b6c39ef"></a><a name="ad127ed2c187746a3ab07095a6b6c39ef"></a></p>
</td>
<td class="cellrowborder" valign="top" width="23.232323232323235%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p542852314123"><a name="zh-cn_topic_0264269293_p542852314123"></a><a name="zh-cn_topic_0264269293_p542852314123"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="19.191919191919194%" headers="mcps1.2.6.1.3 "><p id="aa667d73598644b44ac58b0e31fc74207"><a name="aa667d73598644b44ac58b0e31fc74207"></a><a name="aa667d73598644b44ac58b0e31fc74207"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.6.1.4 "><p id="aafd4e7c731eb4bb792d214fe2ff5a779"><a name="aafd4e7c731eb4bb792d214fe2ff5a779"></a><a name="aafd4e7c731eb4bb792d214fe2ff5a779"></a>m6.xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="12.121212121212121%" headers="mcps1.2.6.1.5 "><p id="ac5c9fb53c8ac4b6a9e1453b657f40b1f"><a name="ac5c9fb53c8ac4b6a9e1453b657f40b1f"></a><a name="ac5c9fb53c8ac4b6a9e1453b657f40b1f"></a>KVM</p>
</td>
</tr>
<tr id="rebe7744fe5ad44b9ad7c9a190234dbbc"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a1dd8884735004ae99756fb0772fa9052"><a name="a1dd8884735004ae99756fb0772fa9052"></a><a name="a1dd8884735004ae99756fb0772fa9052"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a9241d329113b4b40a7bf3e4e10d5c11e"><a name="a9241d329113b4b40a7bf3e4e10d5c11e"></a><a name="a9241d329113b4b40a7bf3e4e10d5c11e"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="adc6f3de2ffc946879a21be8d857f4c13"><a name="adc6f3de2ffc946879a21be8d857f4c13"></a><a name="adc6f3de2ffc946879a21be8d857f4c13"></a>m6.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="ada536f58eb2c4b7d94d1833e1cb3397a"><a name="ada536f58eb2c4b7d94d1833e1cb3397a"></a><a name="ada536f58eb2c4b7d94d1833e1cb3397a"></a>KVM</p>
</td>
</tr>
<tr id="r0ae9715ebc20471c8c967a2ccd28bc44"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p617122312019"><a name="zh-cn_topic_0264269293_p617122312019"></a><a name="zh-cn_topic_0264269293_p617122312019"></a>12</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p717102315207"><a name="zh-cn_topic_0264269293_p717102315207"></a><a name="zh-cn_topic_0264269293_p717102315207"></a>96</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="acefc0bf5cbf6489fab51792b0a9421ec"><a name="acefc0bf5cbf6489fab51792b0a9421ec"></a><a name="acefc0bf5cbf6489fab51792b0a9421ec"></a>m6.3xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a3194fb7388c545ff96b780c660461ad7"><a name="a3194fb7388c545ff96b780c660461ad7"></a><a name="a3194fb7388c545ff96b780c660461ad7"></a>KVM</p>
</td>
</tr>
<tr id="r569d701667074648bfc651ec859ce638"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ac7859a7b79424c0f8f5624b65701c4d4"><a name="ac7859a7b79424c0f8f5624b65701c4d4"></a><a name="ac7859a7b79424c0f8f5624b65701c4d4"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p550412254203"><a name="zh-cn_topic_0264269293_p550412254203"></a><a name="zh-cn_topic_0264269293_p550412254203"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="add85f281df894e1ca7951bb1922e7ece"><a name="add85f281df894e1ca7951bb1922e7ece"></a><a name="add85f281df894e1ca7951bb1922e7ece"></a>m6.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264269293_p85040255202"><a name="zh-cn_topic_0264269293_p85040255202"></a><a name="zh-cn_topic_0264269293_p85040255202"></a>KVM</p>
</td>
</tr>
<tr id="r3d42754874e84865b8f412ecca0494f6"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a5245282185c54ef6bbdcfd285ee43151"><a name="a5245282185c54ef6bbdcfd285ee43151"></a><a name="a5245282185c54ef6bbdcfd285ee43151"></a>24</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="aec94d1b2ec374a47b4145a7e1e0919f7"><a name="aec94d1b2ec374a47b4145a7e1e0919f7"></a><a name="aec94d1b2ec374a47b4145a7e1e0919f7"></a>192</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a1c7ca4c37ba14f648e58c6eebb9b45d3"><a name="a1c7ca4c37ba14f648e58c6eebb9b45d3"></a><a name="a1c7ca4c37ba14f648e58c6eebb9b45d3"></a>m6.6xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a2283f76482474175aae679a465f0366f"><a name="a2283f76482474175aae679a465f0366f"></a><a name="a2283f76482474175aae679a465f0366f"></a>KVM</p>
</td>
</tr>
<tr id="r548e93308dc145bb82033f936eb1c2f1"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="abef2a43538e244629c3e2acd4112fdf9"><a name="abef2a43538e244629c3e2acd4112fdf9"></a><a name="abef2a43538e244629c3e2acd4112fdf9"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p487016296200"><a name="zh-cn_topic_0264269293_p487016296200"></a><a name="zh-cn_topic_0264269293_p487016296200"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="af3e7b2b970b3437580efa025dd055558"><a name="af3e7b2b970b3437580efa025dd055558"></a><a name="af3e7b2b970b3437580efa025dd055558"></a>m6.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a87c601fef77e4eb186baa46b642918dd"><a name="a87c601fef77e4eb186baa46b642918dd"></a><a name="a87c601fef77e4eb186baa46b642918dd"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 8**  鲲鹏通用计算增强型（KC1型）弹性云服务器的规格

<a name="t9b9a18b89b1c4855ac8bc2fc738c047f"></a>
<table><thead align="left"><tr id="ra620308e996a436188f3154a95993579"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="ad14085268720454d971e4bf60c91c2a5"><a name="ad14085268720454d971e4bf60c91c2a5"></a><a name="ad14085268720454d971e4bf60c91c2a5"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="a49bf265e94b84fd58c74f4574387c684"><a name="a49bf265e94b84fd58c74f4574387c684"></a><a name="a49bf265e94b84fd58c74f4574387c684"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="a69da48b0d8ab499a9feab09b76597f02"><a name="a69da48b0d8ab499a9feab09b76597f02"></a><a name="a69da48b0d8ab499a9feab09b76597f02"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="a0630948cb4b543faa6bc296af859936e"><a name="a0630948cb4b543faa6bc296af859936e"></a><a name="a0630948cb4b543faa6bc296af859936e"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="ad7f146ffe8b04d5bb0a2ad6d326dafe3"><a name="ad7f146ffe8b04d5bb0a2ad6d326dafe3"></a><a name="ad7f146ffe8b04d5bb0a2ad6d326dafe3"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="r63eefdc459f04371ab19c46f0094b6f4"><td class="cellrowborder" rowspan="8" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="ae5abe957ef224bf6ad17f1586fb7698f"><a name="ae5abe957ef224bf6ad17f1586fb7698f"></a><a name="ae5abe957ef224bf6ad17f1586fb7698f"></a>KC1型</p>
<p id="a2d22d1283eaa49d5a8516d1218c6de59"><a name="a2d22d1283eaa49d5a8516d1218c6de59"></a><a name="a2d22d1283eaa49d5a8516d1218c6de59"></a></p>
<p id="ae0ce67ee85f741eca68c73afdb05efe8"><a name="ae0ce67ee85f741eca68c73afdb05efe8"></a><a name="ae0ce67ee85f741eca68c73afdb05efe8"></a></p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="acd96880616884de294b6e07cb123005e"><a name="acd96880616884de294b6e07cb123005e"></a><a name="acd96880616884de294b6e07cb123005e"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="a39abc69f4b1b46b299ab88d7ebc21324"><a name="a39abc69f4b1b46b299ab88d7ebc21324"></a><a name="a39abc69f4b1b46b299ab88d7ebc21324"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="abba40970e8d4491a9f4d93fba0b72428"><a name="abba40970e8d4491a9f4d93fba0b72428"></a><a name="abba40970e8d4491a9f4d93fba0b72428"></a>kc1.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="aa49f11f56b334af9bfb312ef44d93604"><a name="aa49f11f56b334af9bfb312ef44d93604"></a><a name="aa49f11f56b334af9bfb312ef44d93604"></a>KVM</p>
</td>
</tr>
<tr id="r9dd9729a18f448339b6b5b67e97697f8"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a6bfc1876ea3e4ed19200aa4c6d5bfb8f"><a name="a6bfc1876ea3e4ed19200aa4c6d5bfb8f"></a><a name="a6bfc1876ea3e4ed19200aa4c6d5bfb8f"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a7eec7f39079248b9ae3ea858cb2f6868"><a name="a7eec7f39079248b9ae3ea858cb2f6868"></a><a name="a7eec7f39079248b9ae3ea858cb2f6868"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a1ccb26bb6f744cd2a03a7f2d67ab13cb"><a name="a1ccb26bb6f744cd2a03a7f2d67ab13cb"></a><a name="a1ccb26bb6f744cd2a03a7f2d67ab13cb"></a>kc1.2xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a1a071ad92def441ebd79e95fd94dc1e7"><a name="a1a071ad92def441ebd79e95fd94dc1e7"></a><a name="a1a071ad92def441ebd79e95fd94dc1e7"></a>KVM</p>
</td>
</tr>
<tr id="r90ba36edc05a46dbbd4e52a72a90920e"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a0d4cea0988a84e0cbd989046096e8223"><a name="a0d4cea0988a84e0cbd989046096e8223"></a><a name="a0d4cea0988a84e0cbd989046096e8223"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="adecd647681c94ca29e3b99a5cdcaf110"><a name="adecd647681c94ca29e3b99a5cdcaf110"></a><a name="adecd647681c94ca29e3b99a5cdcaf110"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a6f8c98792fe64fa2bf9a11629798aa2a"><a name="a6f8c98792fe64fa2bf9a11629798aa2a"></a><a name="a6f8c98792fe64fa2bf9a11629798aa2a"></a>kc1.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a6d4790dabe4648b2996d89c9c1c97fe1"><a name="a6d4790dabe4648b2996d89c9c1c97fe1"></a><a name="a6d4790dabe4648b2996d89c9c1c97fe1"></a>KVM</p>
</td>
</tr>
<tr id="r716f7fe09e75435797ff50f56f2eaad5"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a6d4defe671b942079277c59739ef0b93"><a name="a6d4defe671b942079277c59739ef0b93"></a><a name="a6d4defe671b942079277c59739ef0b93"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="aabcbf0b94a6e48278fde80e7d1b1d259"><a name="aabcbf0b94a6e48278fde80e7d1b1d259"></a><a name="aabcbf0b94a6e48278fde80e7d1b1d259"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a772863f4c1824122a77c6b81aefaf808"><a name="a772863f4c1824122a77c6b81aefaf808"></a><a name="a772863f4c1824122a77c6b81aefaf808"></a>kc1.4xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="ac4c832b974094226b84c4411431e6dbd"><a name="ac4c832b974094226b84c4411431e6dbd"></a><a name="ac4c832b974094226b84c4411431e6dbd"></a>KVM</p>
</td>
</tr>
<tr id="rb71e77c98337409ab85880f0b0273ee7"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="af1630938c51a4bd3b4e805c3d88ded4d"><a name="af1630938c51a4bd3b4e805c3d88ded4d"></a><a name="af1630938c51a4bd3b4e805c3d88ded4d"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a339986fdb6644ac2a4c7609f477418cd"><a name="a339986fdb6644ac2a4c7609f477418cd"></a><a name="a339986fdb6644ac2a4c7609f477418cd"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a71a9dd1c02ec4efead2dd47283b3acfd"><a name="a71a9dd1c02ec4efead2dd47283b3acfd"></a><a name="a71a9dd1c02ec4efead2dd47283b3acfd"></a>kc1.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a2c4422a02a3a47b9a794928b3e9d9191"><a name="a2c4422a02a3a47b9a794928b3e9d9191"></a><a name="a2c4422a02a3a47b9a794928b3e9d9191"></a>KVM</p>
</td>
</tr>
<tr id="rcc2d7c763cb34d23adcaf74b2faa478a"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a2df2fde2efe44306b626348bb78a2254"><a name="a2df2fde2efe44306b626348bb78a2254"></a><a name="a2df2fde2efe44306b626348bb78a2254"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ac1cad9d94f1141feb671bbb56a6dfdec"><a name="ac1cad9d94f1141feb671bbb56a6dfdec"></a><a name="ac1cad9d94f1141feb671bbb56a6dfdec"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a692ef763ef9042dabbfea5a4bc9e7536"><a name="a692ef763ef9042dabbfea5a4bc9e7536"></a><a name="a692ef763ef9042dabbfea5a4bc9e7536"></a>kc1.8xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a0b5364f583bd4b5d998a79501795b0d2"><a name="a0b5364f583bd4b5d998a79501795b0d2"></a><a name="a0b5364f583bd4b5d998a79501795b0d2"></a>KVM</p>
</td>
</tr>
<tr id="r0653a95391294012a56ec03436a20cd2"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a0dcf80490e5a43ab8091c29116f49e4d"><a name="a0dcf80490e5a43ab8091c29116f49e4d"></a><a name="a0dcf80490e5a43ab8091c29116f49e4d"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a594d8779d1b44a938fc76048536b2fa7"><a name="a594d8779d1b44a938fc76048536b2fa7"></a><a name="a594d8779d1b44a938fc76048536b2fa7"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="ab9353135dbad4dc6bf69c8be1659adea"><a name="ab9353135dbad4dc6bf69c8be1659adea"></a><a name="ab9353135dbad4dc6bf69c8be1659adea"></a>kc1.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a1f91d1f35b01484d8ae61a5f9d6c38ea"><a name="a1f91d1f35b01484d8ae61a5f9d6c38ea"></a><a name="a1f91d1f35b01484d8ae61a5f9d6c38ea"></a>KVM</p>
</td>
</tr>
<tr id="r2ee16ec830e74b2a81cf43b45e7cd5de"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a62a138b5794b4f368b4f2f6831b13640"><a name="a62a138b5794b4f368b4f2f6831b13640"></a><a name="a62a138b5794b4f368b4f2f6831b13640"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a737db2ab345b4282ac05b55d1259573e"><a name="a737db2ab345b4282ac05b55d1259573e"></a><a name="a737db2ab345b4282ac05b55d1259573e"></a>120</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="afc3040bd67664081a04fa037c974e4fd"><a name="afc3040bd67664081a04fa037c974e4fd"></a><a name="afc3040bd67664081a04fa037c974e4fd"></a>kc1.15xlarge.2.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a2c7480540de74103aab02e0065b74c36"><a name="a2c7480540de74103aab02e0065b74c36"></a><a name="a2c7480540de74103aab02e0065b74c36"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 9**  鲲鹏内存优化型（KM1型）弹性云服务器的规格

<a name="t8aafe22d513d47f581d69a02187bdfcd"></a>
<table><thead align="left"><tr id="r7b7176ab838640089f7e64fae86cdcb5"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="ae4ef7e52cb124bc88ea22b21b6eb9b41"><a name="ae4ef7e52cb124bc88ea22b21b6eb9b41"></a><a name="ae4ef7e52cb124bc88ea22b21b6eb9b41"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="abf39f04bd9f64697bb2763cfee45228a"><a name="abf39f04bd9f64697bb2763cfee45228a"></a><a name="abf39f04bd9f64697bb2763cfee45228a"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="a2d53af3625c64a27bc73d3ea9be28717"><a name="a2d53af3625c64a27bc73d3ea9be28717"></a><a name="a2d53af3625c64a27bc73d3ea9be28717"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="ae50e4379525a460299fba815c744ff27"><a name="ae50e4379525a460299fba815c744ff27"></a><a name="ae50e4379525a460299fba815c744ff27"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="aa683245f405f4f108113c566dc180868"><a name="aa683245f405f4f108113c566dc180868"></a><a name="aa683245f405f4f108113c566dc180868"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="r6951d935117f40358b796cbd713442dc"><td class="cellrowborder" rowspan="5" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="a97628c725d184ffca545971a780e9fad"><a name="a97628c725d184ffca545971a780e9fad"></a><a name="a97628c725d184ffca545971a780e9fad"></a>KM1型</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="a918e8fb2b8ee4ba0a807abcd6d8d9290"><a name="a918e8fb2b8ee4ba0a807abcd6d8d9290"></a><a name="a918e8fb2b8ee4ba0a807abcd6d8d9290"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="ae5dd5ab0dfe041da97febc116b8e2166"><a name="ae5dd5ab0dfe041da97febc116b8e2166"></a><a name="ae5dd5ab0dfe041da97febc116b8e2166"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="a22f147f2539543c58b7e428c83368c43"><a name="a22f147f2539543c58b7e428c83368c43"></a><a name="a22f147f2539543c58b7e428c83368c43"></a>km1.xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="a8199ed903eee45949c4c2aa0011817df"><a name="a8199ed903eee45949c4c2aa0011817df"></a><a name="a8199ed903eee45949c4c2aa0011817df"></a>KVM</p>
</td>
</tr>
<tr id="r427606214b844555890f6621c4b5f072"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a67190d2d5f5e4030b0f33a2d7d96b939"><a name="a67190d2d5f5e4030b0f33a2d7d96b939"></a><a name="a67190d2d5f5e4030b0f33a2d7d96b939"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a06a9f07f1d2f4c43a1925a1c91c686af"><a name="a06a9f07f1d2f4c43a1925a1c91c686af"></a><a name="a06a9f07f1d2f4c43a1925a1c91c686af"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a2c95ca135ade44c8b766355270bbce41"><a name="a2c95ca135ade44c8b766355270bbce41"></a><a name="a2c95ca135ade44c8b766355270bbce41"></a>km1.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="aae053a3fff3744639e46d7050fbdb2f3"><a name="aae053a3fff3744639e46d7050fbdb2f3"></a><a name="aae053a3fff3744639e46d7050fbdb2f3"></a>KVM</p>
</td>
</tr>
<tr id="rce1e9f48db404b81a74c2579e30f52c0"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ad8fef5211306450eb6456438c38926e1"><a name="ad8fef5211306450eb6456438c38926e1"></a><a name="ad8fef5211306450eb6456438c38926e1"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a9b2ffacb8388428f9ed4b72c99cb913c"><a name="a9b2ffacb8388428f9ed4b72c99cb913c"></a><a name="a9b2ffacb8388428f9ed4b72c99cb913c"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a97b967fc72db43daa5a6e0a06ccc148a"><a name="a97b967fc72db43daa5a6e0a06ccc148a"></a><a name="a97b967fc72db43daa5a6e0a06ccc148a"></a>km1.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a1ff52060e48242c8bb843345408edf10"><a name="a1ff52060e48242c8bb843345408edf10"></a><a name="a1ff52060e48242c8bb843345408edf10"></a>KVM</p>
</td>
</tr>
<tr id="r600c837e9f124f5297058af07cf3db6b"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a6ccaf256413647b7b519735618b9e078"><a name="a6ccaf256413647b7b519735618b9e078"></a><a name="a6ccaf256413647b7b519735618b9e078"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a962f4b3534b84a7ea8321f584a89cc86"><a name="a962f4b3534b84a7ea8321f584a89cc86"></a><a name="a962f4b3534b84a7ea8321f584a89cc86"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a5cb3d59364cd4c0fb2b7b299de813d7e"><a name="a5cb3d59364cd4c0fb2b7b299de813d7e"></a><a name="a5cb3d59364cd4c0fb2b7b299de813d7e"></a>km1.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="ada820cb43b4449c2b7e1ca54462f4eb3"><a name="ada820cb43b4449c2b7e1ca54462f4eb3"></a><a name="ada820cb43b4449c2b7e1ca54462f4eb3"></a>KVM</p>
</td>
</tr>
<tr id="re6483387a9974f28b8f887be2945f32c"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a9035058452014b2b9e536b02a9496a4e"><a name="a9035058452014b2b9e536b02a9496a4e"></a><a name="a9035058452014b2b9e536b02a9496a4e"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a95c97ef11dd342628e4dbcc8c5811aa0"><a name="a95c97ef11dd342628e4dbcc8c5811aa0"></a><a name="a95c97ef11dd342628e4dbcc8c5811aa0"></a>480</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a4b6f6174686a4b00b33077c86b1bbc8c"><a name="a4b6f6174686a4b00b33077c86b1bbc8c"></a><a name="a4b6f6174686a4b00b33077c86b1bbc8c"></a>km1.15xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="adefde0c979a14ba5abcd5bbd7d4d365b"><a name="adefde0c979a14ba5abcd5bbd7d4d365b"></a><a name="adefde0c979a14ba5abcd5bbd7d4d365b"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 10**  鲲鹏超高I/O型（KI1型）弹性云服务器的规格

<a name="t5447597b037542d59b5e62d8de32e3c7"></a>
<table><thead align="left"><tr id="rf807f709d6544bdea57c87aa44d785d2"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="aab97fd0567f04146b5d4175ceef3b03a"><a name="aab97fd0567f04146b5d4175ceef3b03a"></a><a name="aab97fd0567f04146b5d4175ceef3b03a"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0264269293_p262111911290"><a name="zh-cn_topic_0264269293_p262111911290"></a><a name="zh-cn_topic_0264269293_p262111911290"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="adbd572a5b4ec4859bbb4d62f0dde2f05"><a name="adbd572a5b4ec4859bbb4d62f0dde2f05"></a><a name="adbd572a5b4ec4859bbb4d62f0dde2f05"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0264269293_p76341910292"><a name="zh-cn_topic_0264269293_p76341910292"></a><a name="zh-cn_topic_0264269293_p76341910292"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0264269293_p163141911292"><a name="zh-cn_topic_0264269293_p163141911292"></a><a name="zh-cn_topic_0264269293_p163141911292"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="r30e6f2f14e73429b97d46c8b155a32bd"><td class="cellrowborder" rowspan="5" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p863719122920"><a name="zh-cn_topic_0264269293_p863719122920"></a><a name="zh-cn_topic_0264269293_p863719122920"></a>KI1型</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p186361910291"><a name="zh-cn_topic_0264269293_p186361910291"></a><a name="zh-cn_topic_0264269293_p186361910291"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="a2eb116c6419d497fbaf338e29afae8d9"><a name="a2eb116c6419d497fbaf338e29afae8d9"></a><a name="a2eb116c6419d497fbaf338e29afae8d9"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="a6cbd201f357447e1adc13c839df630b5"><a name="a6cbd201f357447e1adc13c839df630b5"></a><a name="a6cbd201f357447e1adc13c839df630b5"></a>ki1.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264269293_p96361962912"><a name="zh-cn_topic_0264269293_p96361962912"></a><a name="zh-cn_topic_0264269293_p96361962912"></a>KVM</p>
</td>
</tr>
<tr id="rae750d0cc1fc43f2b68662ab8a7fac9d"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p13645195299"><a name="zh-cn_topic_0264269293_p13645195299"></a><a name="zh-cn_topic_0264269293_p13645195299"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a63a0bc0f54624199a16de5f4d65b9cec"><a name="a63a0bc0f54624199a16de5f4d65b9cec"></a><a name="a63a0bc0f54624199a16de5f4d65b9cec"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264269293_p136416192296"><a name="zh-cn_topic_0264269293_p136416192296"></a><a name="zh-cn_topic_0264269293_p136416192296"></a>ki1.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264269293_p116416194299"><a name="zh-cn_topic_0264269293_p116416194299"></a><a name="zh-cn_topic_0264269293_p116416194299"></a>KVM</p>
</td>
</tr>
<tr id="zh-cn_topic_0264269293_row1642194292"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p126441962912"><a name="zh-cn_topic_0264269293_p126441962912"></a><a name="zh-cn_topic_0264269293_p126441962912"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p764191922910"><a name="zh-cn_topic_0264269293_p764191922910"></a><a name="zh-cn_topic_0264269293_p764191922910"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264269293_p36461917296"><a name="zh-cn_topic_0264269293_p36461917296"></a><a name="zh-cn_topic_0264269293_p36461917296"></a>ki1.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264269293_p66441992914"><a name="zh-cn_topic_0264269293_p66441992914"></a><a name="zh-cn_topic_0264269293_p66441992914"></a>KVM</p>
</td>
</tr>
<tr id="r61ab9c8af0f44c08871595bee835d693"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p764131911296"><a name="zh-cn_topic_0264269293_p764131911296"></a><a name="zh-cn_topic_0264269293_p764131911296"></a>48</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p7646197298"><a name="zh-cn_topic_0264269293_p7646197298"></a><a name="zh-cn_topic_0264269293_p7646197298"></a>192</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264269293_p156531911299"><a name="zh-cn_topic_0264269293_p156531911299"></a><a name="zh-cn_topic_0264269293_p156531911299"></a>ki1.12xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264269293_p26510194290"><a name="zh-cn_topic_0264269293_p26510194290"></a><a name="zh-cn_topic_0264269293_p26510194290"></a>KVM</p>
</td>
</tr>
<tr id="ref9e9a6072184a13b42c67e1193fe2b1"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p96521972911"><a name="zh-cn_topic_0264269293_p96521972911"></a><a name="zh-cn_topic_0264269293_p96521972911"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p106517198299"><a name="zh-cn_topic_0264269293_p106517198299"></a><a name="zh-cn_topic_0264269293_p106517198299"></a>228</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264269293_p865219192914"><a name="zh-cn_topic_0264269293_p865219192914"></a><a name="zh-cn_topic_0264269293_p865219192914"></a>ki1.16xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a134d66eb64544bdaa17aef0e6902e920"><a name="a134d66eb64544bdaa17aef0e6902e920"></a><a name="a134d66eb64544bdaa17aef0e6902e920"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 11**  超高I/O型弹性云服务器的规格

<a name="t21d3a54e6e4746f195c73f1f48abda5c"></a>
<table><thead align="left"><tr id="r33abb1e8e2284fe39c5f9e344aaca466"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="aab75f74139fa42d6899b2c1fad77335e"><a name="aab75f74139fa42d6899b2c1fad77335e"></a><a name="aab75f74139fa42d6899b2c1fad77335e"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="a20d95751ad354fd6ac5e7f1db3fcab1e"><a name="a20d95751ad354fd6ac5e7f1db3fcab1e"></a><a name="a20d95751ad354fd6ac5e7f1db3fcab1e"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="a41f4781bc39b4d738eb1ff9aea6e324d"><a name="a41f4781bc39b4d738eb1ff9aea6e324d"></a><a name="a41f4781bc39b4d738eb1ff9aea6e324d"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="a7383da87f0544cfb9dd696cd697db554"><a name="a7383da87f0544cfb9dd696cd697db554"></a><a name="a7383da87f0544cfb9dd696cd697db554"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="afda107c9aac248de89340e2ac4618a2c"><a name="afda107c9aac248de89340e2ac4618a2c"></a><a name="afda107c9aac248de89340e2ac4618a2c"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="rcad8938749524d9891dfa2f3f63ef32e"><td class="cellrowborder" rowspan="4" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="a3ad59a28ba364f9fa20263b86a44da57"><a name="a3ad59a28ba364f9fa20263b86a44da57"></a><a name="a3ad59a28ba364f9fa20263b86a44da57"></a>I3型</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="a85e52ecb6b894d93b7e98f4cb562a44b"><a name="a85e52ecb6b894d93b7e98f4cb562a44b"></a><a name="a85e52ecb6b894d93b7e98f4cb562a44b"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="a115f820a62f94e88983b9cdd03eaab86"><a name="a115f820a62f94e88983b9cdd03eaab86"></a><a name="a115f820a62f94e88983b9cdd03eaab86"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="a7db30df17d824b3cb63797d48a686527"><a name="a7db30df17d824b3cb63797d48a686527"></a><a name="a7db30df17d824b3cb63797d48a686527"></a>i3.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="ac60a5fdbffcf4e62bcd128b1bbf78143"><a name="ac60a5fdbffcf4e62bcd128b1bbf78143"></a><a name="ac60a5fdbffcf4e62bcd128b1bbf78143"></a>KVM</p>
</td>
</tr>
<tr id="r4b1bd567803948a68789ff455c3c9fb9"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ab29198ec40fe49fda6ced806ca8e0a8c"><a name="ab29198ec40fe49fda6ced806ca8e0a8c"></a><a name="ab29198ec40fe49fda6ced806ca8e0a8c"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a675bba842f4c48e58670df5b8875c353"><a name="a675bba842f4c48e58670df5b8875c353"></a><a name="a675bba842f4c48e58670df5b8875c353"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a9e6197d187674ece884408b7909f6262"><a name="a9e6197d187674ece884408b7909f6262"></a><a name="a9e6197d187674ece884408b7909f6262"></a>i3.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="aafee8d9dc3014e71a6d21f4c2c21190e"><a name="aafee8d9dc3014e71a6d21f4c2c21190e"></a><a name="aafee8d9dc3014e71a6d21f4c2c21190e"></a>KVM</p>
</td>
</tr>
<tr id="re3e8ba971cad40eeb8394b404bb7ee2c"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ae3ef03778fc34ef68156840e43986572"><a name="ae3ef03778fc34ef68156840e43986572"></a><a name="ae3ef03778fc34ef68156840e43986572"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="aa3d5979be97e4b0585b2d9b68e2e971d"><a name="aa3d5979be97e4b0585b2d9b68e2e971d"></a><a name="aa3d5979be97e4b0585b2d9b68e2e971d"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a4ec5819695df4ccbadce86b05287f089"><a name="a4ec5819695df4ccbadce86b05287f089"></a><a name="a4ec5819695df4ccbadce86b05287f089"></a>i3.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a39b7a5494eed47828495e4b2692e70d6"><a name="a39b7a5494eed47828495e4b2692e70d6"></a><a name="a39b7a5494eed47828495e4b2692e70d6"></a>KVM</p>
</td>
</tr>
<tr id="raa7bed6ea07847fab126c6ba3b27f707"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="aea55cde244ac412caecc8b63ddf47a4b"><a name="aea55cde244ac412caecc8b63ddf47a4b"></a><a name="aea55cde244ac412caecc8b63ddf47a4b"></a>60</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="ac56bfeacc957490b86fad7fa97f014fb"><a name="ac56bfeacc957490b86fad7fa97f014fb"></a><a name="ac56bfeacc957490b86fad7fa97f014fb"></a>512</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a21ebb961aec947c598bc0c32074fbf8f"><a name="a21ebb961aec947c598bc0c32074fbf8f"></a><a name="a21ebb961aec947c598bc0c32074fbf8f"></a>i3.15xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="acbfe074743f142748a636c7145d1496e"><a name="acbfe074743f142748a636c7145d1496e"></a><a name="acbfe074743f142748a636c7145d1496e"></a>KVM</p>
</td>
</tr>
<tr id="r74cb42f3ab114e299b90f4c8ad03573b"><td class="cellrowborder" rowspan="4" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p292418569254"><a name="zh-cn_topic_0264269293_p292418569254"></a><a name="zh-cn_topic_0264269293_p292418569254"></a>IR3型</p>
<p id="afc46d13bc238449cb55ca6dc05c01434"><a name="afc46d13bc238449cb55ca6dc05c01434"></a><a name="afc46d13bc238449cb55ca6dc05c01434"></a></p>
<p id="zh-cn_topic_0264269293_p7388215275"><a name="zh-cn_topic_0264269293_p7388215275"></a><a name="zh-cn_topic_0264269293_p7388215275"></a></p>
<p id="a4122ef7de7804174965d28111b86d7f6"><a name="a4122ef7de7804174965d28111b86d7f6"></a><a name="a4122ef7de7804174965d28111b86d7f6"></a></p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="a606d6082f1054abc9e1a46fcc492df37"><a name="a606d6082f1054abc9e1a46fcc492df37"></a><a name="a606d6082f1054abc9e1a46fcc492df37"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="a4b473e0515484616b47d990b3be887ba"><a name="a4b473e0515484616b47d990b3be887ba"></a><a name="a4b473e0515484616b47d990b3be887ba"></a>16</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="abc81c204cd6742ffa39d99c04784c69e"><a name="abc81c204cd6742ffa39d99c04784c69e"></a><a name="abc81c204cd6742ffa39d99c04784c69e"></a>ir3.xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="a11a4ceb5d80046b8b42542160d636268"><a name="a11a4ceb5d80046b8b42542160d636268"></a><a name="a11a4ceb5d80046b8b42542160d636268"></a>KVM</p>
</td>
</tr>
<tr id="r3bf751ba8be74467800f867a4ef5e522"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p680195842615"><a name="zh-cn_topic_0264269293_p680195842615"></a><a name="zh-cn_topic_0264269293_p680195842615"></a>8</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p580155882613"><a name="zh-cn_topic_0264269293_p580155882613"></a><a name="zh-cn_topic_0264269293_p580155882613"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a4ad225cd95b244a1b06847c9db93f2c7"><a name="a4ad225cd95b244a1b06847c9db93f2c7"></a><a name="a4ad225cd95b244a1b06847c9db93f2c7"></a>ir3.2xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a4a09666f880140c380867804cec654e5"><a name="a4a09666f880140c380867804cec654e5"></a><a name="a4a09666f880140c380867804cec654e5"></a>KVM</p>
</td>
</tr>
<tr id="rf774925214d746efb1e179012d342961"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a08d8844dc32f4401991b839efe9d373e"><a name="a08d8844dc32f4401991b839efe9d373e"></a><a name="a08d8844dc32f4401991b839efe9d373e"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="acc91b4bfe4cf4b29845bb1d0f4489a13"><a name="acc91b4bfe4cf4b29845bb1d0f4489a13"></a><a name="acc91b4bfe4cf4b29845bb1d0f4489a13"></a>64</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264269293_p153886172718"><a name="zh-cn_topic_0264269293_p153886172718"></a><a name="zh-cn_topic_0264269293_p153886172718"></a>ir3.4xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="ac5642b3a3ecb4162a18af577418ae77e"><a name="ac5642b3a3ecb4162a18af577418ae77e"></a><a name="ac5642b3a3ecb4162a18af577418ae77e"></a>KVM</p>
</td>
</tr>
<tr id="rceb52d4d0cbc4c04912507d0181d33b8"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264269293_p133801030276"><a name="zh-cn_topic_0264269293_p133801030276"></a><a name="zh-cn_topic_0264269293_p133801030276"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264269293_p19380337275"><a name="zh-cn_topic_0264269293_p19380337275"></a><a name="zh-cn_topic_0264269293_p19380337275"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264269293_p838013342717"><a name="zh-cn_topic_0264269293_p838013342717"></a><a name="zh-cn_topic_0264269293_p838013342717"></a>ir3.8xlarge.4.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264269293_p63806362717"><a name="zh-cn_topic_0264269293_p63806362717"></a><a name="zh-cn_topic_0264269293_p63806362717"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

**表 12**  GPU计算加速型（P1型）弹性云服务器的规格

<a name="tcd1d8e24028644938356622fb259aa8b"></a>
<table><thead align="left"><tr id="r745b65734dd74b63b567f0e5fab64bb7"><th class="cellrowborder" valign="top" width="25.03%" id="mcps1.2.6.1.1"><p id="a3cdb1029a37841a28f982befff419885"><a name="a3cdb1029a37841a28f982befff419885"></a><a name="a3cdb1029a37841a28f982befff419885"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="14.97%" id="mcps1.2.6.1.2"><p id="afa202ef3d21d47b7be9db88fa7b419ab"><a name="afa202ef3d21d47b7be9db88fa7b419ab"></a><a name="afa202ef3d21d47b7be9db88fa7b419ab"></a>vCPU</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.6.1.3"><p id="ad1d9a31f866e4367ac723ed610d02832"><a name="ad1d9a31f866e4367ac723ed610d02832"></a><a name="ad1d9a31f866e4367ac723ed610d02832"></a>内存(GB)</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.6.1.4"><p id="a67b54aab7ca6422a8d421e01adb07e01"><a name="a67b54aab7ca6422a8d421e01adb07e01"></a><a name="a67b54aab7ca6422a8d421e01adb07e01"></a>规格名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="a89ff269be1d449068b729703b18394d7"><a name="a89ff269be1d449068b729703b18394d7"></a><a name="a89ff269be1d449068b729703b18394d7"></a>虚拟化类型</p>
</th>
</tr>
</thead>
<tbody><tr id="rb0879be56a5c4d8c94933b8c2fdb74f9"><td class="cellrowborder" rowspan="3" valign="top" width="25.03%" headers="mcps1.2.6.1.1 "><p id="a3721bc9dc2e64733a130b0a7b931ded0"><a name="a3721bc9dc2e64733a130b0a7b931ded0"></a><a name="a3721bc9dc2e64733a130b0a7b931ded0"></a>P1型</p>
</td>
<td class="cellrowborder" valign="top" width="14.97%" headers="mcps1.2.6.1.2 "><p id="aad6ed45c67d2457684b241df62d24f5a"><a name="aad6ed45c67d2457684b241df62d24f5a"></a><a name="aad6ed45c67d2457684b241df62d24f5a"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.6.1.3 "><p id="a170ed6642cfe458ca8ab7a3a9ff19276"><a name="a170ed6642cfe458ca8ab7a3a9ff19276"></a><a name="a170ed6642cfe458ca8ab7a3a9ff19276"></a>64</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.6.1.4 "><p id="a2e8a255e8ab949a29eea01c3e45139e4"><a name="a2e8a255e8ab949a29eea01c3e45139e4"></a><a name="a2e8a255e8ab949a29eea01c3e45139e4"></a>p1.2xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="aba1efaa4298a498f8fc50ee7a5603a86"><a name="aba1efaa4298a498f8fc50ee7a5603a86"></a><a name="aba1efaa4298a498f8fc50ee7a5603a86"></a>KVM</p>
</td>
</tr>
<tr id="r4ef42dc647f641649fd0d0ef62dd8b89"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="a85a4f6f510dc4869bf7d2772bf5b0947"><a name="a85a4f6f510dc4869bf7d2772bf5b0947"></a><a name="a85a4f6f510dc4869bf7d2772bf5b0947"></a>16</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="adc621cb835514300bcd2702d831f3799"><a name="adc621cb835514300bcd2702d831f3799"></a><a name="adc621cb835514300bcd2702d831f3799"></a>128</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="a03f48343f5374c9ebdc70a9d7d8ffcb9"><a name="a03f48343f5374c9ebdc70a9d7d8ffcb9"></a><a name="a03f48343f5374c9ebdc70a9d7d8ffcb9"></a>p1.4xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a2e0b1f6eb1a64d71a84bca023709ce09"><a name="a2e0b1f6eb1a64d71a84bca023709ce09"></a><a name="a2e0b1f6eb1a64d71a84bca023709ce09"></a>KVM</p>
</td>
</tr>
<tr id="r50dc35e96a66499e8b982d0b51053a89"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="ae27d447740854bc9be2e7d08b40cf931"><a name="ae27d447740854bc9be2e7d08b40cf931"></a><a name="ae27d447740854bc9be2e7d08b40cf931"></a>32</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><p id="a7df4b4fb46f040b3bed710624f5342cc"><a name="a7df4b4fb46f040b3bed710624f5342cc"></a><a name="a7df4b4fb46f040b3bed710624f5342cc"></a>256</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="ae26264891313437c844cbe29f136c111"><a name="ae26264891313437c844cbe29f136c111"></a><a name="ae26264891313437c844cbe29f136c111"></a>p1.8xlarge.8.linux.bigdata</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="a8d12ecf401604de3ae54b19294e200bf"><a name="a8d12ecf401604de3ae54b19294e200bf"></a><a name="a8d12ecf401604de3ae54b19294e200bf"></a>KVM</p>
</td>
</tr>
</tbody>
</table>

