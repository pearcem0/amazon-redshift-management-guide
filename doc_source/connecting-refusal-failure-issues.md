# The Connection Is Refused or Fails<a name="connecting-refusal-failure-issues"></a>

**Example errors:**

+ "Failed to establish a connection to *<endpoint>*\."

+ "Could not connect to server: Connection timed out\. Is the server running on host *'<endpoint>'* and accepting TCP/IP connections on port *'<port>'*?"

+ "Connection refused\. Check that the hostname and port are correct and that the postmaster is accepting TCP/IP connections\."

**Possible solutions:**

 Generally, when you receive an error message indicating that there is a failure to establish a connection, it is an issue with permission to access the cluster\. 

 If you attempt to connect to the cluster from a client tool outside of the network that the cluster is in, you must add an ingress rule to the cluster security group for the CIDR/IP that you are connecting from: 

+ If you created your Amazon Redshift cluster in an Amazon Virtual Private Cloud \(Amazon VPC\), you need to add your client CIDR/IP address to the VPC security group in Amazon VPC\. For more information about configuring VPC security groups for your cluster, see [Managing Clusters in an Amazon Virtual Private Cloud \(VPC\)](managing-clusters-vpc.md)\.

+  If you created your Amazon Redshift cluster outside a VPC, you need to add your client CIDR/IP address to the cluster security group in Amazon Redshift\. For more information about configuring cluster security groups, see [Amazon Redshift Cluster Security Groups](working-with-security-groups.md)\.

 If you attempt to connect to the cluster from a client tool in an Amazon EC2 instance, you must add an ingress rule to the cluster security group for the Amazon EC2 security group that is associated with the Amazon EC2 instance\. For more information about configuring cluster security groups, see [Amazon Redshift Cluster Security Groups](working-with-security-groups.md)\. 

 Additionally, if you have a layer between your client and server, such as a firewall, make sure that the firewall accepts inbound connections over the port that you configured for your cluster\. 