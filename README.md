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
**Dry Run**:  
1. For 3x3 matrix: transpose then reverse each row  
2. Original: `[[1,2,3],[4,5,6],[7,8,9]]`  
3. Transpose: `[[1,4,7],[2,5,8],[3,6,9]]`  
4. Reverse rows: `[[7,4,1],[8,5,2],[9,6,3]]`  

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

