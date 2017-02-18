# assignment-3.5
QN 1 Explain what is High availability of Namenode
In Hadoop 1.x there is a main disadvantage related to NameNode (ie) Single point of Failure(if name node fails there will  be some loss of data despite having a secondary node as the updation from name node to secondary name node is done on  hourly basis)
So we come with the solution of HIGH AVAILABILITY OF NODE 
In Hadoop 2.x we have two name node (other than secondary name)namely
1.Active NameNode
2.Standby NameNode
Now  the Data node will send block reports to both Active NameNode and Standby NameNode
So if active NameNode fails or crashes Stand By Name node becomes active NameNode
Then how do we know how Active NameNode fails  .So for that we have Journal Node 
This works on the Basis of polling so if there are 3 journal nodes formula for calculated quorom is
(no of journal node + 2)/2(suppose 3 journal node (3+2)/2 =2)) while the expected QUOROM here is 2.
If active name node fails the journal count quorom will be less than 2 and the journal node automatically changes the 
Stand by name node as active name node and when the failed name node gets up it will now be a standby and the process goes on 
 
