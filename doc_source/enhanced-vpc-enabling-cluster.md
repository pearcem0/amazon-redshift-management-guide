# Enabling Enhanced VPC Routing<a name="enhanced-vpc-enabling-cluster"></a>

You can enable Enhanced VPC Routing when you create a cluster, or you can modify an existing cluster to enable Enhanced VPC Routing\.

To work with Enhanced VPC Routing, your cluster must meet the following requirements and constraints:

+ Your cluster must be in a VPC\. 

  If you attach an Amazon S3 VPC endpoint, your cluster will use the VPC endpoint only for access to Amazon S3 buckets in the same region\. To access buckets in another region \(not using the VPC endpoint\) or to access other AWS services, make your cluster publicly accessible or use a [network address translation \(NAT\) gateway](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html)\. For more information, see [Creating a Cluster in a VPC](getting-started-cluster-in-vpc.md)\.

+ You must enable Domain Name Service \(DNS\) resolution in your VPC, or if you're using your own DNS server, ensure that DNS requests to Amazon S3 are resolved correctly to the IP addresses maintained by AWS\. For more information, see [Using DNS with Your VPC](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-dns.html)\.

+ DNS hostnames must be enabled in your VPC\. DNS hostnames are enabled by default\.

+ Your VPC endpoint policies must allow access to any Amazon S3 buckets used with COPY, UNLOAD, or CREATE LIBRARY calls in Amazon Redshift, including access to any manifest files involved\. For COPY from remote hosts, your endpoint policies must allow access to each host machine\. For more information, see [IAM Permissions for COPY, UNLOAD, and CREATE LIBRARY](http://docs.aws.amazon.com/redshift/latest/dg/copy-usage_notes-access-permissions.html#copy-usage_notes-iam-permissions) in the Amazon Redshift Database Developer Guide\.

To create a cluster with Enhanced VPC Routing enabled using the AWS Management Console, choose **Yes** for the **Enhanced VPC Routing** option in the Launch Cluster wizard’s **Configure Networking Options** section, as shown following\. For more information, see [Creating a Cluster](managing-clusters-console.md#create-cluster)\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/redshift/latest/mgmt/images/enhanced-routing-create.png)

To modify a cluster to enable Enhanced VPC Routing using the console, choose the cluster, then choose Modify Cluster and choose **Yes** for the **Enhanced VPC Routing** option in the **Modify Cluster** dialog\. For more information, see [Modifying a Cluster](managing-clusters-console.md#modify-cluster)\.

**Note**  
When you modify a cluster to enable Enhanced VPC Routing, the cluster automatically restarts to apply the change\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/redshift/latest/mgmt/images/enhanced-routing-modify.png)

You can use the following AWS Command Line Interface \(AWS CLI\) operations for Amazon Redshift to enable Enhanced VPC Routing\.

+ [create\-cluster ](http://docs.aws.amazon.com/cli/latest/reference/redshift/create-cluster.html)

+ [modify\-cluster](http://docs.aws.amazon.com/cli/latest/reference/redshift/modify-cluster.html)

 You can use the following Amazon Redshift APIs actions to enable Enhanced VPC Routing\.

+ [CreateCluster](http://docs.aws.amazon.com/redshift/latest/APIReference/API_CreateCluster.html)

+ [ModifyCluster](http://docs.aws.amazon.com/redshift/latest/APIReference/API_ModifyCluster.html)