## Part C: Experiments and Analysis

### Experiment 1: Belady's Anomaly

**Reference String:** 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5

#### Results with 3 Frames

| Algorithm | Page Faults | Page Hits |
|---|---:|---:|
| FIFO | 9 | 3 |
| LRU | 10 | 2 |
| Optimal | 7 | 5 |

#### Results with 4 Frames

| Algorithm | Page Faults | Page Hits |
|---|---:|---:|
| FIFO | 10 | 2 |
| LRU | 8 | 4 |
| Optimal | 6 | 6 |

**Q1. Does FIFO show Belady's anomaly?**

**Answer:** Yes. FIFO shows Belady's anomaly because its page faults increase from 9 with 3 frames to 10 with 4 frames. This means that increasing the number of frames can sometimes increase page faults in FIFO.

**Q2. Do LRU and Optimal show Belady's anomaly for this reference string?**

**Answer:** No. For this reference string, LRU page faults decrease from 10 to 8, and Optimal page faults decrease from 7 to 6 when the number of frames increases from 3 to 4.

### Experiment 2: Comparing FIFO and LRU

**Number of Frames:** 3

#### Case A: LRU Performs Better Than FIFO

**Reference String:** 4, 5, 3, 2, 3, 3, 3, 5, 4, 1, 5, 2, 1, 3, 1

| Algorithm | Page Faults | Page Hits |
|---|---:|---:|
| FIFO | 10 | 5 |
| LRU | 8 | 7 |

**Observation:** LRU performs better than FIFO because it produces 2 fewer page faults for this reference string.

#### Case B: FIFO Performs Better Than LRU

**Reference String:** 2, 5, 5, 3, 3, 4, 3, 5, 1, 2, 1, 4, 4, 2, 1

| Algorithm | Page Faults | Page Hits |
|---|---:|---:|
| FIFO | 6 | 9 |
| LRU | 7 | 8 |

**Observation:** FIFO performs better than LRU because it produces 1 fewer page fault for this reference string.

### Short Questions

**Q1. Why is Optimal Page Replacement not practically implementable in a real operating system?**

**Answer:** Optimal Page Replacement requires knowing which pages will be used in the future. Since a real operating system cannot predict future page references exactly, this algorithm cannot be implemented practically. It is mainly used as a benchmark.

**Q2. What extra hardware or bookkeeping does LRU need compared with FIFO?**

**Answer:** LRU needs to track when each page was last used. This requires extra bookkeeping, such as timestamps, counters, or a stack-like structure. FIFO mainly tracks the order in which pages entered memory.

**Q3. If the number of frames equals the number of distinct pages in the reference string, how many page faults will each algorithm produce, and why?**

**Answer:** FIFO, LRU, and Optimal will each produce a number of page faults equal to the number of distinct pages, assuming all frames are initially empty. Each distinct page causes one fault on its first reference, and no page needs to be replaced afterward.

