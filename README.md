# Arrays

### 1. Set Matrix Zeroes
**Pattern**: Use first row/column as markers  
**Key Insight**: O(1) space by leveraging existing structure  
**Use Case**: Grid modification with constraints  
**Time Complexity**: O(m×n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Check if first row/column has zeros and store in variables
2. Loop through matrix (except first row/column) to mark zeros in first row/column
3. Use markers to set zeros in inner matrix
4. Finally, set first row/column based on stored variables

### 2. Pascal's Triangle
**Pattern**: DP - build from previous row  
**Key Insight**: edges=1, inner=sum of above two  
**Use Case**: Combinatorial problems, DP  
**Time Complexity**: O(n²)  
**Space Complexity**: O(n²)  
**Dry Run**:
1. Loop from 0 to required length
2. Keep adding arrays of length i+1
3. Set first and last elements to 1
4. Calculate inner elements from previous array values

### 3. Next Permutation
**Pattern**: Find pivot → swap → reverse suffix  
**Key Insight**: Lexicographical ordering  
**Use Case**: Permutation generation  
**Time Complexity**: O(n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Find first decreasing element from right (pivot)
2. Find smallest greater element from right of pivot
3. Swap pivot with found element
4. Reverse the right subarray to make it ascending

### 4. Kadane's Algorithm
**Pattern**: Track current sum and max sum  
**Key Insight**: Reset when sum becomes negative  
**Use Case**: Maximum subarray problems  
**Time Complexity**: O(n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Initialize max and sum variables
2. Loop through array, adding values to sum
3. Update max when sum increases
4. Reset sum to 0 if it becomes negative

### 5. Dutch National Flag
**Pattern**: Three pointers partitioning  
**Key Insight**: In-place O(n) sorting  
**Use Case**: Partitioning, categorization  
**Time Complexity**: O(n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Set low, mid, high pointers
2. 0 to low-1 = 0s, low to mid-1 = 1s, mid to high = unsorted, high+1 to end = 2s
3. If mid=0, swap with low and increment both
4. If mid=1, increment mid
5. If mid=2, swap with high and decrement high

### 6. Stock Buy/Sell
**Pattern**: Track min price and max profit  
**Key Insight**: Single pass greedy approach  
**Use Case**: Time series optimization  
**Time Complexity**: O(n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Use max profit and minimum variables
2. Loop through array
3. If current price < min, update min
4. Else update profit if current profit > max profit
