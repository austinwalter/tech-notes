# Outline
1. Foundations of Data Systems
	1. Overview
		- Reliability
		- Scalability
		- Maintainability
	2. Data Models & Query Languages
	3. Storage Engines
	4. Data Encoding Formats (Serialization)
2. Distributed Systems
	1. Replication
	2. Partitioning/Sharding
	3. Transactions
	4. Detailed Problems
	5. Consistency/Consensus
3. Derived Datasets
	1. Batch Processing
	2. Stream Processing
	3. Putting Everything Together

# I. Foundations of Data Systems

## Overview

- Three Main System Concerns
	- Reliability
	- Scalability
	- Maintainability 
- Types of Data Systems
	- Databases
	- Caches
	- Search Indexes
	- Stream Processing
	- Batch Processing

### Reliability
- Hardware Faults
- Software Errors
- Human Errors

> **Keywords**
> *faults, fault-tolerant, resilient, failure, Chaos Monkey, rolling upgrades, sandbox, telemetry*

### Scalability
- Describing Load
- Measuring Performance
- Coping with Load

> **Side Note**
> Common Wisdom: Until really necessary for costs or requirements, keep your database on a single node and scale it vertically, and scale your application horizontally.

> **Keywords**
> *load parameters, throughput, response time, distribution, outliers, arithmetic mean, percentiles, median, 50th percentile, tail latencies, service level objectives, service level agreements, head-of-line blocking, tail latency amplification, shared-nothing, elastic, magic scaling sauce*

### Maintainability
- Operability
- Simplicity
- Evolvability

> **Keywords**

___

## Data Models & Query Languages
## Storage Engines
## Data Encoding Formats (Serialization)

# II. Distributed Systems

## Replication
## Partitioning/Sharding
## Transactions
## Detailed Problems
## Consistency/Consensus

# III. Derived Datasets

## Batch Processing
## Stream Processing
## Putting Everything Together