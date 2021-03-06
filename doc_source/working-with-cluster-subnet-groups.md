# Amazon Redshift Cluster Subnet Groups<a name="working-with-cluster-subnet-groups"></a>

## Overview<a name="working-with-cluster-subnet-groups-overview"></a>

You create a cluster subnet group if you are provisioning your cluster in your virtual private cloud \(VPC\)\. For more information about VPC, go to [Amazon Virtual Private Cloud \(Amazon VPC\)](https://aws.amazon.com/vpc/) *product detail page*\.

Your VPC can have one or more subnets, a subset of IP addresses within your VPC, that enable you to group your resources based on your security and operation needs\. A cluster subnet group allows you to specify a set of subnets in your VPC\. When provisioning a cluster you provide the subnet group and Amazon Redshift creates the cluster on one of the subnets in the group\. 

For more information about creating a VPC, go to [Amazon VPC User Guide](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/) Documentation\.

After creating a subnet group, you can remove subnets you previously added or add more subnets\. Amazon Redshift provides APIs for you to create, modify or delete a cluster subnet group\. You can also perform these operations in the console\.