# ELASTICACHE

You can use ElastiCache for caching, which accelerates application and database performance, or as a primary data store for use cases that don't require durability like session stores, gaming leaderboards, streaming, and analytics. ElastiCache is compatible with Redis and Memcached.

## CLUSTER : 

A group of two or more computers, or nodes, that run in parallel to achieve a common goal. This allows workloads consisting of a high number of individual, parallelizable tasks to be distributed among the nodes in the cluster.

## MEMCACHED CLUSTER : 

Memcached is a general-purpose distributed memory-caching system. It is often used to speed up dynamic database-driven websites by caching data and objects in RAM to reduce the number of times an external data source (such as a database or API) must be read. Amazon ElastiCache for Memcached is available in multiple AWS Regions around the world. Thus, you can launch ElastiCache clusters in the locations that meet your business requirements. For example, you can launch in the AWS Region closest to your customers or to meet certain legal requirements.
The default Memcached port is 11211. ElastiCache uses that subnet group to choose a subnet and IP addresses within that subnet to associate with your nodes.

## Endpoint
An endpoint is the URL of the entry point for an AWS web service. The AWS SDKs and the AWS Command Line Interface (AWS CLI) automatically use the default endpoint for each service in an AWS Region. But you can specify an alternate endpoint for your API requests.
If a service supports Regions, the resources in each Region are independent of similar resources in other Regions. 

## CREATING MEMCACHED CLUSTER AND ENDPOINT

To launch a Memcached instance. Open the AWS Console and search for 'ElastiCache'.In the ElastiCache dashboard, click ‘Get Started Now’ and select Memcached. Enter the name 'myMemcached', and select the node type. Select the engine version, the port(default 11211) and the security group. 

![Image](https://d1.awsstatic.com/elasticache/WordPressWithMemcached/ElastiCacheSetupRB.dd5224d0b40f6d9a81aa4f5b51f8baa59e77c63c.png)

Finish the setup by selecting create memcached cluster.

After a few minutes the cluster status will become 'Available'.

Make a note of the Configuration Endpoint 

    Example : memcache01.gw0puo.cfg.aps1.cache.amazonaws.com:11211

![image](https://d1.awsstatic.com/elasticache/WordPressWithMemcached/ElastiCacheRunningRB.99eb656e5c6b1d0c2cd1702e43943a348f384da2.png)


## Validating a memcached connection

For steps to validate the connection to a linux server, install telnet or netcat in the server.
   
   $ yum install telnet (or)
    $ yum install nc
    
Initiate a connection between the server(terminal) and the memcached cluster using the configuration endpoint of the memcached cluster

    $ telnet [configuration endpoint] (port number)       (or)
    $ nc [configuration endpoint] (port number)
    
The connection if established, can be verified if the following lines are displayed

    Trying [node-ip-address]
    Connected to [node-ip-address]
    
    
## Telnet commands :

- stats - shows numerous statistics about Memcached server
- set - creates Memcached a key / value combination
- get - retrieves a Memcached key
- flush_all - deletes all keys
- Ctrl + ] - to exit telnet


## Deleting a memcached service

- Select the cluster to be delete in the memcached cluster dashboard.
- For Actions, choose Delete.
- In the Delete Cluster confirmation screen, choose Delete to delete the cluster, or Cancel to keep the cluster.
- If you choose Delete, the status of the cluster changes to deleting.
- As soon as your cluster is no longer listed in the list of clusters, the cluster is deleted.


## Note : You can only delete one cluster at a time from the ElastiCache console. Selecting multiple clusters disables the delete operation. To delete multiple clusters, repeat this process for each cluster.

------------------------------------------------------------------------------------------------------------------------------------------------------------------













