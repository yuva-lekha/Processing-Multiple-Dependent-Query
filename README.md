# Processing-Multiple-Dependent-Query
PROBLEM STATEMENT

Paralleization of queries to improve dbms performance and to reduce waiting 
time for query execution. Currently a thread based DAG scheduler has been 
coded to acheive the parallel execution of queries. Every query is threaded to 
and executed in the DB. Since few queries are dependent (try and access same 
columns of the DBMS). We have implemented a Mutual lock based thread 
algorithm. Still there is a need to priotorize queries to avoid any Raw Hazard.
An algorithm is needed to priorotize waiting queries. All non dependant queries
gets executed parallely. Kindly consider the following commands for testing the
algorithm.

Select Queries - Reading the records from DB .
Update Queries - Updating the records from DB.
Insert Queries – Inserting into the records from DB.
Delete Queries – Droping the tables from DB.
Modification Queries - Adding & deleting columns in a table from DB

Conditions:
Conditions are as follows:
1. The database state should be consistent at any instance of the time.
2. All non dependant queries must not wait for any queries.
3. No two dependant queries should execute at the same time.
4. Algorithm should ensure minimum waiting time for dependant queries

Solution was given in ppt file :
explanation :
consider you have columns say c1 , c2 , c3
queries are               q1:  1   0    0                   1: dependent on that column    0 : independent on that column
                          q2 : 0   0    1
                          q3 : 1   0    1
                          q4  :0   1    0
we used concept of bucket : gathering in queries together and working them together. 
example : q1 , q2 , q4 can execute concurrently


