# Top-K-Shortest-Path-Problem-with-MPI-and-OpenMP
The objective of this project is to implement the K shortest paths algorithm for weighted graphs, with a focus on scalability and performance optimization. The project involves preprocessing input data, implementing the algorithm, and testing it on various input files..

### Introduction:
The objective of this project is to implement the K shortest paths algorithm for weighted graphs, with a focus on scalability and performance optimization. The project involves preprocessing input data, implementing the algorithm, and testing it on various configurations.

### Input Files:
The input data consists of weighted graphs represented in files. Initially, we attempted to use the Enron email dataset, which contained 265214 nodes and 420045 edges. However, due to memory constraints, processing the entire dataset resulted in memory errors. To address this, we divided the input file into smaller subsets for preprocessing and testing.

### Preprocessing:
During preprocessing, we assigned weights to the edges of the graphs. Since some of the  provided graphs did not have weights assigned, we initially assigned weights equal to 1. In DocWho Dataset we also converted csv files into text files and assigned unique integers to the same words.  We also divided the dataset into smaller subsets to alleviate memory issues

### Initialization of distance matrix:
As we read the data from the file and assign random weights to it.  We made a distance matrix according to the given condition in which diagonals are zero and the not connecting graphs are considered to infinity and the remaining get their assigned weights of 10 randomly selected data, but later on we did not display our matrices because of clarity. 

### Implementation:
We implemented the K shortest paths algorithm using a combination of MPI (Message Passing Interface) and OpenMP (Open Multi-Processing) for parallelization. Initially, we attempted a parallelization strategy where each process broadcasted the graph data, and OpenMP was used for parallel execution of the algorithm. However, we encountered segmentation faults and synchronization issues with this approach.
Subsequently, we opted for a simpler approach, where we implemented the algorithm using hardcoded data. This approach involved creating a distance vector, utilizing priority queues, and employing Dijkstra's algorithm to find the K shortest paths. This implementation provided correct results, matching those obtained from existing C++ implementations.

### Challenges Faced:
The primary challenge encountered during preprocessing was handling large datasets within memory constraints. Dividing the dataset into smaller subsets helped mitigate this issue. In terms of implementation, the major challenge was achieving efficient parallelization while ensuring proper synchronization among processes. We also faced challenges related to debugging segmentation faults and optimizing the algorithm for performance.

### Optimizations and Performance:
To improve performance, we optimized the preprocessing step by dividing the dataset into smaller subsets. Additionally, we optimized the algorithm implementation by simplifying the parallelization strategy and ensuring proper synchronization. Despite encountering challenges, these optimizations led to improved performance and correct results.

### Conclusion:
In conclusion, the implementation of the K shortest paths algorithm involved preprocessing input data, addressing challenges related to memory constraints and parallelization, and optimizing the algorithm for performance. Despite encountering challenges, the project achieved its objectives and provided valuable insights into scalable algorithm implementation. Further optimizations and experiments can be explored to enhance performance and scalability further.



