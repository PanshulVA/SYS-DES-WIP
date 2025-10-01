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
