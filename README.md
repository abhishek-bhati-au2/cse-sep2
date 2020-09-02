# cse-sep2

Q1) .What is Cryptography and what are the Encryption Methods? 

Ans1→) The prefix “crypt” means “hidden” and the suffix graphy means “writing”.So generally it means hidden writing. Now, let’s modify this statement according to the IT purpose.
Cryptography  is the technique of securing information and communications through use of codes so that only those person for whom the information is intended can understand it and process it. Thus preventing unauthorized access to information.

Cryptography involves various techniques and technologies including algorithms, mathematics, information theories, transmission, encryption etc. Encryption is one such technique of Cryptography. A standalone, Encryption process can provide the message in a confidential way, but at the same time, other techniques and strategies are required to provide the integrity and authenticity of a message. So, in a nutshell, a successful scheme should provide data integrity, authentication, and non-repudiation, which is what Cryptography provides.

Basically there are three types of cryptography:-

 1.Secret Key Cryptography (SKC): Uses a single key for both encryption and decryption; also called symmetric encryption. Primarily used for privacy and confidentiality.

 2. Public Key Cryptography (PKC): Uses one key for encryption and another for decryption; also called asymmetric encryption. Primarily used for authentication, non-repudiation,       and key exchange.
 
 3. Hash Functions: Uses a mathematical transformation to irreversibly "encrypt" information, providing a digital fingerprint. Primarily used for message integrity.
 
  Q3)How will you create persistent connections between the server and the client? 

Ans 3)→ A persistent connection (HTTP persistent connection) is a network communication channel that remains open for further HTTP requests and responses rather than closing     after a single exchange.
HTTP has a persistent connection function that allows the channel to remain open rather than be closed after a requested exchange of data. TCP is a connection-oriented protocol: It starts a connection after confirmation from both ends that they are available and open to a data exchange. In a non-persistent connection, the channel closes when one host signals that it wants to end communications or when a certain amount of time has elapsed with no exchange of data. To maintain a persistent connection, TCP keep-alive packets are sent to prevent the connection from timing out.
 An open connection is faster for frequent data exchanges. Communications overhead is saved by leaving a connection open rather than opening and closing sessions for each request. Persistent connections can also be used with APIs to enable servers to push data to clients. Other benefits of persistent connections include reduced network congestion, latency and CPU and memory usage due to the lower number of connections; errors can also be reported without closing the connection.Persistent connections are also called HTTP keep-alive or HTTP connection reuse.
 
 Q4) What is Multithreading? What is the difference between a thread and a process?

Ans 4→)  Say you have a road with one lane. You can only send so many cars, in order, and at a certain speed. The speed of the cars is the speed of the processor.
Now say you have a road with 4 lanes. Now, you can send more cars down at the same time, and at various speeds because the huge truck is blocking only one lane of four.
In programming, multi threading allows a program to run multiple tasks concurrently which is very useful for heavy data processing or tasks which rely on external factors, such as slower storage or internet services. It also helps user experience as you can run the UI on one thread, along with simple tasks like showing forms, loading/saving settings etc, while your heavier tasks like queying a database are run on other threads.
When the UI has to wait for any slow task, the UI will appear to hang as it can't process any further commands until the task it is waiting for has fiinished. A multi threaded application doesn't have this problem because it runs the slow tasks on separate threads, independent of the UI thread.
Multi threading does have drawbacks. I would say the main one is coming across something called a race condition. A race condition happens when multiple tasks are running and one of them finishes and updates data state before it's expected. This is also true of database apps where one task might modify a record before another task, even though the second task was started before the first one. This means the data is now inconsistent - especially if the data is supposed to be sequential. Another type of race conditon is when a task updates a variable while another task is running. The program state has now changed, but the still running task is unaware of this which can cause a crash if the task relies on this data.
Multi threading is one of the best ways to immediately make an improvement in performance for concurrent tasks, but it also requires careful consideration during the design phase so that the program doesn't make itself crash.



The primary difference is that threads within the same process run in a shared memory space, while processes run in separate memory spaces.
Threads are not independent of one another like processes are, and as a result threads share with other threads their code section, data section, and OS resources (like open files and signals). But, like process, a thread has its own program counter (PC), register set, and stack space.

Q5) Explain Indexing in DBMS. 

Ans 5)→ Indexing is a data structure technique to efficiently retrieve records from the database files based on some attributes on which the indexing has been done. Indexing in database systems is similar to what we see in books.
Indexing is defined based on its indexing attributes. Indexing can be of the following types −
Primary Index − Primary index is defined on an ordered data file. The data file is ordered on a key field. The key field is generally the primary key of the relation.
Secondary Index − Secondary index may be generated from a field which is a candidate key and has a unique value in every record, or a non-key with duplicate values.
Clustering Index − Clustering index is defined on an ordered data file. The data file is ordered on a non-key field.
Ordered Indexing is of two types −
Dense Index
Sparse Index
Dense Index
In dense index, there is an index record for every search key value in the database. This makes searching faster but requires more space to store index records itself. Index records contain search key value and a pointer to the actual record on the disk.

Sparse Index
In sparse index, index records are not created for every search key. An index record here contains a search key and an actual pointer to the data on the disk. To search a record, we first proceed by index record and reach at the actual location of the data. If the data we are looking for is not where we directly reach by following the index, then the system starts sequential search until the desired data is found.

Multilevel Index
Index records comprise search-key values and data pointers. Multilevel index is stored on the disk along with the actual database files. As the size of the database grows, so does the size of the indices. There is an immense need to keep the index records in the main memory so as to speed up the search operations. If single-level index is used, then a large size index cannot be kept in memory which leads to multiple disk accesses.


Q6)  What are normalization and denormalization and why do we need it? 

Ans 6)->Normalization:
Normalization is the method used in a database to reduce the data redundancy and data inconsistency from the table. It is the technique in which Non-redundancy and consistency data are stored in the set schema. By using normalization the number of tables is increased instead of decreased. It is used in OLTP system, where the emphasize is on making the insert, delete and update anomalies faster and storing the quality data.
 
 
Denormalization:
Denormalization is also the method which is used in a database. It is used to add the redundancy to execute the query quickly. It is a technique in which data are combined to execute the query quickly. By using denormalization the number of tables is decreased which oppose to the normalization. It is used in OLAP system, where the emphasis is on making the search and analysis faster.
 
Conclusion
Normalization and denormalization are useful according to the situation. Normalization is used when the faster insertion, deletion and update anomalies, and data consistency are necessarily required. On the other hand, Denormalization is used when the faster search is more important and to optimize the read performance. It also lessens the overheads created by over-normalized data or complicated table joins.
 
 Q7) Difference between INNER and OUTER JOIN.

Joins in SQL are used to combine the contents of different tables. You can specify how you want the data from tables to be joined in many ways, one of which is the type of join. There are four main types of joins: inner join, full outer join, left outer join and right outer join.
The major difference between inner and outer joins is that inner joins result in the intersection of two tables, whereas outer joins result in the union of two tables.
Inner Join
An inner join focuses on the commonality between two tables. When using an inner join, there must be at least some matching data between two (or more) tables that are being compared. An inner join searches tables for matching or overlapping data. Upon finding it, the inner join combines and returns the information into one new table.
 
Example of Inner Join
Let's consider a common scenario of two tables: product prices and quantities. The common information in the two tables is product name, so that is the logical column to join the tables on. There are some products that are common in the two tables; others are unique to one of the tables and don't have a match in the other table.
An inner join on Products returns information about only those products that are common in both tables.

Outer Join
An outer join returns a set of records (or rows) that include what an inner join would return but also includes other rows for which no corresponding match is found in the other table.
There are three types of outer joins:
Left Outer Join (or Left Join)
Right Outer Join (or Right Join)
Full Outer Join (or Full Join)
Each of these outer joins refers to the part of the data that is being compared, combined, and returned. Sometimes nulls will be produced in this process as some data is shared while other data is not.

Left Outer Join
A left outer join will return all the data in Table 1 and all the shared data (so, the inner part of the Venn diagram example), but only corresponding data from Table 2, which is the right join.
Left Join Example
In our example database, there are two products — oranges and tomatoes — on the 'left' (Prices table) that do not have a corresponding entry on the 'right' (Quantities table). In a left join, these rows are included in the result set with a NULL in the Quantity column. The other rows in the result are the same as the inner join.
 
Right Outer Join
A right outer join returns Table 2's data and all the shared data, but only corresponding data from Table 1, which is the left join.
Right Join Example
Similar to the left join example, the output of a right outer join includes all rows of the inner join and two rows — broccoli and squash — from the 'right' (Quantities table) that do not have matching entries on the left.

Full Outer Join
A full outer join, or full join, which is not supported by the popular MySQL database management system, combines and returns all data from two or more tables, regardless of whether there is shared information. Think of a full join as simply duplicating all the specified information, but in one table, rather than multiple tables. Where matching data is missing, nulls will be produced.
 
 
 Q10) If RAM size is 4GB, if 4 processes of size 2GB are launched! What happens?

Ans 10)→ Virtual memory (transferring from physical RAM to the hard disk) theoretically allows processes to take as much memory as they want (within the limit of the hard disk obviously).

However, since disk access is many orders of magnitude slower than RAM access, the more of the process can live in RAM the better.

Also, virtual memory only really works well as long as there is a pattern to data access. If things keep having to get written out to disk after every access (because they are not in RAM) then performance is catastrophic.

 





