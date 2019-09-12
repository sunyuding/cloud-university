# Binary Search

## Divide & Conquer - Divide the input space

## Reference
- [ ] [Binary Search (video)](https://www.youtube.com/watch?v=D5SrAga1pno)
- [ ] [Binary Search (video)](https://www.khanacademy.org/computing/computer-science/algorithms/binary-search/a/binary-search)
- [ ] [detail](https://www.topcoder.com/community/data-science/data-science-tutorials/binary-search/)
- [ ] Implement:
    - binary search (on sorted array of integers)
    - binary search using recursion

# 2 Pointers/K Pointers
- Apply on sequence typed data
Categories
- Opposite direction
    - 2 sum, 3 sum, x sum
- Same direction

## Two Sum, Two Diff Problem

### Q1. 2 sum, how many pairs sum = target
0. no duplicate
1. could be duplicate, but we don't count
2. could be duplicate, but we count

### Q2. Unsorted array # of pairs sum to target

## Partition/Removal

iterate(explore) all the elements in the input array.
for each of them:
    determine if we need to retain the cur element.

- [0   , slow]: the left part of the array are non-zeros()
- (slow, fast]: garbage area
- [fast, right end of array]: the area we need to explore each time

# Sliding Windows
- Still 2 pointers: slow/fast
- With slow/fast pointers, what we are interested in is the part **between the two pointers**
- Size of the window
    - fixed size sliding window, when fast ++, slow must ++.
    - non fixed size sliding window, 
- Key benefits/points
    - reuse the computation result of the previous sliding window - **Time**
    - reduce the space consumption- **Space**
- extended to non-array scenario
    - Basiclly works well for all **sequence** type

- [0, slow): not useful to us anymore
- [slow, fast]: the actual sliding window we are interested in
- (fast, end of array]: the area to explore

## Fixed sizer
is relatively easy
    - usually it is clearly prompted in the problem's description
    - when fast++, slow++

```java
while (fast < array.length) { 
    add the delta for fast;
    remove delta for slow;
    fast++;
    slow++;
}
```

Check two Maps if they equal:
A: {a:1, b:1, c:1}
B: {a:1, b:1, c:1}

```Java
for (<K, V> in B) {
    check the corresponding V for the same K in A
}
```
O(size of the map)

### Q2. Find all **anagrams** of a shorter String in a longer String.
Using a variable "match" to record # of distinct characters already matched to the shorter String.

### Q3. Maximum value of each size K subarray.
how can we represent the sliding window efficiently?

Choices
- maxHeap
    - add array[fast] -> O(logk)
    - remove array[slow] 
    - get max -> O(1)
- treeMap/treeSet 
    - add array[fast] -> O(logk)
    - remove array[slow] -> O(logk)
    - get max -> O(logk)
- monotonically decreasing deque
    - add array[fast] -> O(1) amortized
    - remove array[slow] -> O(1)
    - get max -> O(1)

What if we have duplicate elements?
- use pair of <index, value>

### Q3.1 Find k-largest elements in each of the subarray of size n.
e.g. [1, 4, 3, 2, 1, 2], n = 3, k = 2.

Can we use monotonically decreasing deque? NO.
- how can we represent the sliding window efficiently? what data structure
    - maxHeap
        - add array[fast] -> O(logn)
        - remove array[slow] -> O(logn) ?? -> lazy
        - get k largest -> O(k * logn) poll() operation * k times
    - treeMap/treeSet 
        - add array[fast] -> O(logn)
        - remove array[slow] -> O(logn)
        - get k largest -> O(k + logn)

### Q4.1: given an Array, if duplicate, return true, else false

### Q4.2: 

## 2D Sliding Window

## Non-fixed Size Sliding Window

# Tree

## Binary Tree Traversals(pre, post, in-order)
- Recursion
- Iterative ways
    - Stack - simulate the recursion call stack
    - parent pointer

- Iterator

class TreeNode {
    TreeNode left;
    TreeNode right;
    TreeNode parent;
}

### 1.0 In-Order traversal with recursion
- pros:
    - elegant
- cons:
    - Stack space

Time/Space complexity is the same.
- Recursion: use call Stack space -> stackoverflow
- Iteration: use Heap space

### 1.1 In-Order traversal(iterative), with Stack.
```java
public List<Integer> inorderTraversal(TreeNode root) {
    List<Integer> result = new ArrayList<>();
    if (root == null) {
        return result;
    }
    Deque<TreeNode> stack = new ArrayDeque<>();
    // 1. initial state:
    pushLeft(root, stack);
    while(!stack.isEmpty()) {
        TreeNode cur = stack.pollFirst(); // nextNode()
        result.add(cur.val);
        pushLeft(root.right, stack);
    }
    return result;
}

private void pushLeft(TreeNode cur, Deque<TreeNode> stack) {
    while(cur != null) {
        stack.offerFirst(cur);
        cur = cur.left;
    }
}
```
Time: O(n) - for each node, it is only pushed and popped once from the Stack.
Space: O(height)

### 1.2 In-Order traversal Binary Tree, using the following methods - with parent pointer
```java
TreeNode cur = firstNode(root);
while (cur != null) {
    cur = nextNode(cur);
}
```

```
            1
        /       \
        2        3
     /   \      /  \
    4    7     6    5
     \
      8
        \
          9
```
- if current = 9, next is 2: 9 -> 8 -> 4 -> 2
- if current = 5, next is null.

inorder traverse the current node, what is the next:
- we don't need to check the cur.left subtree at all! because we are using inorder
- cur.rigth != null
    - firstNode of the right subtree - **firstNode(cur.right)**
- cur.right == null
    - along the path using parent pointer from cur to root:
        find the first node where node.parent == null || node.parent.left == null
```java
public TreeNode firstNode(TreeNode root) {
    if (root == null) return null;
    while (root.left != null) root = root.left;
    return root;
}

public TreeNode nextNode(TreeNode cur) {
    if (cur == null) return null;
    // case 1: cur.right != null
    if (cur.right != null) return firstNode(cur.right);
    // case 2: cur.right == null
    while(cur.parent != null && cur == cur.parent.right) {
        cur = cur.parent;
    }
    // terminate cur.parent == null || cur.parent.left == cur
    return cur.parent;
}
```
- Time: O(n) - for each edge, we traversed down/up twice - O(# of edges) = O(# of nodes)
- Space: O(1)

### 1.3 pre-order, post-order with parent pointer iterative traversal

### Q3. k-th largest node in the given BST.
=> find the kth largest node in the sorted sequence by inorder traversal
1. Recursion
2. Iterative - Using Iterator to decouple the traversal logic

## The views of binary tree

## DFS Traversals

## BFS vs. DFS Traversals

# PriorityQueue vs. TreeSet/TreeMap
Categorize the data structures by sorted property
- sorted data structure
    - sorted array/sorted linked list
    - BST(balanced)
    - priorityqueue(partially sorted)
- unsorted data structure

## PriorityQueue
- top k
- find median
- Best First Search

The most basic operations
- O(1) get min - peek()
- O(logn) insert into the heap - offer()
- O(logn) remove min from min heap - poll()

## Read more

# Reference
