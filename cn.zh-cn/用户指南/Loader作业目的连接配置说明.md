# Loader作业目的连接配置说明<a name="ZH-CN_TOPIC_0173178884"></a>

## 基本介绍<a name="sf4db6484f4f947c1a67e8d2a1652b035"></a>

Loader作业需要将数据保存到不同目的存储位置时，应该选择对应类型的目的连接，每种连接在该场景中需要配置连接的属性。

## obs-connector<a name="s6d4f1f57f7d946518783a17a4f4a200c"></a>

**表 1**  obs-connector目的连接属性

<a name="t56a7d8c11195431fb3877b80b9539cab"></a>
<table><thead align="left"><tr id="rb7b0153467a140deaeed3f9cc7093eb2"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a67ead871b0204914af6b12b55c064129"><a name="a67ead871b0204914af6b12b55c064129"></a><a name="a67ead871b0204914af6b12b55c064129"></a><strong id="a50086b6049d84f72ada089d272151fc3"><a name="a50086b6049d84f72ada089d272151fc3"></a><a name="a50086b6049d84f72ada089d272151fc3"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a248d5396ad184cc7ad5ae64c5f402c59"><a name="a248d5396ad184cc7ad5ae64c5f402c59"></a><a name="a248d5396ad184cc7ad5ae64c5f402c59"></a><strong id="a69ae4d9332ca44adb537f9b382002b21"><a name="a69ae4d9332ca44adb537f9b382002b21"></a><a name="a69ae4d9332ca44adb537f9b382002b21"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r07847718f0704541b6bff575e5784f9c"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a7fe524d77a614a5ea912e285ca0fc125"><a name="a7fe524d77a614a5ea912e285ca0fc125"></a><a name="a7fe524d77a614a5ea912e285ca0fc125"></a>桶名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a881633228678422f95ab2c458c31c4b1"><a name="a881633228678422f95ab2c458c31c4b1"></a><a name="a881633228678422f95ab2c458c31c4b1"></a>保存最终数据的OBS桶。</p>
</td>
</tr>
<tr id="r16b75f9011cd4c7d99ab371ed47ed51c"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ac4c68684857e4efc99d99dc85222c02c"><a name="ac4c68684857e4efc99d99dc85222c02c"></a><a name="ac4c68684857e4efc99d99dc85222c02c"></a>写入目录</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a9f77db72f4ed4e958b65c42e3b9de45c"><a name="a9f77db72f4ed4e958b65c42e3b9de45c"></a><a name="a9f77db72f4ed4e958b65c42e3b9de45c"></a>最终数据在桶保存时的具体目录。必须指定一个目录。</p>
</td>
</tr>
<tr id="r2305e8f75ae847d1b84dc864de398133"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="aee06b3797d234ec5b860baedf97f7886"><a name="aee06b3797d234ec5b860baedf97f7886"></a><a name="aee06b3797d234ec5b860baedf97f7886"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a9c3d17fe47a24df8b40eb67d49bde80c"><a name="a9c3d17fe47a24df8b40eb67d49bde80c"></a><a name="a9c3d17fe47a24df8b40eb67d49bde80c"></a>Loader支持OBS中存储数据的文件格式，默认支持以下两种：</p>
<a name="ua203f41442a14e63b349131dac80d508"></a><a name="ua203f41442a14e63b349131dac80d508"></a><ul id="ua203f41442a14e63b349131dac80d508"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="r18f80222f79e42b7a65ec4737fba9d3f"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ab11f2e51a1494873b852abd8794c8ada"><a name="ab11f2e51a1494873b852abd8794c8ada"></a><a name="ab11f2e51a1494873b852abd8794c8ada"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a933cf558c3974613a0e9b86866d9ebb3"><a name="a933cf558c3974613a0e9b86866d9ebb3"></a><a name="a933cf558c3974613a0e9b86866d9ebb3"></a>最终数据的每行结束标识字符。</p>
</td>
</tr>
<tr id="rbca97f25e93e45c9a5168f32c3c66b12"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a0e26894054cf412ca85a2847d50abdb2"><a name="a0e26894054cf412ca85a2847d50abdb2"></a><a name="a0e26894054cf412ca85a2847d50abdb2"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a51fc0e5a558544a4a251c3366b4700f7"><a name="a51fc0e5a558544a4a251c3366b4700f7"></a><a name="a51fc0e5a558544a4a251c3366b4700f7"></a>最终数据的每个字段分割标识字符。</p>
</td>
</tr>
<tr id="rf8b40b927d4145b88d8d680c82896b93"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a6977dff1a749499cbefcaa2908c0f901"><a name="a6977dff1a749499cbefcaa2908c0f901"></a><a name="a6977dff1a749499cbefcaa2908c0f901"></a>编码类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ad3c196a1c9f24a7c9a90ef29022c7007"><a name="ad3c196a1c9f24a7c9a90ef29022c7007"></a><a name="ad3c196a1c9f24a7c9a90ef29022c7007"></a>最终数据的文本编码类型。只对文本类型文件有效。</p>
</td>
</tr>
</tbody>
</table>

## generic-jdbc-connector<a name="s2ef6997327ec4448a256efa62d00dd8f"></a>

**表 2**  generic-jdbc-connector目的连接属性

<a name="tbf6ec10da2b443b18168e9e37dc648d8"></a>
<table><thead align="left"><tr id="r71d3668e828842cc922153b1982568cb"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a8e7577dc339748c3ace69ca7a1995b09"><a name="a8e7577dc339748c3ace69ca7a1995b09"></a><a name="a8e7577dc339748c3ace69ca7a1995b09"></a><strong id="a35868dc3d6844155a04263842d7a6121"><a name="a35868dc3d6844155a04263842d7a6121"></a><a name="a35868dc3d6844155a04263842d7a6121"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a3af52b28f7be4da89dd5d9bd3fce775e"><a name="a3af52b28f7be4da89dd5d9bd3fce775e"></a><a name="a3af52b28f7be4da89dd5d9bd3fce775e"></a><strong id="a93e7bacfc9b943caa747d971f88ed27e"><a name="a93e7bacfc9b943caa747d971f88ed27e"></a><a name="a93e7bacfc9b943caa747d971f88ed27e"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r836c7340842c4478bdf8b311e721c1f1"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ab6d989b0560248f9b4f85c075ada4e74"><a name="ab6d989b0560248f9b4f85c075ada4e74"></a><a name="ab6d989b0560248f9b4f85c075ada4e74"></a>模式名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a955c3c3dc1454c3db5cc47d7cad05b34"><a name="a955c3c3dc1454c3db5cc47d7cad05b34"></a><a name="a955c3c3dc1454c3db5cc47d7cad05b34"></a>保存最终数据的数据库名称。</p>
</td>
</tr>
<tr id="r5e341ebcc6e24ec3ab6d1b5e9e096855"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a854db138893d45d4b88268991fed0721"><a name="a854db138893d45d4b88268991fed0721"></a><a name="a854db138893d45d4b88268991fed0721"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a8aae9d8199954ae3a80386b9cbe1f277"><a name="a8aae9d8199954ae3a80386b9cbe1f277"></a><a name="a8aae9d8199954ae3a80386b9cbe1f277"></a>保存最终数据的数据表名称。</p>
</td>
</tr>
</tbody>
</table>

## ftp-connector或sftp-connector<a name="sffd34a136db7486295f08167d80914d3"></a>

**表 3**  ftp-connector或sftp-connector目的连接属性

<a name="t161560b9aca8429c972e5b5df931beba"></a>
<table><thead align="left"><tr id="r43ae323c72f54f97a947909d7a897c38"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="afafe26c8621d4481bec4ac4ea4d18e18"><a name="afafe26c8621d4481bec4ac4ea4d18e18"></a><a name="afafe26c8621d4481bec4ac4ea4d18e18"></a><strong id="a71f34a05bb584365be15fb034be95f70"><a name="a71f34a05bb584365be15fb034be95f70"></a><a name="a71f34a05bb584365be15fb034be95f70"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a71d73e26126f4366b9e08b830068109b"><a name="a71d73e26126f4366b9e08b830068109b"></a><a name="a71d73e26126f4366b9e08b830068109b"></a><strong id="a3e0a531ed1b04fb998aca4a01017a05c"><a name="a3e0a531ed1b04fb998aca4a01017a05c"></a><a name="a3e0a531ed1b04fb998aca4a01017a05c"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r0cfea59125fc4836b8d0ed1f825bfd06"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a5a4f69a69103482fae75f177d6ed3cbc"><a name="a5a4f69a69103482fae75f177d6ed3cbc"></a><a name="a5a4f69a69103482fae75f177d6ed3cbc"></a>写入目录</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aded13967ce994e91925366c14559c6ca"><a name="aded13967ce994e91925366c14559c6ca"></a><a name="aded13967ce994e91925366c14559c6ca"></a>最终数据在文件服务器保存时的具体目录。必须指定一个目录。</p>
</td>
</tr>
<tr id="rd6360ee259e741c1b7d8880fb2ec6161"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a96ca0c8ad06548d199b008cb9691f0b9"><a name="a96ca0c8ad06548d199b008cb9691f0b9"></a><a name="a96ca0c8ad06548d199b008cb9691f0b9"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a022bedfa25234562a419e7a7c5e1efe8"><a name="a022bedfa25234562a419e7a7c5e1efe8"></a><a name="a022bedfa25234562a419e7a7c5e1efe8"></a>Loader支持文件服务器中存储数据的文件格式，默认支持以下两种：</p>
<a name="u2cc922e6badd46fe84bbff316f36b2b1"></a><a name="u2cc922e6badd46fe84bbff316f36b2b1"></a><ul id="u2cc922e6badd46fe84bbff316f36b2b1"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="r71117888b8b94eaca06df40d859dd741"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ae0d38c2d379f4ddab669f57b14d1a3ef"><a name="ae0d38c2d379f4ddab669f57b14d1a3ef"></a><a name="ae0d38c2d379f4ddab669f57b14d1a3ef"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a5555fd7400e942c89e4681c0ac2d3116"><a name="a5555fd7400e942c89e4681c0ac2d3116"></a><a name="a5555fd7400e942c89e4681c0ac2d3116"></a>最终数据的每行结束标识字符。</p>
<div class="note" id="n4748c5f3970b4286aa17382dc2450dcc"><a name="n4748c5f3970b4286aa17382dc2450dcc"></a><a name="n4748c5f3970b4286aa17382dc2450dcc"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="aecead33cc33b42a9bef7510c04b9637f"><a name="aecead33cc33b42a9bef7510c04b9637f"></a><a name="aecead33cc33b42a9bef7510c04b9637f"></a>ftp或sftp作为目的连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“换行符”配置无效。</p>
</div></div>
</td>
</tr>
<tr id="r641fed345951440f9212431735ab1952"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ac0d8bc4c59284887aa6db6bada8224a0"><a name="ac0d8bc4c59284887aa6db6bada8224a0"></a><a name="ac0d8bc4c59284887aa6db6bada8224a0"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a1d3f89f4632a496d828470918d78db34"><a name="a1d3f89f4632a496d828470918d78db34"></a><a name="a1d3f89f4632a496d828470918d78db34"></a>最终数据的每个字段分割标识字符。</p>
<div class="note" id="n70c14e72a4ff45caa9327d106708c18d"><a name="n70c14e72a4ff45caa9327d106708c18d"></a><a name="n70c14e72a4ff45caa9327d106708c18d"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a366da565302e4b5fab1da9b5e8842e1d"><a name="a366da565302e4b5fab1da9b5e8842e1d"></a><a name="a366da565302e4b5fab1da9b5e8842e1d"></a>ftp或sftp作为目的连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“字段分割符”配置无效</p>
</div></div>
</td>
</tr>
<tr id="rda3cd602372d472eb7f3ba0505324f31"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ab9f6fa964d5b4790807960f9809e8475"><a name="ab9f6fa964d5b4790807960f9809e8475"></a><a name="ab9f6fa964d5b4790807960f9809e8475"></a>编码类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aaad609187f2a462fb6f9de2053132afc"><a name="aaad609187f2a462fb6f9de2053132afc"></a><a name="aaad609187f2a462fb6f9de2053132afc"></a>最终数据的文本编码类型。只对文本类型文件有效。</p>
</td>
</tr>
</tbody>
</table>

## hbase-connector<a name="s57ae469628564482ae0d21c53587b278"></a>

**表 4**  hbase-connector目的连接属性

<a name="t7b84781f6036461793071602b9770da4"></a>
<table><thead align="left"><tr id="rb23a85b8c87e423bad16fea7983d9a9f"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a02f8e61f499642b8ac6ace4139bd05b4"><a name="a02f8e61f499642b8ac6ace4139bd05b4"></a><a name="a02f8e61f499642b8ac6ace4139bd05b4"></a><strong id="a5682039e7c834d3f856e8563f37cbe20"><a name="a5682039e7c834d3f856e8563f37cbe20"></a><a name="a5682039e7c834d3f856e8563f37cbe20"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a7c71743370c84f658e105f5152403f3c"><a name="a7c71743370c84f658e105f5152403f3c"></a><a name="a7c71743370c84f658e105f5152403f3c"></a><strong id="a6ee1f0eca6344460955681419f19ffc2"><a name="a6ee1f0eca6344460955681419f19ffc2"></a><a name="a6ee1f0eca6344460955681419f19ffc2"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="re79d99e87dd64e4a92490c61ae5b12ac"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a796f7624aa6d4cfeb19efe45cf2c9fb1"><a name="a796f7624aa6d4cfeb19efe45cf2c9fb1"></a><a name="a796f7624aa6d4cfeb19efe45cf2c9fb1"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a4457a35390644911a4b7b0ce274eddf1"><a name="a4457a35390644911a4b7b0ce274eddf1"></a><a name="a4457a35390644911a4b7b0ce274eddf1"></a>保存最终数据的HBase表名称，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="r85abe1201f1a4d6b882a7a7e84f61776"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="aa09941b252c7478da8552179bb754ae4"><a name="aa09941b252c7478da8552179bb754ae4"></a><a name="aa09941b252c7478da8552179bb754ae4"></a>导入方式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="af58b77e5556542c6abc4c5d4b7c5fc1f"><a name="af58b77e5556542c6abc4c5d4b7c5fc1f"></a><a name="af58b77e5556542c6abc4c5d4b7c5fc1f"></a>支持BULKLOAD、PUTLIST两种方式导入数据到HBase表。</p>
</td>
</tr>
<tr id="rb94aa94a3e5d4bc7b8136931def0faef"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a808037bf198844a3a11245e41e7c539f"><a name="a808037bf198844a3a11245e41e7c539f"></a><a name="a808037bf198844a3a11245e41e7c539f"></a>导入前清空数据</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="af892c2aadef24f29b81cf366b8d42f7e"><a name="af892c2aadef24f29b81cf366b8d42f7e"></a><a name="af892c2aadef24f29b81cf366b8d42f7e"></a>标识是否需要清空目标HBase表中的数据，支持以下两种类型：</p>
<a name="u63d56d92dbf1438484aa332e2a6cc3fd"></a><a name="u63d56d92dbf1438484aa332e2a6cc3fd"></a><ul id="u63d56d92dbf1438484aa332e2a6cc3fd"><li>True：清空表中的数据。</li><li>False：不清空表中的数据，选择False时如果表中存在数据，则作业运行会报错。</li></ul>
</td>
</tr>
</tbody>
</table>

## hdfs-connector<a name="s0e7a49c2520c498aa9e3d9fa84325e2e"></a>

**表 5**  hdfs-connector目的连接属性

<a name="t0549e6c84ff84d08a87e8e1856d0561b"></a>
<table><thead align="left"><tr id="r4df7bda561a24d95887ff2015a4eadb7"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="ad0f79bb317df452c81a461472ab0ff19"><a name="ad0f79bb317df452c81a461472ab0ff19"></a><a name="ad0f79bb317df452c81a461472ab0ff19"></a><strong id="a8bf7b00dd1d84f32b89828899c444bfb"><a name="a8bf7b00dd1d84f32b89828899c444bfb"></a><a name="a8bf7b00dd1d84f32b89828899c444bfb"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="ac6fc0ca7732f467bbe6120d363d13790"><a name="ac6fc0ca7732f467bbe6120d363d13790"></a><a name="ac6fc0ca7732f467bbe6120d363d13790"></a><strong id="a29030d6fc852402a93d886e3d0270f3b"><a name="a29030d6fc852402a93d886e3d0270f3b"></a><a name="a29030d6fc852402a93d886e3d0270f3b"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="rde0c581a3b1f4a1290c81339ec61caf4"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p385045217275"><a name="zh-cn_topic_0071084973_p385045217275"></a><a name="zh-cn_topic_0071084973_p385045217275"></a>写入目录</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aa204024af5604ccc9a295c0b98ef31c8"><a name="aa204024af5604ccc9a295c0b98ef31c8"></a><a name="aa204024af5604ccc9a295c0b98ef31c8"></a>最终数据在HDFS保存时的具体目录。必须指定一个目录。</p>
</td>
</tr>
<tr id="r576b28a3bd554bdbb6c4b0db1379f398"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a59125ed8641d45e38bfa8ab88c68ead2"><a name="a59125ed8641d45e38bfa8ab88c68ead2"></a><a name="a59125ed8641d45e38bfa8ab88c68ead2"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a7d8ea3077a70449c9cea01fe96819b00"><a name="a7d8ea3077a70449c9cea01fe96819b00"></a><a name="a7d8ea3077a70449c9cea01fe96819b00"></a>Loader支持HDFS中存储数据的文件格式，默认支持以下两种：</p>
<a name="udb8bf478df304e54b353f69a76f112d3"></a><a name="udb8bf478df304e54b353f69a76f112d3"></a><ul id="udb8bf478df304e54b353f69a76f112d3"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="r79d42af328aa414fba6a7460e97641dc"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p402135418121"><a name="zh-cn_topic_0071084973_p402135418121"></a><a name="zh-cn_topic_0071084973_p402135418121"></a>压缩格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a9dc559c110f048b3b30ad6bbe3508bf9"><a name="a9dc559c110f048b3b30ad6bbe3508bf9"></a><a name="a9dc559c110f048b3b30ad6bbe3508bf9"></a>文件在HDFS保存时的压缩行为。支持NONE、DEFLATE、GZIP、BZIP2、LZ4和SNAPPY。</p>
</td>
</tr>
<tr id="rec0c3a4cc48c4b5a92b179e6dabfb7bc"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ad202a0bf826b48959c0b0abc64ef82ad"><a name="ad202a0bf826b48959c0b0abc64ef82ad"></a><a name="ad202a0bf826b48959c0b0abc64ef82ad"></a>是否覆盖</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a0c7e205c10f248b59250ac409c0529d0"><a name="a0c7e205c10f248b59250ac409c0529d0"></a><a name="a0c7e205c10f248b59250ac409c0529d0"></a>文件在导入HDFS时对写入目录中原有文件的处理行为，支持以下两种：</p>
<a name="u85778ae080024bbb92178a5583c51ca0"></a><a name="u85778ae080024bbb92178a5583c51ca0"></a><ul id="u85778ae080024bbb92178a5583c51ca0"><li>True：默认清空目录中的文件并导入新文件。</li><li>False：不清空文件。如果写入目录中有文件，则作业运行失败。</li></ul>
</td>
</tr>
<tr id="r29f7bdc84cb1475aa47829459e18dad6"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a78d95ac0f934435b83eebf54ecbf3f39"><a name="a78d95ac0f934435b83eebf54ecbf3f39"></a><a name="a78d95ac0f934435b83eebf54ecbf3f39"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a2e1f0c3696f948118860c863aef82dd1"><a name="a2e1f0c3696f948118860c863aef82dd1"></a><a name="a2e1f0c3696f948118860c863aef82dd1"></a>最终数据的每行结束标识字符。</p>
<div class="note" id="n0daee149ceb94e0c9f1e88e783cb47f4"><a name="n0daee149ceb94e0c9f1e88e783cb47f4"></a><a name="n0daee149ceb94e0c9f1e88e783cb47f4"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a8c4817d3136f47809570cddcea4db740"><a name="a8c4817d3136f47809570cddcea4db740"></a><a name="a8c4817d3136f47809570cddcea4db740"></a>hdfs作为目的连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“换行符”配置无效。</p>
</div></div>
</td>
</tr>
<tr id="r94151ab15063402c8eef321739124c9b"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ad6c56e6bacd84f8680ab686f926c7112"><a name="ad6c56e6bacd84f8680ab686f926c7112"></a><a name="ad6c56e6bacd84f8680ab686f926c7112"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="affdcb2b07f0b448d8445f59c8f186051"><a name="affdcb2b07f0b448d8445f59c8f186051"></a><a name="affdcb2b07f0b448d8445f59c8f186051"></a>最终数据的每个字段分割标识字符。</p>
<div class="note" id="ne6127968535b4cf8adb834946d43a0c9"><a name="ne6127968535b4cf8adb834946d43a0c9"></a><a name="ne6127968535b4cf8adb834946d43a0c9"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a86015f958d9e4ada9aec40acf3d6c5b0"><a name="a86015f958d9e4ada9aec40acf3d6c5b0"></a><a name="a86015f958d9e4ada9aec40acf3d6c5b0"></a>hdfs作为目的连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“字段分割符”配置无效</p>
</div></div>
</td>
</tr>
</tbody>
</table>

## hive-connector<a name="sa29e63b9762c42a5895bc17a1240edc9"></a>

**表 6**  hive-connector目的连接属性

<a name="t1ad287517e244db183344638cc1d0637"></a>
<table><thead align="left"><tr id="ra5051a7b50e1476799f649dd4b129f8e"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a7775e8ad23be449c97a2100f092a7ca5"><a name="a7775e8ad23be449c97a2100f092a7ca5"></a><a name="a7775e8ad23be449c97a2100f092a7ca5"></a><strong id="zh-cn_topic_0071084973_b816290111751"><a name="zh-cn_topic_0071084973_b816290111751"></a><a name="zh-cn_topic_0071084973_b816290111751"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a562a111106ed40b3aef74305b37f684e"><a name="a562a111106ed40b3aef74305b37f684e"></a><a name="a562a111106ed40b3aef74305b37f684e"></a><strong id="a0a971c05d19f425c8afbeacf135a50d0"><a name="a0a971c05d19f425c8afbeacf135a50d0"></a><a name="a0a971c05d19f425c8afbeacf135a50d0"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="ra0bf9ca5b54b44df82b645c92b3357bf"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a1166a8fe5a09431ab58ddc49ef6209c9"><a name="a1166a8fe5a09431ab58ddc49ef6209c9"></a><a name="a1166a8fe5a09431ab58ddc49ef6209c9"></a>数据库名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a62d6fa69ff5b4c2d8aa8bd8032525093"><a name="a62d6fa69ff5b4c2d8aa8bd8032525093"></a><a name="a62d6fa69ff5b4c2d8aa8bd8032525093"></a>保存最终数据的Hive数据库名称，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="r3ddbb8a921714a3c931d5c897bdb5516"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="aa9d4983c5d3d42b3a1d71357fb75b265"><a name="aa9d4983c5d3d42b3a1d71357fb75b265"></a><a name="aa9d4983c5d3d42b3a1d71357fb75b265"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aa2f4671db59940d08b5f3a3619d06bd7"><a name="aa2f4671db59940d08b5f3a3619d06bd7"></a><a name="aa2f4671db59940d08b5f3a3619d06bd7"></a>保存最终数据的Hive表名称，支持通过界面查询并选择。</p>
</td>
</tr>
</tbody>
</table>

## voltdb-connector<a name="s15051302e0cd417487fa5ef090f2a624"></a>

**表 7**  voltdb-connector目的连接属性

<a name="t1bee96f1234c4d6c9bb74908b14d0668"></a>
<table><thead align="left"><tr id="r3b396e8bfc9949f3b2441a936c09037a"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a94fcaaf7f90f48a0a9659bc1ae7bd9fa"><a name="a94fcaaf7f90f48a0a9659bc1ae7bd9fa"></a><a name="a94fcaaf7f90f48a0a9659bc1ae7bd9fa"></a><strong id="a6a7032ae7f924aa89c305a633238b423"><a name="a6a7032ae7f924aa89c305a633238b423"></a><a name="a6a7032ae7f924aa89c305a633238b423"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a8e29dd38d2c442d6bff5f3d7829d7b41"><a name="a8e29dd38d2c442d6bff5f3d7829d7b41"></a><a name="a8e29dd38d2c442d6bff5f3d7829d7b41"></a><strong id="aac5bfc2e00c042c0ae22dd14530db9c8"><a name="aac5bfc2e00c042c0ae22dd14530db9c8"></a><a name="aac5bfc2e00c042c0ae22dd14530db9c8"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r6e135857e1aa477fa6d1af9324ae7d21"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="af4e505ea62c9459bb38e96f05bacf6f4"><a name="af4e505ea62c9459bb38e96f05bacf6f4"></a><a name="af4e505ea62c9459bb38e96f05bacf6f4"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aba6c09c09edc43d892eda3ce31fb4f92"><a name="aba6c09c09edc43d892eda3ce31fb4f92"></a><a name="aba6c09c09edc43d892eda3ce31fb4f92"></a>保存最终数据的内存数据库表，支持通过界面查询并选择。</p>
</td>
</tr>
</tbody>
</table>

