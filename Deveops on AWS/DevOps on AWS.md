“基于 EC2 的 AWS Code系列 CI/CD 动手练习示例 ”实验手册地址 https://github.com/awslabs/aws-devops-essential
备注：可以尝试修改部署方案，比如在EC2 Instance前加入ALB，修改CodeDeploy部署模式实现蓝绿部署

“Infrastructure as a Code 动手练习示例 ”实验手册地址https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/continuous-delivery-codepipeline-basic-walkthrough.html 备注： 1）手册中的Infra Code默认保存在S3中，可以尝试修改Code Repo Source至CodeCommit中，如实验演练中所示；手册中 2）因样例中wordpress的yaml模版中wordpress的配置需要使用较老版本的wordpress软件，所以yaml模版中原有的代码“/var/www/html: http://wordpress.org/latest.tar.gz” 需要替换为“/var/www/html: https://wordpress.org/wordpress-3.7.12.tar.gz”才能部署成功

“基于 EKS 的 AWS Code系列 CI/CD 动手练习示例 ”实验手册地址 https://github.com/aws-samples/aws-kube-codesuite
备注：请选择在AWS “us-west-2” Region完成该练习，其他Region运行CloudFormation模版会遇到Lambda部署EKS应用失败的问题，需要修改Lambda函数中和Region相关的代码