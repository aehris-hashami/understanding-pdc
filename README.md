# Parallel & Distributive Computing — Categorized Mastery Roadmap

Each category bundles: **core topics + the real-world problems they solve + the technologies (old/modern) used.** Study top to bottom — each category leans on the one before it.

---

## 1. Fundamentals — Mental Model & Metrics
**Topics:** Intro to PDC · why parallelism vs why distribution · sequential vs parallel vs distributed thinking · performance metrics (speedup, efficiency, scalability, latency, throughput)
**Why it matters:** This is the lens you apply to *every* problem below — before picking a tool, you decide "is this compute-bound (parallelize) or coordination-bound (distribute)?"
**Industry framing:** every problem in this list is ultimately justified by these metrics — e.g. "can we get 10x speedup" or "can this scale to 1M users."

---

## 2. Hardware Architecture & Memory Hierarchy
**Topics:** CPU architecture & memory hierarchy · cache, cache coherence, NUMA · shared vs distributed memory · Flynn's taxonomy · SIMD/MIMD, multicore, manycore, GPU systems
**Industry problems:** video processing & rendering · genomics/bioinformatics (compute-heavy pipelines) · weather/climate modeling (raw FLOPs) · scientific simulation
**Technologies:**
- *Old/classic:* vector processors, multiprocessors, pipeline/array processors, shared-memory SMP
- *Still important:* NUMA-aware programming
- *Modern:* GPUs, heterogeneous computing (CPU+GPU+accelerator)

---

## 3. Parallel Programming Models
**Topics:** task parallelism · data parallelism · process-centric models · shared-memory vs message-passing
**Industry problems:** large-scale AI/ML training (data parallelism) · video rendering (task parallelism) · scientific simulation
**Technologies:** OpenMP, pthreads (shared-memory) · MPI (message-passing) · CUDA (GPU data-parallel)

---

## 4. Parallel Algorithm Design
**Topics:** decomposition & partitioning · scheduling & load balancing · contention · communication overhead
**Industry problems:** real-time recommendation systems · fraud/anomaly detection · search indexing (parallel crawl/index builds)
**Conceptual tools:** map-reduce pattern, work-stealing, divide & conquer — the design patterns that sit underneath every framework in category 10

---

## 5. Synchronization & Coordination
**Topics:** mutual exclusion · barriers · atomicity · critical sections · consensus basics
**Industry problems:** financial risk/pricing simulation (coordinated parallel runs must agree on state) · any multi-threaded real-time system
**Conceptual tools:** locks, semaphores, atomics — the primitives consensus algorithms (ch. 9) are built on top of

---

## 6. Distributed System Foundations & Communication
**Topics:** execution & communication models · middleware · global state · synchronous vs asynchronous systems · message passing · shared-state issues
**Industry problems:** distributed databases & storage · IoT/sensor-data aggregation · search engine indexing (distributed crawlers talking to each other)
**Conceptual tools:** this is where "parallel" thinking stops being enough and "distributed" thinking (no shared clock, no shared memory, partial failure) takes over

---

## 7. Cloud Computing, HPC & Storage Systems
**Topics:** cloud architecture — services, storage, data management, elastic scaling · HPC & cluster computing — supercomputers, clusters, high-performance workloads
**Industry problems:** large-scale AI/ML training infrastructure · weather/climate modeling (supercomputer-class HPC) · genomics/bioinformatics · distributed databases
**Technologies:** cloud platforms (elastic compute/storage) · Hadoop-style distributed storage & processing · HPC clusters/supercomputers

---

## 8. Performance Engineering, Profiling & Optimization
**Topics:** benchmarking · bottleneck analysis · optimization tuning
**Industry problems:** real-time recommendation systems (latency budgets) · video rendering pipelines · financial pricing simulation (must finish within a time window)
**Skill outcome:** given a slow parallel/distributed system, find *where* time is lost (compute, communication, or contention) and fix it

---

## 9. Fault Tolerance, Reliability & Consistency
**Topics:** recovery · replication · failure handling · consistency tradeoffs
**Industry problems:** distributed databases & storage · fraud detection (must never go down) · financial systems · large-scale AI training (checkpointing for long jobs)
**Conceptual tools:** this is where consensus (ch. 5) gets applied at scale — replication protocols, quorum reads/writes, eventual vs strong consistency

---

## 10. Frameworks, Advanced Applications & Capstone
**Topics:** OpenMP, MPI, CUDA, pthreads · Hadoop-style distributed storage/processing · big data analytics · machine learning · computer vision · scientific simulation
**Industry problems (full sweep — pick a few to build toward):**
- Search engines & indexing
- Financial risk & pricing simulation
- Weather & climate modeling
- Genomics & bioinformatics
- Video processing & rendering
- Real-time recommendation systems
- Distributed databases & storage
- Large-scale AI/ML training
- Fraud & anomaly detection
- IoT & sensor-data aggregation

This category is where every earlier category gets exercised at once: hardware choice (2) + programming model (3) + algorithm design (4) + sync (5) + distributed comms (6) + cloud/HPC deployment (7) + tuning (8) + fault tolerance (9), applied to one real system end to end.

---

## Fast Study Order (same as categories above, in sequence)
1 → 2 → 3 → 4 → 5 → 6 → 7 → 8 → 9 → 10

## End-state check
Given any new problem, you should be able to: decide parallel vs distributed vs both → pick a programming/communication model → map it to the right hardware → implement with a suitable framework → reason about scalability, correctness, and fault tolerance.
