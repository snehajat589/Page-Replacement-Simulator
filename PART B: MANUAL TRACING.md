## Part B: Manual Tracing of Page Replacement Algorithms

**Reference String:** 7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2  
**Number of Frames:** 3

### 1. FIFO (First In First Out)

| Page | 7 | 0 | 1 | 2 | 0 | 3 | 0 | 4 | 2 | 3 | 0 | 3 | 2 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Frame 1 | 7 | 7 | 7 | 2 | 2 | 2 | 2 | 4 | 4 | 4 | 0 | 0 | 0 |
| Frame 2 | - | 0 | 0 | 0 | 0 | 3 | 3 | 3 | 2 | 2 | 2 | 2 | 2 |
| Frame 3 | - | - | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 3 | 3 | 3 | 3 |
| Status | F | F | F | F | H | F | F | F | F | F | F | H | H |

**Page Faults = 10**  
**Page Hits = 3**  
**Hit Ratio = 3/13 = 23.08%**

### 2. LRU (Least Recently Used)

| Page | 7 | 0 | 1 | 2 | 0 | 3 | 0 | 4 | 2 | 3 | 0 | 3 | 2 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Frame 1 | 7 | 7 | 7 | 2 | 2 | 2 | 2 | 4 | 4 | 4 | 0 | 0 | 0 |
| Frame 2 | - | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 3 | 3 | 3 | 3 |
| Frame 3 | - | - | 1 | 1 | 1 | 3 | 3 | 3 | 2 | 2 | 2 | 2 | 2 |
| Status | F | F | F | F | H | F | H | F | F | F | F | H | H |

**Page Faults = 9**  
**Page Hits = 4**  
**Hit Ratio = 4/13 = 30.77%**

### 3. Optimal Page Replacement

| Page | 7 | 0 | 1 | 2 | 0 | 3 | 0 | 4 | 2 | 3 | 0 | 3 | 2 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Frame 1 | 7 | 7 | 7 | 2 | 2 | 2 | 2 | 2 | 2 | 2 | 2 | 2 | 2 |
| Frame 2 | - | 0 | 0 | 0 | 0 | 0 | 0 | 4 | 4 | 4 | 0 | 0 | 0 |
| Frame 3 | - | - | 1 | 1 | 1 | 3 | 3 | 3 | 3 | 3 | 3 | 3 | 3 |
| Status | F | F | F | F | H | F | H | F | H | H | F | H | H |

**Page Faults = 7**  
**Page Hits = 6**  
**Hit Ratio = 6/13 = 46.15%**

*F = Page Fault, H = Page Hit*

### Comparison Table

| Algorithm | Page Faults | Page Hits | Hit Ratio |
|---|---:|---:|---:|
| FIFO | 10 | 3 | 23.08% |
| LRU | 9 | 4 | 30.77% |
| Optimal | 7 | 6 | 46.15% |

**Conclusion:** Optimal page replacement produces the fewest page faults for this reference string, followed by LRU and FIFO.
