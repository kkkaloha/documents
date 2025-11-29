# COMP7104 DATABASE SYSTEMS EXAM CHEATSHEET

## 2023-2024 EXAM

**Q1.1** Join algorithms: (A) PNLJ order matters if both fit in memory - FALSE; (B) Use smaller as inner if one fits - TRUE; (C) INLJ choice based on table sizes - FALSE
**Q1.2** System R: (A) Never cartesian products - FALSE; (B) Only right-deep - FALSE; (C) Keeps interesting orders - TRUE
**Q1.3** Left-deep plans: (A) Same output - TRUE; (B) Different access method - TRUE; (C) Different join method - TRUE
**Q1.4** NOT good optimization: (B) Push projection below right inner CNLJ
**Q1.5** Pipeline breaker: (B) Sort Merge Join; (C) Grace Hash Join
**Q1.6** Selectivity: (A) Independence; (B) Uniform distribution in histograms
**Q1.7** Transactions: (A) Serial ⇒ serializable - TRUE; (B) Interleaving faster - FALSE; (C) Conflict-serializable ⇒ recoverable - FALSE
**Q1.8** 2PL/Strict2PL: All TRUE
**Q1.9** 2PL properties: (A) Some conflict-serializable missed - TRUE; (B) Acyclic graph iff conflict-serializable - TRUE; (C) Both enforce conflict serializability - TRUE
**Q1.10** PDBMS: (A) Round-robin lookup higher cost - TRUE; (B) Range better than hash - FALSE; (C) Symmetric shuffle fewer IOs - FALSE
**Q1.11** Hash partition scan: Constant (bottleneck at popular value machine)
**Q1.12** PDBMS partitioning: (A) Round-robin broadcast - TRUE; (B) Range only balanced - FALSE; (C) Round-robin balanced - TRUE
**Q1.13** PDBMS evaluation: (A) Pipeline scales to depth - FALSE; (B) Partition scales with data - TRUE; (C) Pipeline scales to depth - TRUE
**Q1.14** Grace Hash Join: (A) No extra disk IO for repartition - TRUE; (B) Data skew problem regardless - FALSE; (C) Different agg locally/globally - FALSE
**Q1.15** NoSQL replication: (B) Recover from failures - TRUE; (C) Workload scalability - TRUE
**Q1.16** NoSQL: (A) High simple read-write - FALSE

**Q2.1** CNLJ: (a) 2,500×2,500 + 2,500 = 6,250,500 IOs; (b) 1,500 + 1,500×(750-2)=1,123,500 IOs; (c) 600 + 600×(750-2)=449,400 IOs

**Q2.2** Sort-Merge: (d) 10,000 IOs (2 passes); (e) 6,000 IOs (2 passes); (f) 3,750,000 IOs; (g) 4,000 IOs; (h) 2,000 IOs

**Q2.3** Grace Hash: (a) Partition 1 pass, cost 4,200 IOs; (b) 474 IOs; (c) 2 passes; (d) 962 IOs

**Q2.4** Selectivity: (a) 1/1000; (b) 1/1000; (c) 0.45; (d) 1450/7250≈0.2

**Q2.5** Lock manager: Track granted locks and queues per transaction-resource pair

**Q2.6** Concurrency: (a) No cycle → NOT conflict-serializable FALSE; (b) 2PL allows this - FALSE

**Q2.7** PDBMS: (a) 528 KB; (b) 396 KB; (c) 480 ms; (d) Broadcast join; (e) 64 KB

**Q2.8** Query optimization: (a) 1/25000; (b) 1/500; (c) 4/11; (d) 139/1300

---

## 2024-2025 EXAM

**Q1.1** Join: (A) BNLJ ≥ PNLJ - TRUE; (B) Smaller as outer - FALSE; (C) Two indexes, query larger - TRUE
**Q1.2** SNLJ same pages, different density: (C) Same IOs
**Q1.3** Nested loops: (A) Both fit, order doesn't matter - TRUE; (B) Per-block better - TRUE; (C) Use hash not sort - TRUE
**Q1.4** Nested loop sorted: (B) Outer table sorted
**Q1.5** Index join algorithm: All TRUE
**Q1.6** Not pipeline breakers: (A) INLJ; (B) CNLJ
**Q1.7** System R: (A) May include cartesian - TRUE; (B) Always pipelined - FALSE; (C) Only cheapest - FALSE
**Q1.8** System R: (A) Optimal guarantee - FALSE; (B) Pushdown always better - FALSE; (C) Top-down - FALSE
**Q1.9** Histograms: (A) Equi-width - TRUE; (B) Equi-depth - TRUE; (C) Uniformity assumption - TRUE
**Q1.10** Locking: (A) No cascading aborts Strict2PL - FALSE; (B) 2PL → conflict-serializable - TRUE; (C) Acyclic Strict2PL - TRUE
**Q1.11** Schedules: (A) Dirty reads in conflict-serializable - TRUE; (B) Lost updates - FALSE; (C) Cascading aborts - TRUE
**Q1.12** PDBMS: (A) Shared-disk independent scale - TRUE; (B) Shared-memory closest - TRUE; (C) Shared-nothing easier scale - FALSE
**Q1.13** PDBMS: (A) Round-robin insertion higher - TRUE; (B) Round-robin better than hash - FALSE; (C) Range better than round-robin - TRUE
**Q1.14** NoSQL replication: (A) Multiple nodes - FALSE; (B) Latency - TRUE; (C) DB sizes - FALSE
**Q1.15** NoSQL: (A) High read-write - TRUE; (B) Replication for scalability - FALSE; (C) Transactional - TRUE

**Q2.1** Grace Hash with rehashing: YES, that's Grace-Hash Join

**Q2.2** Join 40K pages + 25 pages: Naive in-memory = 425 IOs

**Q2.3** Cardinality: (a) 1.5; (b) Underestimate (correlation)

**Q2.4** Serializability: (a) Not serial; (b) Dependency graph; (c) Has cycles → NOT conflict-serializable

**Q2.5** Deadlock avoidance: Wait-Die/Wound-Wait protocols

**Q2.6** Schedule: Not conflict-serializable, not possible under 2PL

**Q2.7** Selectivity: Multiple predicate queries with formula calculations

**Q2.8** PDBMS 4-way join: Replicate small tables, partition large on join key, 165 pages transfer

---

## 2022-2023 EXAM

**Q1.1** Storage: (A) Flash predictability - TRUE; (B) Locality for SSD - FALSE; (C) Write > Read for SSD - FALSE
**Q1.2** Storage/Indexing: (A) SSD for reads - TRUE; (B) Pointers omit - FALSE; (C) Adapt to latency - TRUE
**Q1.3** Storage: (A) One block-addressable - FALSE; (B) 8KB read - FALSE; (C) Random position - TRUE
**Q1.4** Paginated files: (A) Log-structured for read-mostly - FALSE; (B) Directory scan near full - FALSE; (C) Chained-lists lookup - FALSE
**Q1.5** Pages: (A) Bitmap varies - FALSE; (B) Fragmentation no ID change - TRUE; (C) Slot > Bitmap space - TRUE
**Q1.6** Record footer: All FALSE (use header)
**Q1.7** Alt 3 indexes: (B) Exactly 1
**Q1.8** B-tree: (A) Leaf unordered - TRUE; (B) Search invariant fails - TRUE; (C) Rebalance - FALSE
**Q1.9** Unclustered B-tree: (A) Random reads per record - TRUE; (B) Few matches unclustered better - TRUE; (C) SSD always unclustered - FALSE
**Q1.10** Buffer: (A) LRU floods - TRUE; (B) Clock faster - TRUE; (C) MRU cost - TRUE
**Q1.11** External sort: (A) Different hash hp vs hr - TRUE; (B) De-dup by sort/hash - TRUE; (C) Permutation sorted - FALSE
**Q1.12** Sort 5M pages, B=6: (A) 10 passes - TRUE; (B) 1M pages same - TRUE; (C) 5x buffers 2-pass - FALSE; (D) 30x buffers 3-pass - TRUE
**Q1.13** External: (A) Pass 0 same IOs - TRUE; (B) Double-buffer time - TRUE; (C) Output buffer all - FALSE
**Q1.14** Joins: (A) CNLJ scans outer - FALSE; (B) INLJ inner indexed - TRUE; (C) Index required - FALSE; (D) Two indexes, query larger - TRUE
**Q1.15** Joins: (A) SMJ if clustered - TRUE; (B) GHJ same value worst - FALSE; (C) SMJ skewed data - TRUE
**Q1.16** Bad optimization: (B) Highest selectivity first (should be lowest)
**Q1.17** Left-deep: (A) No cartesian - FALSE; (B) Optimal with perfect estimates - FALSE; (C) Polynomial time - FALSE; (D) Pipelined - TRUE
**Q1.18** Blocking operators: (B) DISTINCT; (D) ORDER BY
**Q1.19** Strict 2PL: (A) No dirty reads - TRUE; (B) No deadlock - FALSE; (C) Acyclic → conflict-serializable - TRUE; (D) Serializable = conflict-serializable - FALSE
**Q1.20** Locking: (A) Request/upgrade - TRUE; (B) Optimistic - FALSE; (C) Durable lock table - FALSE; (D) Fair access - FALSE
**Q1.21** Recovery: (A) NO-STEAL data fits - TRUE; (B) WAL fastest - FALSE; (C) FORCE buffers - FALSE; (D) NO-STEAL FORCE easiest - FALSE
**Q1.22** PDBMS: (A) Equal size - FALSE; (B) Hash better than round-robin - TRUE; (C) Range always better - FALSE; (D) Round-robin no skew - TRUE
**Q1.23** 2PC: (A) Cycle distributed deadlock - FALSE; (B) All vote abort - FALSE; (C) Ack after commit flush - TRUE; (D) Failed crash others - TRUE
**Q1.24** NoSQL: (A) Both scalability - TRUE; (B) Both latency - TRUE; (C) Only partition scaling - FALSE; (D) Replication without partitioning - FALSE
**Q1.25** Cassandra: (A) Hash partitioning - TRUE; (B) Schema-on-read - FALSE; (C) Horizontal scaling - TRUE; (D) Sync updates - TRUE

**Q2.1** 2PC: (a) N2,N3 respond; (b) Mark aborted; (c) T committed

**Q2.2** Joins: (a) 42M IOs; (b) 42M IOs; (c) Uniform distribution; (d) 7,200 IOs; (e) 3,600 IOs; (f) Recursive rehash

**Q2.3** Serializability: Cycles → not serializable

**Q2.4** Deadlock detection: Construct waits-for graph

**Q2.5** Deadlock prevention: Wait-Die & Wound-Wait policies

**Q2.6** Query optimization: Selectivity formulas and dynamic programming

**Q2.7** Buffer management: MRU/Clock replacement policies

**Q2.8** Files/Pages: Slotted pages, fragmentation, record encoding

**Q2.9** PDBMS: Data skew, parallel joins, aggregation

**Q2.10** Cassandra CQL: Queries, indexing, denormalization

---

**KEY FORMULAS:**
- CNLJ: ⌈M/(B-2)⌉×N + M
- SMJ sort passes: 1 + ⌈log_{B-1}(⌈N/B⌉)⌉
- GHJ: 3(R+S) IOs, needs (B-1)(B-2) ≥ R/(B-1)
- Selectivity: RF = 1/max(distinct values) for joins
- AND: multiply RFs; OR: RF1 + RF2 - RF1×RF2
