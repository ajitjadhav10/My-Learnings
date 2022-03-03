#### it is the largest open source data processing project

- It breaks a large task into smaller ones between different machines

- Spark is known for 'parallelism' 
- Each parallel action is know a **Job**
- each job is divided into **stages**(which are a set of ordered steps which together make a job)
- Each stage can have multiple **tasks** which process the assigned 


- Spark uses a cluster of computers to process data

Spark cluster-
Driver: 
1. It consists if a **Driver** : It is the machines on which the application runs.
2. It has 3 main tasks:
    a. maintaning information about the spark application
    b. responding to the user program
    c. scheduling and distributing work across the cluster
    

Worker:
1. It hosts the executor process.
2. It has a fixed number of executors at any point of time.

Executors;
1. Each executor has a part of the data to be processed(spark partition)
2. Executor has two main responsibilities: executing the task assigned by the driver and returning the result back to the driver
3. Each executor has some slots, each slot can be assigned a task.
    
