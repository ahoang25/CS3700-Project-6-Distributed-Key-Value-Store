# Andrew Hoang

# Project 6 - Distributed Key-Value Database

## High Level Approach
This project implements a simple distributed key-value store using the Raft consensus protocol. The key objectives were to ensure data consistency and fault tolerance across a cluster of replicas. The main functionalities include handling `get` and `put` operations, managing elections, and log replication to ensure strong consistency.


## Challenges Faced
- Network Unreliability: Simulating an unreliable network environment and ensuring the system could handle message loss, delays, and network partitions was challenging.
- Concurrency: Managing the concurrent operations without causing race conditions or deadlocks, especially during leader election and log replication.
- State Management: Ensuring all replicas maintain a consistent state across various edge cases, such as leader failover, was complex.


## Features of the Design
- Robust Leader Election: Through Raft's election protocol, the system can quickly elect a new leader in case of the current leader's failure.
- Log Replication: Ensures all committed entries are consistently replicated across all replicas, even in the face of network failures.
- **Fault Tolerance**: The system can handle the crash of several replicas without losing data integrity or availability.
- Scalability: New replicas can be easily added to the system, enhancing the fault tolerance and load capacity of the store.

## Testing Overviw
We used a course-provided simulator to mimic client interactions and network conditions. Testing focused on observing replica behaviors, verifying accurate implementation of the Raft protocol, and confirming the system's resilience to simulated network disruptions.
