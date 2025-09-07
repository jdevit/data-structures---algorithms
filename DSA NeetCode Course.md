# Arrays: Data Storage and Operations

An array is a fundamental data structure that stores a collection of elements, typically of the same data type, in a **contiguous block of memory**. Understanding how arrays work involves a basic knowledge of **Random Access Memory (RAM)**.

---

## RAM and Memory

RAM is a type of computer memory used for storing data and instructions that are actively being used by the computer. Data in RAM is stored at specific memory addresses. A common unit of data is a **byte**, which is composed of 8 bits. For example, a single integer is typically represented using 4 bytes. An array's elements are stored one after the other in a contiguous block, which allows for fast access to any element.

---

## Array Properties and Operations

- **Indexed Access**: Array elements are accessed using an **index**, which starts at 0. This allows for very fast, direct access to any element.
    
- **Fixed Size**: Arrays are generally **fixed-size**, meaning their size is determined at the time of creation and cannot be changed. In dynamic languages like JavaScript, what are often called arrays are actually **dynamic arrays** or **array lists** that automatically resize themselves when needed.
    
- **Insertion and Deletion**:
    
    - **Insertion/Removal at the end**: Adding or removing an element from the end of a dynamic array is an **O(1)** operation, as it doesn't require shifting other elements.
        
    - **Insertion/Removal in the middle**: Inserting or removing an element from the middle of an array is an **O(n)** operation. This is because all subsequent elements must be shifted to make space for the new element or to fill the gap left by a removed one.
        

---

## Big O Operations Table

|Operation|Big O Notation|
|---|---|
|Read/Write i-th element|O(1)|
|Insert/Remove at end|O(1)|
|Insert/Remove in the middle|O(n)|