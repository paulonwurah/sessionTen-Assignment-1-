# sessionTen-Assignment-1-

1.	When running Spark in Yarn, do you need to install spark on all nodes of Yarn Cluster? No you don’t need to. However, spark assembly jar can be added to HDFS

2.	Explain the life cycle of a Spark program
Right from the client machine, a code is created which is known as the driver code. What it does is that it performs operations on the data that is to be worked on.  In the code, a spark context is initiated which is a bridge to connect the code to the cluster. Spark context is the main entity responsible for setting up a job. A driver which is the machine where the spark context is initialized runs a driver process when it wants to perform a job. When a driver process needs resources to run a job, it connects to the spark master and then the master to the cluster manager. Then cluster manager will allocate the resources to the workers. These resources are called executors which is where the program will run. This information is what the client machine will use to copy the code as tasks to the executors (data locality) for processing of the data.

3.	What are transformations and actions? What is the difference between them in terms of execution?
Transformations are operations that produce another RDD when it acts on an RDD. In order words, it an intermediary RDD creator which still needs an action for the final output. Examples include map, flatMap. In terms of execution, transformation is lazy in its evaluation. That is why most white papers often refer to multiple transformations as a map outline for an action. 
On the contrary, actions do not create another RDD when it acts on another RDD. Instead, it produces an output. Examples include count, collect, take. In terms of execution, an action evaluates all the transformation that has been created and produces and output. 

4.	In what scenario can spark be used more?  
Spark can be used more in various scenarios because of its ability to perform processing with various libraries such as streaming and machine learning libraries. In spark-streaming, spark can perform processing in real-time and can also do iterative processing (machine learning) well. 

5.	What makes Spark 10-100x times faster than Hadoop?  
The major thing that makes spark 10-100x faster is its in-memory caching abstraction. This makes Spark ideal for workloads with multiple operations access the same input data. Users can instruct Spark to cache input data sets in memory, so they don’t need to be read from disk for each operation. 

