# 创建MRS自定义策略<a name="mrs_01_0455"></a>

如果系统预置的MRS权限，不满足您的授权要求，可以创建自定义策略。自定义策略中可以添加的授权项（Action）请参考[策略及授权项说明](https://support.huaweicloud.com/api-mrs/mrs_02_0083.html)。

目前支持以下两种方式创建自定义策略：

-   可视化视图创建自定义策略：无需了解策略语法，按可视化视图导航栏选择云服务、操作、资源、条件等策略内容，可自动生成策略。
-   JSON视图创建自定义策略：可以在选择策略模板后，根据具体需求编辑策略内容；也可以直接在编辑框内编写JSON格式的策略内容。

具体创建步骤请参见：[创建自定义策略](https://support.huaweicloud.com/usermanual-iam/iam_01_0605.html)。本章为您介绍常用的MRS自定义策略样例。

## MRS自定义策略样例<a name="section106232058111114"></a>

-   示例1：授权用户仅有创建MRS集群的权限

    ```
    {
        "Version": "1.1",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "mrs:cluster:create",
                    "ecs:*:*",
                    "bms:*:*",
                    "evs:*:*",
                    "vpc:*:*"
                ]
            }
        ]
    }
    ```

-   示例2：授权用户调整MRS集群

    ```
    { 
        "Version": "1.1", 
        "Statement": [ 
            { 
                "Effect": "Allow", 
                "Action": [ 
                    "mrs:cluster:resize" 
                ] 
            } 
        ] 
    }
    ```

-   示例3：授权用户创建集群、创建并执行作业、删除单个作业，但不允许用户删除集群的权限

    ```
    {
        "Version": "1.1",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "mrs:cluster:create",
                    "mrs:job:submit",
                    "mrs:job:delete"
                ]
            },
            {
                "Effect": "Deny",
                "Action": [
                    "mrs:cluster:delete"
                ]
            }
        ]
    }
    ```


