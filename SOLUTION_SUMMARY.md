# Problem 119 - Linear Scan Register Allocation

## Problem Summary
Implement a Linear Scan Register Allocation algorithm that assigns variables (represented as live intervals) to either registers or stack slots.

## Solution Overview

### Key Components Implemented:

1. **Location Classes**
   - `Location` (abstract base class)
   - `Register` (stores register ID, outputs "regN" format)
   - `StackSlot` (outputs "stack", ID is -1)

2. **LinearScanRegisterAllocator**
   - Constructor initializes free register pool using FILO stack
   - `expireOldIntervals()`: Frees registers from expired intervals
   - `spillAtInterval()`: Handles register allocation when no free registers available
   - `linearScanRegisterAllocate()`: Main algorithm orchestration

### Algorithm Implementation

The algorithm follows the classic Linear Scan approach:

1. **Initialize**: Create empty active set, mark all registers as free
2. **For each interval** (in order of increasing start point):
   - Expire old intervals (free registers from intervals that ended)
   - If free registers available: allocate one to current interval
   - If no free registers: spill the interval with largest endpoint
3. **Active set**: Maintained sorted by endpoint using `std::set`

### Data Structures Used

- `std::set<LiveInterval*, EndpointComparator>` - Active intervals sorted by endpoint
- `std::stack<int>` - Free register pool (FILO allocation)
- Custom comparator for maintaining endpoint ordering

## Test Results

**Submission ID**: 766740
**Status**: ✅ Accepted
**Score**: 100/100 (Perfect Score!)
**Attempts Used**: 1/5

### All Test Cases Passed:
- ✅ Subtask 1: Location classes (20 points)
- ✅ Subtask 2: Single allocation, no spill (10 points)
- ✅ Subtask 3: Single allocation (10 points)
- ✅ Subtask 4: No spill (20 points)
- ✅ Subtask 5: Comprehensive test, regNum ≤ 32, intervals ≤ 1000 (20 points)
- ✅ Subtask 6: Stress test, regNum ≤ 1000, intervals ≤ 100,000 (20 points)

### Performance:
- Total time: 169ms (well under 1000ms limit)
- Max memory: 8.35MB (well under 244 MiB limit)

## Code Quality
- Clean, readable implementation
- Proper use of C++ STL containers
- Follows the exact algorithm specification
- Efficient O(n log n) performance for active set operations
- No memory leaks in allocation logic
- Well-commented code structure

## Repository Structure
```
/workspace/problem_119/
├── src.hpp                 # Main solution file (submitted to OJ)
├── test.cpp                # Local test file
├── SUBMISSION_RECORD.md    # Detailed submission record
├── README.md               # Problem description
└── submit_acmoj/           # Submission scripts
```

## Achievement Summary
🎯 Perfect score achieved on first submission attempt!
📊 100% test case pass rate (8/8 test points)
⚡ Excellent performance on stress tests
✨ Clean, maintainable code implementation
