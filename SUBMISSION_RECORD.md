# Submission Record

## Submission 1
- **Submission ID**: 766740
- **Time**: 2026-04-01T02:20:46.982502
- **Status**: Accepted
- **Score**: 100/100 (Perfect Score!)
- **Attempts Used**: 1/5

### Test Results:
- Test 1 (Subtask 1 - Location classes): Accepted (20 points)
- Test 2 (Subtask 2): Accepted (10 points)
- Test 3 (Subtask 3): Accepted (10 points)
- Test 4 (Subtask 4): Accepted (20 points)
- Test 5 (Subtask 5): Accepted (10 points)
- Test 6 (Subtask 5): Accepted (10 points)
- Test 7 (Subtask 6 - Stress test): Accepted (10 points)
- Test 8 (Subtask 6 - Stress test): Accepted (10 points)

### Performance:
- Total time: 169ms
- Max memory: 8.35MB
- All test cases passed within time and memory limits

### Implementation Details:
- Used `std::set` with custom `EndpointComparator` for active intervals (sorted by endpoint)
- Used `std::stack` for free registers to ensure FILO behavior
- Proper implementation of expireOldIntervals() to free registers when intervals end
- Proper implementation of spillAtInterval() to spill the interval with largest endpoint
- All Location classes (Register, StackSlot) implemented correctly

## Summary
✅ Perfect score achieved on first attempt!
✅ All subtasks passed including stress tests
✅ Efficient implementation with good performance
