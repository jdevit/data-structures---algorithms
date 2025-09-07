# DSA Study Note Cleaner

## Arrays: Data Storage and Operations

An array is a data structure that stores a collection of elements, usually of the same data type, in a contiguous block of memory. This contiguity allows for direct, fast access to any element.

---

### **Topics**

- Array Properties
    
- Big O Notation for Arrays
    
- Dynamic Arrays vs. Fixed-Size Arrays
    
- Stacks
    
- LeetCode Problems: Concatenation of Array & Valid Parentheses
    

---

### **Array Properties**

- **Contiguous Memory**: Elements are stored next to each other in a single block of memory.
    
- **Indexed Access**: Elements are accessed using an index, which starts at **0**.
    
- **Fixed vs. Dynamic Size**:
    
    - **Fixed-size arrays** are allocated with a specific size at creation, which cannot be changed.
        
    - **Dynamic arrays** (like those in Python and JavaScript) automatically resize themselves when full. This often involves creating a new, larger array and copying all elements. While a single resize operation can be O(n), the overall **amortized time complexity** for adding elements is still considered O(1).
        

---

### **Big O Operations for Arrays**

|**Operation**|**Big O Notation**|**Notes**|
|---|---|---|
|Read/Write i-th element|O(1)|Direct access via index.|
|Insert/Remove at end|O(1)|Requires no shifting of other elements.|
|Insert/Remove in the middle|O(n)|All subsequent elements must be shifted.|

---

### **Stacks**

A stack is a data structure that follows the **Last-In, First-Out (LIFO)** principle. It is often implemented using an array or a linked list.

|**Operation**|**Big O Notation**|
|---|---|
|Push (add element to top)|O(1)|
|Pop (remove element from top)|O(1)|
|Peek/Top (view top element)|O(1)|

Stacks are useful for tasks like reversing sequences or validating parentheses.

---

### **Problem: Concatenation of Array**

**Problem Description**: Given an array `nums` of length `n`, create a new array `ans` of length `2n` that is a concatenation of two copies of `nums`.

**Python Solution**:

Python

```
class Solution:
    def getConcatenation(self, nums: List[int]) -> List[int]:
        # Create a new list and append all elements from nums, twice
        new_list = []
        for i in nums:
            new_list.append(i)
        for i in nums:
            new_list.append(i)
        return new_list
```

Time Complexity: O(n), where n is the length of the input array. The code iterates through the array twice.

Space Complexity: O(n), as a new list of size 2n is created.

---

### **Problem: Valid Parentheses**

**Problem Description**: Given a string `s` containing only parentheses `()`, `[]`, `{}`, determine if the string is valid. A string is valid if open brackets are closed by the same type of brackets in the correct order.

**Python Solution**:

Python

```
class Solution:
    def isValid(self, s: str) -> bool:
        stack = []
        pairs = {")": "(", "]": "[", "}": "{"}

        for char in s:
            if char in pairs:  # If the character is a closing bracket
                # Check if the stack is not empty and the top element matches the corresponding open bracket
                if stack and stack[-1] == pairs[char]:
                    stack.pop()
                else:
                    return False  # Mismatched or no corresponding open bracket
            else:  # If the character is an opening bracket
                stack.append(char)
        
        # The string is valid only if the stack is empty at the end
        return not stack
```

Time Complexity: O(n), as the code iterates through each character of the string once.

Space Complexity: O(n) in the worst-case, for a string like ((((....)))), where the stack would store all the opening brackets.