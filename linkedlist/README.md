# Linked List Problems

### 1. Reverse a Linked List

**Pattern**: Three-pointer technique (prev, current, next)  
**Key Insight**: Reverse links while traversing once  
**Use Case**: List manipulation, palindrome checking  
**Time Complexity**: O(n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Initialize `prev = NULL`, `current = head`
2. Loop while `current ≠ NULL`:
   - Save `next = current→next`
   - Reverse: `current→next = prev`
   - Move: `prev = current`, `current = next`
3. Return `prev` as new head

### 2. Find Middle Element in Linked List

**Pattern**: Fast and slow pointers (tortoise and hare)  
**Key Insight**: Fast moves 2x speed, slow reaches middle when fast reaches end  
**Use Case**: Binary search, palindrome checking, list partitioning  
**Time Complexity**: O(n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Initialize `slow = head`, `fast = head`
2. Loop while `fast ≠ NULL` and `fast→next ≠ NULL`:
   - Move `slow = slow→next` (1 step)
   - Move `fast = fast→next→next` (2 steps)
3. Return `slow` as middle element
