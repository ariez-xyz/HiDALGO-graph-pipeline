# HiDALGO Graph Pipeline 

Unified tools for parallel clustering of large graphs.

## Architecture

The main Java program reads an execution plan from a file and runs it. For an example of an execution plan, see `data/`. Parts of the functionality are implemented in Python. IPC is implemented via a named pipe. The pipe name is deterministic, so running multiple instances in the same folder will get in each other's way. 

## Pipeline stages

### CutNeighborhoods

* Takes MetisFile
* Params: none
* Semantics: Create a separate graph out of the immediate neighborhood of each node

### ClusterNeighborhoods

* Params:
    * Threads: int, number of threads to use
* Semantics: Cluster neighborhoods using KIT's implementation of PLM

