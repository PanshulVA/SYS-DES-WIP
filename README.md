# SYSTEM DESIGN

## BASICS
1) Try to break the problem into simpler modules
(Top Down Approach)
2) Talk about trade-offs
(No solution is prefect)
Calculate the impact on system based on all the constraints and the end test cases. Scoping the problem is the most important after which comes abstract design and lastly finding and addressing bottlenecks.
3) Rationalize ideas and inputs
4) Utilization and trade-offs  
a. Consistent Hashing  
b. CAP theorem  
c. Load Balancing  
d. Queues  
e. Caching  
f. Replication  
g. SQL vs NO-SQL  
h. Indexes  
i. Proxies  
j. Data Partitioning  

## Load Balancing
### There are 3 types of distributions 
1 Random  
2 Round-Robin  
3 Random (weights for memory & CPU cycles)  

### To utilise full scalability & redundancy, add 3 LB

1) Between User and Web server
2) Between Web server and App/ Cache server
3) Betweem Internal platform and Database

## Smart Clients
Takes a pool of service hosts & balances load.  
--> Detects hosts that are not responsive  
--> recovered hosts  
--> addition of new hosts  
### Hardware Load Balancers:  
Expensive but high performance and easy to configure but large companies avoid this config or use it as 1st point of contact.

### Software Load Balancers  
No pain of creation of smart client and no cost of purchasing hardware.


## World of DATABASES

### SQL vs NOSQL
| SQL                                                    | NOSQL                                                    |
|--------------------------------------------------------|----------------------------------------------------------|
| Relational Database                                    | Non-Relational Database                                  |
| Structured                                             | Unstructured                                             |
| Predeifned Schema                                      | Dynamic Schema                                           |
| Data in rows & colums                                  | Distributed                                              |
| EG. MySQL Oracle MS SQL server SQLite Postgres MaraiDB | EG> Key-Value Stores Document DB Wide-column DB Graph DB |


### NOSQL
1) Key-Value Store:  
Data => array of key value pair
Key=> Attribute linked to value
eg. Redis  
Voldemart  
Dynamo  
2) Document DB  
Data => Do0cuments goruped into => collections
**Each doc can be different**
eg. CouchDB  
MongoDB  
3) Wide-Column DB  
Instead of tables, column families which is container for rows
** No need of knowing all columns upfront.  
Each row => Different number of columns**  
Analysis of large datasets
eg. Cassandra  
HBase  
4) Graph DB  
Data whose relations are best represented in Graphs
==> Nodes (Entities)
==> Properties (Information of entities)
==> Lines (Collection of Properties)
eg. Neo4J  
InfiniteGraph  
  
  
### Reason for using SQL
1) You need to ensure ACID Compliance:  
ACID Complaice  
  ==> Reduces Anomalies  
  ==> Protects integrity of the database  
for many E- commerce & financial applications ACID Complaint Database is the first choice.

2) Your data is structured & unchanging.  
If your business is not experiencing rapid growth or sudden changes  
----> No requiremnets of more servers  
----> Data is consistent  
Then there is no reason to use system design to support variety of data and high traffic  
  
  
  
 ## Reasons to use NOSQL DB  
1) When all other components of system are fast querying and searching for data becomes a bottleneck  
----->NOSQL prevent data from being bottleneck  
  

    **BIG DATA IS A LARGE SUCCESS FOR NOSQL**  
  

2) To store large volumes of data with little to no structure  
There's no limit on type of data  


    **Document DB as an example stores all data in one place with no need of type of data to be specified**  
  
  
  
3) Using Cloud and Storage to the fullest makes it an excellent cost saving solution.
There's an easy spread of data across multiple servers to scale up  
OR we can buy hardware on site ( affordable and smaller) with no headache of additional software  
  
    **NOSQL Databases like Cassandra are designed to scale across multiple data centres out of the box**   
  
  
4) NOSQL Is useful for rapid/agile development  
If you're making quick iterations on schema SQL **will** slow you down  



## CAP THEOREM
**CONSISTENCY:** Acheived by updating several nodes beofre allowing read (ALL NODES SEE SAME DATA AT THE SAME TIME).  


**AVAILABILITY:** Every request gets response (sucess/failure) acheived by replicating data across different server.  

**PARTITION TOLERANCE:** System continues to work despite message loss or partial failure. It can sustain any amount of network failure without resulting in failure of entire network. Data is sufficiently replicated across combinationof nodes or networks to keep the system up.



**It is impossible for a distributed system to simultaneously provide more than two of three of the above guarantess**



**We cannot build a datastore which is:**  
**1) Continually available**  
**2) Sequentially consistent**  
**3) Partition failure tolerant**  
 
