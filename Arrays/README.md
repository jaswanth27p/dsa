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

### 7. Rotate Matrix
**Pattern**: Layer-by-layer rotation or transpose + reverse  
**Key Insight**: Mathematical pattern in index transformation  
**Use Case**: Matrix transformations, image processing  
**Time Complexity**: O(n²)  
**Space Complexity**: O(1) for in-place, O(n²) if using extra space  
**Approach 1 (Index Pattern)**:  
- For 90° clockwise: `new_matrix[i][j] = matrix[n-1-j][i]`  
- Create new matrix with transformed indices

**Approach 2 (In-place)**:  
1. Transpose the matrix (swap rows and columns)  
2. Reverse each row of the transposed matrix  

### 8. Merge Overlapping Subintervals
**Pattern**: Sort and merge  
**Key Insight**: Sort by start time, then merge adjacent intervals  
**Use Case**: Interval merging, scheduling problems  
**Time Complexity**: O(n log n) for sorting + O(n) for merging  
**Space Complexity**: O(1) or O(n) depending on implementation  
**Dry Run**:  
1. Initialize counter at position 0
2. Compare each interval with last merged interval
3. Merge overlaps by updating current range
4. Move non-overlapping intervals forward and increment counter
5. Return intervals from index 0 to counter

### 9. Search in a 2D Matrix
**Pattern**: Binary Search on 2D structure  
**Key Insight**: Treat matrix as 1D sorted array using index mapping  
**Use Case**: Efficient searching in row/column sorted matrices  
**Time Complexity**: O(log(m×n))  
**Space Complexity**: O(1)  
**Dry Run**:
1. Initialize low=0, high=(rows×cols)-1
2. While low <= high, calculate mid = (low+high)/2
3. Map mid to 2D indices: row = mid/cols, col = mid%cols
4. Compare target with matrix[row][col]
5. Adjust search range based on comparison
6. Return true if found, false otherwise

### 10. Pow(x, n)
**Pattern**: Exponentiation by squaring  
**Key Insight**: Divide and conquer approach for efficient calculation  
**Use Case**: Mathematical computations, optimization problems  
**Time Complexity**: O(log n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Convert n to absolute value (handle sign later)
2. Initialize result = 1
3. While absolute n > 0:
   - If n is odd: multiply result by x, reduce n by 1
   - If n is even: square x, halve n
4. Return result (or 1/result for negative n)

### 11. Majority Element (> n/2)
**Pattern**: Boyer-Moore Voting Algorithm  
**Key Insight**: Cancel out pairs of different elements, majority remains  
**Use Case**: Finding dominant elements in streams/data  
**Time Complexity**: O(n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Initialize count = 0, candidate = null
2. Loop through each element:
   - If count == 0: set candidate = current element
   - If current element == candidate: count++
   - Else: count--
3. Return candidate (guaranteed majority exists)

### 12. Majority Element (> n/3)
**Pattern**: Extended Boyer-Moore Voting  
**Key Insight**: At most 2 elements can appear > n/3 times  
**Use Case**: Finding frequent elements with threshold  
**Time Complexity**: O(n)  
**Space Complexity**: O(1)  
**Dry Run**:
1. Initialize candidate1, candidate2 = null, count1, count2 = 0
2. Loop through elements:
   - If element == candidate1: count1++
   - Else if element == candidate2: count2++
   - Else if count1 == 0: set candidate1 = element, count1 = 1
   - Else if count2 == 0: set candidate2 = element, count2 = 1
   - Else: count1--, count2--
3. Verify both candidates actually appear > n/3 times
4. Return valid candidates
