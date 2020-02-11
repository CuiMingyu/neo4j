# neo4j
Basic introduction of neo4j

## Content
* [Operation](#Operation)
* [Architecture](#Architecture)
* [cluster](#cluster)
* [Deployment](#Deployment)
* [Cypher](#Cypher)


Operation
------
    ./neo4j start 
    ./neo4j console
    ./neo4j stop
    ./neo4j status
    ./neo4j restart
    localhost:7474

Atchitecture
------
    Key Points: Native processing and Native graph storage.

##### Native processing
![image](https://github.com/CuiMingyu/neo4j/blob/master/image/TraditionalDB.jpg)
    In traditional database, they use many types of indexes to connect each node which is more costly.
![image](https://github.com/CuiMingyu/neo4j/blob/master/image/graphDB.jpg)
    In neo4j, if we want find friends of Alice, we only need to follow Alice's friend relationships. 
    While in traditional database, we need to perform a brute-force search.
##### Native graph storage
![image](https://github.com/CuiMingyu/neo4j/blob/master/image/storageStructure.jpg)
    In neo4j, different parts are stored in different parts. Nodes, relationships and properties are in different parts.
    The most important idea is every node or relationship or property is stored in a fixed size 
    which means each of them has a unique id number in order to be indexed.

Cluster
------
    Support Highly Avaliable and causal clustering 
    https://neo4j.com/docs/operations-manual/current/clustering/#cluster-installation

Deployment
------
    1. Select suitable JVM which can compatiable with Neo4j 
    2. Add Envrionment Variants
    3. cd /bin Using basic commands to start it

Cypher
------
    1. match(n) return n
    2. match(p:Person{name:'Bob'}), (p1:Person{name:'Jack'}) 
    create (p)-[r:FOLLOWS]->(p1)
    3. match(n) where id(n)= 1 return n
    ...
