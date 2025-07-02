# Understanding Kafka – Distributed Event Streaming

## Origin Story

- Developed at **LinkedIn** to handle high‑throughput, low‑latency activity streams.
- Open‑sourced → became **Apache Kafka** (named after author Franz Kafka).
- First public release 2011; now top‑level Apache project.

## Basic Kafka Flow

1. **Producer sends message**
   - Application acts as *producer*, builds record (payload + optional key).
   - Sends to a **broker** & chosen **topic**.
   - **Partitioner** decides which partition gets it (load‑balancing).
2. **Message stored & replicated**
   - Partition leader appends to its log.
   - Record gets a unique **offset** (immutable).
   - Leader replicates to follower replicas (fault‑tolerance).
3. **Consumer fetches messages**
   - Application joins a **consumer group**.
   - Consumers share offsets; each partition assigned to one consumer at a time.
   - Batches pulled & processed.
4. **Acknowledging consumption**
   - Consumer commits new offset after processing.
   - Kafka records committed offsets per consumer group.
5. **Flow continues**
   - Producers keep publishing; consumers keep polling based on latest offsets.
   - Ordered delivery within partition; durable even across failures.

## Key Concepts

| Term                | Description                                   |
|---------------------|-----------------------------------------------|
| **Topic**           | Named feed to which records are written       |
| **Partition**       | Ordered, immutable sequence of records        |
| **Offset**          | 0‑based index within a partition              |
| **Broker**          | Kafka server; a cluster hosts many brokers    |
| **ZooKeeper / KRaft** | Metadata quorum (KRaft = built‑in Raft since 3.3) |
| **Producer**        | Client that publishes records                 |
| **Consumer**        | Client that reads records                     |
