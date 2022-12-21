# Outline
1. Foundations of Data Systems
	a. Overview
		- Reliability
		- Scalability
		- Maintainability
	1. Data Models & Query Languages
1. Storage Engines
2. Data Encoding Formats (Serialization)

## II. Distributed Systems
1. Replication
2. Partitioning/Sharding
3. Transactions
4. Detailed Problems
5. Consistency/Consensus

## III. Derived Datasets
1. Batch Processing
2. Stream Processing
3. Putting Everything Together

> **Side Note**
> Common Wisdom (Page 18):
> Horizontally Scale an Application
> Vertically Scale a Database (Single Node)

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

**Keywords**
*faults, fault-tolerant, resilient, failure, Chaos Monkey, rolling upgrades, sandbox, telemetry*

### Scalability
- Describing Load
- Measuring Performance
- Coping with Load

**Keywords**
*load parameters, throughput, response time, distribution, outliers, arithmetic mean, percentiles, median, 50th percentile, tail latencies, service level objectives, service level agreements, head-of-line blocking, tail latency amplification, shared-nothing, elastic, magic scaling sauce*

### Maintainability
- Operability
- Simplicity
- Evolvability

**Keywords**
