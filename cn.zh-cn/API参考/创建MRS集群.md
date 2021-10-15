# 创建MRS集群<a name="mrs_02_0112"></a>

## 场景描述<a name="section1899720324342"></a>

本章节指导用户通过API创建一个MRS分析集群。API的调用方法请参见[如何调用API](构造请求.md)。

## 约束限制<a name="section531216497349"></a>

-   已在待创建集群区域通过虚拟私有云服务创建VPC，子网，请参考[查询VPC列表](https://support.huaweicloud.com/api-vpc/vpc_api01_0003.html)和[创建VPC](https://support.huaweicloud.com/api-vpc/vpc_api01_0001.html)和[查询子网列表](https://support.huaweicloud.com/api-vpc/vpc_subnet01_0003.html)和[创建子网](https://support.huaweicloud.com/api-vpc/vpc_subnet01_0001.html)。
-   已获取待创建集群区域的区域和可用区信息，请参见[终端节点及区域](https://developer.huaweicloud.com/endpoint?MRS)获取。
-   已获取待创建集群区域的项目ID，请参考[获取项目ID](获取项目ID.md)获取。
-   已确定待创建集群的版本及版本支持的组件信息，请参见[MRS组件版本一览表](https://support.huaweicloud.com/productdesc-mrs/mrs_08_0005.html)。
-   该示例创建出来的是按需购买的分析集群。

## 操作步骤<a name="section16151251183414"></a>

-   接口相关信息

    URI格式：POST /v2/\{project\_id\}/clusters

    详情请参见[创建集群](创建集群.md)。

-   请求示例

    POST: https://_\{endpoint\}_/v2/_\{project\_id\}_/clusters

    -   \{endpoint\}信息请参见[终端节点及区域](https://developer.huaweicloud.com/endpoint?MRS)获取。
    -   \{project\_id\}信息请通过[获取项目ID](获取项目ID.md)获取。

    Body：

    ```
    {
      "cluster_version": "MRS 3.0.2MRS 3.1.0",
      "cluster_name": "mrs_Demo",
      "cluster_type": "ANALYSIS",
      "charge_info": {
    	  "charge_mode": "postPaid"
      },
      "region": "",
      "availability_zone": "",
      "vpc_name": "vpc-37cd",
      "subnet_id": "1f8c5ca6-1f66-4096-bb00-baf175954f6e",
      "components": "Hadoop,Spark2x,HBase,Hive,Hue,Loader,Flink,Oozie,Ranger,Tez",
      "safe_mode": "KERBEROS",
      "manager_admin_password": "Mrs@1234",
      "login_mode": "PASSWORD",
      "node_root_password": "Mrs@1234",
      "log_collection": 1,
      "mrs_ecs_default_agency": "MRS_ECS_DEFAULT_AGENCY",
      "tags": [
        {
          "key": "tag1",
          "value": "111"
        },
        {
          "key": "tag2",
          "value": "222"
        }
      ], 
      "node_groups": [
        {
          "group_name": "master_node_default_group",
          "node_num": 2,
          "node_size": "rc3.4xlarge.4.linux.bigdata",
          "root_volume": {
            "type": "SAS",
            "size": 100
          },
          "data_volume": {
            "type": "SAS",
            "size": 600
          },
          "data_volume_count": 1
        },
       {
          "group_name": "core_node_analysis_group",
          "node_num": 3,
          "node_size": "rc3.4xlarge.4.linux.bigdata",
          "root_volume": {
            "type": "SAS",
            "size": 100
          },
          "data_volume": {
            "type": "SAS",
            "size": 600
          },
          "data_volume_count": 1
        },
        {
          "group_name": "task_node_analysis_group",
          "node_num": 3,
          "node_size": "rc3.4xlarge.4.linux.bigdata",
          "root_volume": {
            "type": "SAS",
            "size": 100
          },
          "data_volume": {
            "type": "SAS",
            "size": 600
          },
          "data_volume_count": 1,
    	 "auto_scaling_policy": {
                    "auto_scaling_enable": true,
                    "min_capacity": 0,
                    "max_capacity": 1,
                    "resources_plans": [],
                    "exec_scripts": [],
                    "rules": [
                        {
                            "name": "default-expand-1",
                            "description": "",
                            "adjustment_type": "scale_out",
                            "cool_down_minutes": 5,
                            "scaling_adjustment": "1",
                            "trigger": {
                                "metric_id": 2003,
                                "metric_name": "StormSlotAvailablePercentage",
                                "metric_value": 100,
                                "comparison_operator_id": 2003,
                                "comparison_operator": "LTOE",
                                "evaluation_periods": "1"
                            }
                        }
                    ]
                }
        }
      ]
    }
    ```

    参数详细信息请参考[创建集群](创建集群.md)获取。

-   响应示例

    ```
    {
    	"cluster_id": "da1592c2-bb7e-468d-9ac9-83246e95447a"
    }
    ```


