# 使用curl命令操作OpenTSDB<a name="ZH-CN_TOPIC_0176678777"></a>

## 写入数据<a name="section937319270818"></a>

例如，录入一个指标名称为testdata，时间戳为1524900185，值为true，标签为key，value的指标数据。

```
curl -ki -X POST -d '{"metric":"testdata", "timestamp":1524900185, "value":"true", "tags":{"key":"value"}}' https://<tsd_ip>:4242/api/put?sync
```

<tsd\_ip\>表示所需写入数据的Opentsdb服务的TSD实例的IP地址。

```
HTTP/1.1 204 No Content
Content-Type: application/json; charset=UTF-8
Content-Length:0
```

## 查询数据<a name="section126481332391"></a>

例如，可查询指标testdata在过去三年中中的汇总信息。

```
curl -ks https://<tsd_ip>:4242/api/query?start=3y-ago\&m=sum:testdata | python -m json.tool
```

-   <tsd\_ip\>：所需访问Opentsdb服务的TSD实例IP或主机名。
-   <start=3y-ago\\&m=sum:testdata\>：在请求中可能无法识别“&”符号，需对其进行转义。
-   <python -m json.tool\>（可选）: 把响应的请求转换为json格式。

```
[
    {
        "aggregateTags": [],
        "dps": {
            "1524900185": 1
        },
        "metric": "testdata",
        "tags": {
            "key": "value"
        }
    }
]
```

## 查询tsd状态信息<a name="section1740125111310"></a>

例如，可查询连接HBase的客户端信息。

```
curl -ks https://<tsd_ip>:4242/api/stats/region_clients | python -m json.tool
```

<tsd\_ip\>：所需访问Opentsdb服务的TSD实例IP地址。

```
[
    {
        "dead": false,
        "endpoint":"/xx.xx.xx.xx:16020",
        "inflightBreached": 0,
        "pendingBatchedRPCs": 0,
        "pendingBreached": 0,
        "pendingRPCs": 0,
        "rpcResponsesTimedout": 0,
        "rpcResponsesUnknown": 0,
        "rpcid": 78,
        "rpcsInFlight": 0,
        "rpcsSent": 79,
        "rpcsTimedout": 0,
        "writesBlocked": 0
    }
]
```

