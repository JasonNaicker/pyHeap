# pyHeap — Binary Heap (Min-Heap & Max-Heap)

An extensible and efficient binary heap implementation supporting **both Min-Heap and Max-Heap behavior** from a single class.

---

## Overview

| Component | Purpose |
|---------|---------|
| `Heap` | Binary heap supporting min-heap or max-heap behavior |
| Internal array | Stores heap elements in contiguous memory |
| Heapify operations | Efficient up/down reordering to maintain heap property |
| Utility methods | Push, pop, peek, replace, push-pop, clear, and visualization methods |

---

## Features

- Supports **Min-Heap** and **Max-Heap**
- Build heap in **O(n)** time
- Push / Pop in **O(log n)**
- Efficient `push_pop()` and `replace()` operations
- Tree-style visualization for debugging
- Dunder methods (`__len__`, `__bool__`, `__repr__`)

---

## Time Complexity Chart:

| Operation    | Complexity     |
| ------------ | -------------- |
| `build_heap` | O(n)           |
| `push`       | O(log n)       |
| `pop`        | O(log n)       |
| `peek`       | O(1)           |
| `replace`    | O(n) + heapify |
| `push_pop`   | O(log n)       |


>## User Example

```python
from heap import Heap

# Max-Heap (default)
heap = Heap([5, 3, 8, 1, 2])

# Min-Heap
min_heap = Heap([5, 3, 8, 1, 2], isMinHeap=True)

#Utility methods
heap.push(10)        # Insert element
heap.pop()           # Remove root
heap.peek()          # View root without removing
heap.push_pop(4)     # Push then pop efficiently
heap.replace(8, 6)   # Replace existing value

#Extra methods
len(heap)            # Heap size
bool(heap)           # Empty check
heap.items()         # Shallow copy of elements
heap.clear()         # Remove all elements

#Visualization
heap.print_contents()    # Raw array view
heap.display_contents()  # Tree-style layout

[MaxHeap]:
    10
  8    5
 3  1  2
```

## Benchmarks(1,000,000 Heap Size / 1000 Iterations):
```python
Operation                 Iterations   Total(s)     Avg(s)        Min(s)        Max(s)        StdDev
---------------------------------------------------------------------------------------------------
push                            1000     0.0024   0.00000237   0.00000060   0.00101530   0.00003207
pop                             1000     0.0093   0.00000928   0.00000430   0.00003950   0.00000230
peek                            1000     0.0001   0.00000015   0.00000010   0.00000170   0.00000007
push_pop                        1000     0.0082   0.00000818   0.00000060   0.00002620   0.00000172
replace                         1000    13.9319   0.01393187   0.00010060   0.03169320   0.00626824
build_heap                      1000   588.0408   0.58804078   0.50645580   1.02114870   0.03644119
```

