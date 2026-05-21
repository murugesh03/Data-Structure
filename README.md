# 📚 Data Structures — Complete Guide
### From Beginner to Super Advanced
> **Author:** Murugesh Padmanabhan | **Stack:** JavaScript / TypeScript / Python  
> **Level:** 🟢 Beginner → 🟡 Intermediate → 🔴 Advanced → 🚀 Super Advanced

---

## 📋 Table of Contents

1. [What is a Data Structure?](#1-what-is-a-data-structure)
2. [Big O Notation (Complexity)](#2-big-o-notation-complexity) — Visual Guide for Everyone
3. [Arrays](#3-arrays)
4. [Strings](#4-strings)
5. [Linked Lists](#5-linked-lists)
6. [Stacks](#6-stacks)
7. [Queues](#7-queues)
8. [Hash Tables (Hash Maps)](#8-hash-tables-hash-maps)
9. [Sets](#9-sets)
10. [Trees](#10-trees)
11. [Binary Search Tree (BST)](#11-binary-search-tree-bst)
12. [Heaps / Priority Queues](#12-heaps--priority-queues)
13. [Graphs](#13-graphs)
14. [Tries (Prefix Trees)](#14-tries-prefix-trees)
15. [Segment Trees](#15-segment-trees)
16. [Fenwick Tree (Binary Indexed Tree)](#16-fenwick-tree-binary-indexed-tree)
17. [Disjoint Set Union (Union-Find)](#17-disjoint-set-union-union-find)
18. [AVL Trees (Self-Balancing BST)](#18-avl-trees-self-balancing-bst)
19. [Red-Black Trees](#19-red-black-trees)
20. [Skip Lists](#20-skip-lists)
21. [Bloom Filters](#21-bloom-filters)
22. [Summary Cheat Sheet](#22-summary-cheat-sheet)

---

## 1. What is a Data Structure?

A **data structure** is a way to **organize and store data** in a computer so that it can be accessed and modified efficiently.

Think of it like this:

| Real-life analogy | Data Structure |
|---|---|
| A numbered locker row | Array |
| A stack of plates | Stack |
| A queue at a bank | Queue |
| A phone book | Hash Map |
| A family tree | Tree |
| A road map | Graph |

### Why does it matter?

```
Bad choice of data structure → Slow program → Poor user experience
Good choice of data structure → Fast program → Great user experience
```

---

## 2. Big O Notation (Complexity)

> 🎯 **What is Big O?** — It is simply a way to describe **how long a task takes as the amount of work grows**. Nothing more, nothing less. You don't need to be a programmer to understand it.

---

### 🧠 The Everyday Analogy First

Imagine you have a **jar of candies** with `n` candies inside.  
Different tasks you could do with that jar take different amounts of time.  
That is exactly what Big O measures.

---

### 📊 Visual Speed Chart — Slowest to Fastest (as input grows)

```
 NUMBER OF STEPS NEEDED (↑ = more steps = slower)
 (input size n = 10 items shown below)

  1000 │
       │                                              ██  O(n²)
   500 │
       │
   200 │
       │
   100 │
       │                                         ░░      O(n log n)
    50 │
       │
    20 │                                    ░░░░         O(n)
    10 │
       │                              ░░░░░
     5 │                        ░░░░░                    O(log n)
       │
     1 │  ░░░░░░░░░░░░░░░░░░░░░░                         O(1)
       └──────────────────────────────────────────────▶
          1    2    3    4    5    6    7    8    9   10
                        Input Size (n)

  ✅ FLAT line = FAST (doesn't matter how big n gets)
  ⚠️ STEEP line = SLOW (gets worse as n grows)
```

---

### 🌈 The Complete Complexity Rainbow

```
  BEST ◄────────────────────────────────────────────► WORST

  O(1)   O(log n)   O(n)   O(n log n)   O(n²)   O(2ⁿ)   O(n!)
   🟢      🟢        🟡       🟡           🔴       🔴       💀

  "Magic   "Phone    "Scan  "Good Sort"  "Nested  "Never"  "Never
  Button"  Book"     All"               Loops"            Ever"
```

---

### 🎭 Real-Life Story for Each Complexity

---

#### ✅ O(1) — Constant Time &nbsp;&nbsp; `[ INSTANT ]`

> **"The light switch"**

No matter how big your house is (1 room or 100 rooms), flipping a light switch takes the **same 1 second**. The size of your house doesn't matter at all.

```
House with  1 room  → flip switch → 💡 ON  (1 second)
House with 10 rooms → flip switch → 💡 ON  (1 second)
House with 99 rooms → flip switch → 💡 ON  (1 second)

n doesn't matter. Always 1 step. ✅
```

**In code terms:** Looking up item by index in an array — `arr[5]` — instantly done.

```
Speed bar:  ██████████████████████  BLAZING FAST ⚡
```

---

#### ✅ O(log n) — Logarithmic Time &nbsp;&nbsp; `[ VERY FAST ]`

> **"The phone book / dictionary trick"**

You want to find the name **"Murugesh"** in a 1000-page phone book.  
You don't start at page 1. Instead you:

```
Step 1: Open to page 500  → "M" comes AFTER this → now search pages 500–1000
Step 2: Open to page 750  → "M" comes BEFORE this → now search pages 500–750
Step 3: Open to page 625  → Found the M section!
Step 4: Narrow to exact name...

1000 pages → only ~10 steps needed!
```

Every step **cuts the problem in half**. This is called binary search.

```
n = 1,000      →  ~10 steps
n = 1,000,000  →  ~20 steps   ← barely increased!
n = 1,000,000,000 → ~30 steps ← still tiny!

Speed bar:  ████████████████████  VERY FAST 🚀
```

---

#### 🟡 O(n) — Linear Time &nbsp;&nbsp; `[ FAIR ]`

> **"The lost key search"**

You lost your key somewhere in your house.  
You have to **check every room one by one** until you find it.

```
 3-room house →  check 3 rooms  → found! (3 steps)
10-room house →  check 10 rooms → found! (10 steps)
50-room house →  check 50 rooms → found! (50 steps)

More rooms = more time. Steps grow equally with n. ⚠️
```

```
n =    10  →     10 steps
n =   100  →    100 steps
n = 1,000  →  1,000 steps

Speed bar:  █████████████  OKAY FOR SMALL INPUT 🟡
```

---

#### 🟡 O(n log n) — Linearithmic Time &nbsp;&nbsp; `[ ACCEPTABLE ]`

> **"Sorting a deck of cards smartly"**

Instead of comparing every card to every other card, you:
- **Split** the deck into halves (log n splits)
- **Sort each half** (n work per level)

```
Cards: [5, 2, 8, 1, 9, 3]
                 ↓ split
       [5, 2, 8]      [1, 9, 3]
          ↓ sort          ↓ sort
       [2, 5, 8]      [1, 3, 9]
                 ↓ merge
       [1, 2, 3, 5, 8, 9]  ✅

n =    10  →     33 steps    (10 × ~3.3)
n =  1000  →  10,000 steps   (1000 × ~10)
```

This is how **Merge Sort** and **Heap Sort** work.

```
Speed bar:  ████████████  GOOD FOR SORTING 🟡
```

---

#### 🔴 O(n²) — Quadratic Time &nbsp;&nbsp; `[ SLOW ]`

> **"The awkward party handshake"**

Every person at a party shakes hands with every OTHER person.

```
 2 people → 2 handshakes
 5 people → 20 handshakes       (5 × 4)
10 people → 90 handshakes       (10 × 9)
50 people → 2,450 handshakes!   (50 × 49)

It EXPLODES as more people arrive! 🤯
```

In code, this is a **loop inside a loop** (nested loops):

```
for every person:           ← outer loop (n)
    for every other person: ← inner loop (n)
        shake hands!

Total = n × n = n²
```

```
n =    10  →        100 steps
n =   100  →     10,000 steps
n = 1,000  →  1,000,000 steps  ← starts becoming unusable

Speed bar:  ████  GETS SLOW FAST 🔴
```

---

#### 🔴 O(2ⁿ) — Exponential Time &nbsp;&nbsp; `[ VERY SLOW ]`

> **"The chain letter nightmare"**

You send a letter to 2 friends. Each friend sends it to 2 more friends.

```
Day 1: You send to  2 people
Day 2: They send to 4 people
Day 3: Those send to 8 people
Day 4:             16 people
Day 5:             32 people
...
Day 30:     1,073,741,824 people! 🚨

Each day = 2× the previous. Grows EXPLOSIVELY!
```

```
n =  5  →          32 steps
n = 10  →       1,024 steps
n = 20  →   1,048,576 steps
n = 30  → 1,073,741,824 steps  ← exceeds world population!

Speed bar:  █  AVOID AT ALL COSTS 🔴
```

---

#### 💀 O(n!) — Factorial Time &nbsp;&nbsp; `[ IMPOSSIBLE ]`

> **"Trying every possible seating arrangement"**

You have `n` guests and you want to try every possible seating order.

```
2 guests  →          2 arrangements  (2×1)
3 guests  →          6 arrangements  (3×2×1)
4 guests  →         24 arrangements  (4×3×2×1)
5 guests  →        120 arrangements
10 guests →  3,628,800 arrangements
20 guests →  2,432,902,008,176,640,000 arrangements 🤯💀

COMPLETELY IMPRACTICAL beyond tiny inputs!
```

```
Speed bar:  (empty) PRACTICALLY IMPOSSIBLE 💀
```

---

### 📈 Growth Comparison Table — "How many steps for n items?"

```
┌─────────────┬────────┬────────────┬────────────┬──────────────────────┐
│ Complexity  │  n=5   │   n=10     │   n=100    │       n=1000         │
├─────────────┼────────┼────────────┼────────────┼──────────────────────┤
│ O(1)        │   1    │     1      │      1     │           1          │
│ O(log n)    │   3    │     4      │      7     │          10          │
│ O(n)        │   5    │    10      │    100     │       1,000          │
│ O(n log n)  │  12    │    33      │    665     │      10,000          │
│ O(n²)       │  25    │   100      │ 10,000     │   1,000,000          │
│ O(2ⁿ)       │  32    │  1,024     │ 10³⁰ 🔥   │        ♾️ 🔥         │
│ O(n!)       │ 120    │ 3,628,800  │    ♾️ 💀  │        ♾️ 💀         │
└─────────────┴────────┴────────────┴────────────┴──────────────────────┘

🟢 = Fast and practical   🟡 = Acceptable   🔴 = Slow   💀 = Avoid
```

---

### 🏎️ The Race Analogy — All Together

Imagine 7 cars racing to finish `1000 tasks`:

```
🏎️  O(1)        ────────────────────── FINISHED (1 step)
🏎️  O(log n)    ────────────────────── FINISHED (10 steps)

🚗  O(n)        ─────────────────────────────────────── (1,000 steps)

🚕  O(n log n)  ──────────────────────────────────────────────── (10,000 steps)

🛵  O(n²)       still going... (1,000,000 steps)

🚲  O(2ⁿ)       hasn't even started... (more steps than atoms in universe)

🐢  O(n!)       will never finish in your lifetime...
```

---

### 🧭 Quick Decision Guide — Which is OK to use?

```
Input Size (n)     Acceptable Complexities
──────────────     ────────────────────────────────────────────
n ≤ 10             ✅ Anything works — even O(n!) is fine
n ≤ 100            ✅ O(n²) is okay
n ≤ 1,000          ✅ O(n log n) is fine, O(n²) starts to slow
n ≤ 100,000        ⚠️  Need O(n log n) or better
n ≤ 1,000,000      🚨 Need O(n) or O(log n)
n > 10,000,000     🚀 Need O(1) or O(log n) only
```

---

### 🎯 One-Line Memory Trick for Each

| Notation | Memory Hook | Real World |
|---|---|---|
| **O(1)** | "It's always 1 step, no matter what" | Light switch |
| **O(log n)** | "Keeps cutting problem in half" | Dictionary search |
| **O(n)** | "One step for every item" | Reading a book cover to cover |
| **O(n log n)** | "Smarter sorting — divide and conquer" | Sorting a deck of cards |
| **O(n²)** | "Everyone shakes hands with everyone" | Party handshake |
| **O(2ⁿ)** | "Doubles every step" | Chain letter |
| **O(n!)** | "Try every possible arrangement" | Seating arrangement |

---

## 3. Arrays

### 🟢 Beginner

An **array** is a collection of elements stored in **contiguous memory** with **index-based access**.

```javascript
// JavaScript Array
const fruits = ["apple", "banana", "cherry"];

// Access by index (0-based)
console.log(fruits[0]); // "apple"
console.log(fruits[2]); // "cherry"

// Length
console.log(fruits.length); // 3
```

```python
# Python List (dynamic array)
fruits = ["apple", "banana", "cherry"]
print(fruits[0])   # "apple"
print(fruits[-1])  # "cherry" (negative indexing!)
```

### Core Operations

```javascript
const arr = [10, 20, 30, 40, 50];

// ✅ READ — O(1)
console.log(arr[2]); // 30

// ✅ UPDATE — O(1)
arr[2] = 99;
console.log(arr); // [10, 20, 99, 40, 50]

// ✅ PUSH (add to end) — O(1) amortized
arr.push(60);
console.log(arr); // [10, 20, 99, 40, 50, 60]

// ✅ POP (remove from end) — O(1)
arr.pop();
console.log(arr); // [10, 20, 99, 40, 50]

// ⚠️ UNSHIFT (add to start) — O(n) — shifts all elements
arr.unshift(0);
console.log(arr); // [0, 10, 20, 99, 40, 50]

// ⚠️ SHIFT (remove from start) — O(n)
arr.shift();
console.log(arr); // [10, 20, 99, 40, 50]

// ⚠️ SPLICE (insert/remove at index) — O(n)
arr.splice(2, 1, 777); // at index 2, remove 1, insert 777
console.log(arr); // [10, 20, 777, 40, 50]
```

### 🟡 Intermediate — Iteration Patterns

```javascript
const nums = [3, 1, 4, 1, 5, 9, 2, 6];

// forEach
nums.forEach((n, i) => console.log(`${i}: ${n}`));

// map — transform each element → returns NEW array
const doubled = nums.map(n => n * 2);
// [6, 2, 8, 2, 10, 18, 4, 12]

// filter — keep elements matching condition
const evens = nums.filter(n => n % 2 === 0);
// [4, 2, 6]

// reduce — collapse into single value
const sum = nums.reduce((acc, n) => acc + n, 0);
// 31

// find — first match
const firstBig = nums.find(n => n > 5);
// 9

// some / every
const hasNegative = nums.some(n => n < 0);   // false
const allPositive = nums.every(n => n > 0);   // true

// sort (WARNING: sorts in-place, default is string sort!)
const sorted = [...nums].sort((a, b) => a - b);
// [1, 1, 2, 3, 4, 5, 6, 9]
```

### 🔴 Advanced — Two Pointer Technique

A classic pattern to solve array problems in **O(n)** instead of O(n²).

**Problem:** Find two numbers in a sorted array that sum to a target.

```javascript
// O(n²) approach — Brute Force
function twoSumBrute(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[i] + arr[j] === target) return [i, j];
    }
  }
  return null;
}

// O(n) approach — Two Pointer (only works on SORTED array)
function twoSumPointers(arr, target) {
  let left = 0;
  let right = arr.length - 1;

  while (left < right) {
    const sum = arr[left] + arr[right];

    if (sum === target) {
      return [left, right];       // ✅ found!
    } else if (sum < target) {
      left++;                     // need bigger sum → move left right
    } else {
      right--;                    // need smaller sum → move right left
    }
  }
  return null;
}

const arr = [1, 2, 3, 4, 6, 8, 11];
console.log(twoSumPointers(arr, 10)); // [3, 5] → arr[3]+arr[5] = 4+6 = 10? No → [2,4] → 3+6=9? 
// Let's trace: left=0(1), right=6(11) → 12 > 10 → right--
// left=0(1), right=5(8) → 9 < 10 → left++
// left=1(2), right=5(8) → 10 = 10 ✅ → [1, 5]
```

### 🚀 Super Advanced — Sliding Window

Used when you need to find a **subarray** that satisfies a condition.

**Problem:** Maximum sum of any subarray of size k.

```javascript
function maxSubarraySum(arr, k) {
  if (arr.length < k) return null;

  // Step 1: Calculate sum of first window
  let windowSum = 0;
  for (let i = 0; i < k; i++) {
    windowSum += arr[i];
  }

  let maxSum = windowSum;

  // Step 2: Slide the window — add right, remove left
  for (let i = k; i < arr.length; i++) {
    windowSum = windowSum + arr[i] - arr[i - k]; // Add new, remove old
    maxSum = Math.max(maxSum, windowSum);
  }

  return maxSum;
}

const arr = [2, 1, 5, 1, 3, 2];
console.log(maxSubarraySum(arr, 3)); // 9 → [5, 1, 3]

// Window trace:
// [2,1,5] = 8
// [1,5,1] = 7
// [5,1,3] = 9 ← max
// [1,3,2] = 6
```

### Complexity Table

| Operation | Time | Space |
|---|---|---|
| Access by index | O(1) | O(1) |
| Search (unsorted) | O(n) | O(1) |
| Search (sorted, binary) | O(log n) | O(1) |
| Insert at end | O(1) amortized | O(1) |
| Insert at start/middle | O(n) | O(1) |
| Delete at end | O(1) | O(1) |
| Delete at start/middle | O(n) | O(1) |

---

## 4. Strings

### 🟢 Beginner

Strings are essentially **character arrays** under the hood.

```javascript
const str = "Hello, World!";

// Access character
console.log(str[0]);      // "H"
console.log(str.charAt(7)); // "W"

// Length
console.log(str.length);  // 13

// Common methods
console.log(str.toUpperCase());        // "HELLO, WORLD!"
console.log(str.toLowerCase());        // "hello, world!"
console.log(str.includes("World"));    // true
console.log(str.startsWith("Hello"));  // true
console.log(str.endsWith("!"));        // true
console.log(str.indexOf("o"));         // 4
console.log(str.slice(7, 12));         // "World"
console.log(str.split(", "));          // ["Hello", "World!"]
console.log(str.replace("World", "JS")); // "Hello, JS!"
console.log(str.trim());               // removes whitespace
```

### 🟡 Intermediate — String as Array of Chars

```javascript
// ⚠️ Strings in JS are IMMUTABLE
// You can't do: str[0] = "h";  // This silently fails!

// To manipulate, convert to array:
const reversed = "hello".split("").reverse().join("");
// "olleh"

// Check if palindrome
function isPalindrome(s) {
  s = s.toLowerCase().replace(/[^a-z0-9]/g, ""); // clean string
  let l = 0, r = s.length - 1;
  while (l < r) {
    if (s[l] !== s[r]) return false;
    l++; r--;
  }
  return true;
}

console.log(isPalindrome("A man, a plan, a canal: Panama")); // true
```

### 🔴 Advanced — Anagram Check

```javascript
// O(n) using character frequency map
function isAnagram(s1, s2) {
  if (s1.length !== s2.length) return false;

  const freq = {};

  for (const ch of s1) {
    freq[ch] = (freq[ch] || 0) + 1; // count up
  }

  for (const ch of s2) {
    if (!freq[ch]) return false;     // char missing or over-used
    freq[ch]--;                      // count down
  }

  return true;
}

console.log(isAnagram("listen", "silent")); // true
console.log(isAnagram("hello", "world"));   // false
```

---

## 5. Linked Lists

### 🟢 Beginner — What is it?

A **Linked List** is a chain of **nodes**. Each node contains:
- **data** — the actual value
- **next** — a reference/pointer to the next node

```
[10] → [20] → [30] → [40] → null
 head
```

Unlike arrays, linked list elements are **NOT stored contiguously in memory** — they are scattered, connected by pointers.

### Node Structure

```javascript
// Each node is an object
class Node {
  constructor(value) {
    this.value = value;
    this.next = null; // points to next node (null = end of list)
  }
}

// Manual creation
const n1 = new Node(10);
const n2 = new Node(20);
const n3 = new Node(30);

n1.next = n2;
n2.next = n3;
// n1 → n2 → n3 → null
```

### 🟡 Intermediate — Full Singly Linked List

```javascript
class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  // ✅ Append to end — O(n)
  append(value) {
    const newNode = new Node(value);

    if (!this.head) {
      this.head = newNode; // empty list
      this.size++;
      return;
    }

    let current = this.head;
    while (current.next) {       // traverse to last node
      current = current.next;
    }
    current.next = newNode;      // attach new node
    this.size++;
  }

  // ✅ Prepend to start — O(1)
  prepend(value) {
    const newNode = new Node(value);
    newNode.next = this.head;    // new node points to old head
    this.head = newNode;         // update head
    this.size++;
  }

  // ✅ Delete by value — O(n)
  delete(value) {
    if (!this.head) return;

    // Special case: delete head
    if (this.head.value === value) {
      this.head = this.head.next;
      this.size--;
      return;
    }

    let current = this.head;
    while (current.next) {
      if (current.next.value === value) {
        current.next = current.next.next; // skip the node to delete
        this.size--;
        return;
      }
      current = current.next;
    }
  }

  // ✅ Print list
  print() {
    const values = [];
    let current = this.head;
    while (current) {
      values.push(current.value);
      current = current.next;
    }
    console.log(values.join(" → ") + " → null");
  }
}

// Usage
const list = new LinkedList();
list.append(10);
list.append(20);
list.append(30);
list.prepend(5);
list.print();    // 5 → 10 → 20 → 30 → null
list.delete(20);
list.print();    // 5 → 10 → 30 → null
```

### 🔴 Advanced — Reverse a Linked List

This is one of the most asked interview questions!

```javascript
// Iterative approach — O(n) time, O(1) space
function reverseList(head) {
  let prev = null;
  let curr = head;

  while (curr) {
    const next = curr.next; // save next node
    curr.next = prev;       // reverse the pointer
    prev = curr;            // move prev forward
    curr = next;            // move curr forward
  }

  return prev; // new head (was the old tail)
}

// Trace:
// null ← [5] [10] → [30] → null
//         ↑
//       prev curr
//
// null ← [5] ← [10] [30] → null
//               ↑
//             prev curr
//
// null ← [5] ← [10] ← [30] null
//                        ↑
//                      prev curr (null → stop)
//
// Return prev = [30] — new head!
```

### 🚀 Super Advanced — Detect Cycle (Floyd's Algorithm)

```javascript
// Floyd's "Tortoise and Hare" algorithm
// Uses two pointers: slow moves 1 step, fast moves 2 steps
// If they meet → cycle exists!

function hasCycle(head) {
  let slow = head;
  let fast = head;

  while (fast && fast.next) {
    slow = slow.next;       // 1 step
    fast = fast.next.next;  // 2 steps

    if (slow === fast) return true; // they met → cycle!
  }

  return false; // fast reached null → no cycle
}

// Find START of cycle
function detectCycleStart(head) {
  let slow = head, fast = head;

  // Phase 1: Find meeting point
  while (fast && fast.next) {
    slow = slow.next;
    fast = fast.next.next;
    if (slow === fast) break;
  }

  if (!fast || !fast.next) return null; // no cycle

  // Phase 2: Move one pointer to head
  // They will meet at cycle start
  slow = head;
  while (slow !== fast) {
    slow = slow.next;
    fast = fast.next; // same speed now
  }

  return slow; // cycle start node
}
```

### Doubly Linked List

```javascript
class DNode {
  constructor(value) {
    this.value = value;
    this.next = null;
    this.prev = null; // ← extra pointer
  }
}

// null ← [5] ↔ [10] ↔ [20] ↔ [30] → null
//  head                        tail

class DoublyLinkedList {
  constructor() {
    this.head = null;
    this.tail = null;
    this.size = 0;
  }

  append(value) {
    const node = new DNode(value);
    if (!this.tail) {
      this.head = this.tail = node;
    } else {
      node.prev = this.tail;
      this.tail.next = node;
      this.tail = node;
    }
    this.size++;
  }

  // O(1) delete from tail (impossible with singly linked list!)
  removeTail() {
    if (!this.tail) return null;
    const val = this.tail.value;
    this.tail = this.tail.prev;
    if (this.tail) this.tail.next = null;
    else this.head = null;
    this.size--;
    return val;
  }
}
```

### Complexity Table

| Operation | Singly | Doubly |
|---|---|---|
| Access by index | O(n) | O(n) |
| Search | O(n) | O(n) |
| Prepend | O(1) | O(1) |
| Append | O(n) | O(1) with tail |
| Delete (known node) | O(n) | O(1) |
| Delete head | O(1) | O(1) |
| Delete tail | O(n) | O(1) |

---

## 6. Stacks

### 🟢 Beginner

A **Stack** follows **LIFO** — Last In, First Out.

```
Think of a stack of plates:
 Push → add plate on top
 Pop  → remove plate from top
```

```
     TOP
  ┌───────┐
  │  30   │  ← push/pop here
  │  20   │
  │  10   │
  └───────┘
```

### Implementation

```javascript
// Using Array (simplest)
class Stack {
  constructor() {
    this.items = [];
  }

  push(item) {
    this.items.push(item); // add to end
  }

  pop() {
    return this.items.pop(); // remove from end → O(1)
  }

  peek() {
    return this.items[this.items.length - 1]; // look at top
  }

  isEmpty() {
    return this.items.length === 0;
  }

  size() {
    return this.items.length;
  }
}

const stack = new Stack();
stack.push(10);
stack.push(20);
stack.push(30);
console.log(stack.peek()); // 30
console.log(stack.pop());  // 30
console.log(stack.pop());  // 20
console.log(stack.size()); // 1
```

### 🟡 Intermediate — Valid Parentheses

Classic stack problem!

```javascript
// Problem: Given string of brackets, check if they are valid
// "()[]{}"   → valid ✅
// "([)]"     → invalid ❌
// "{[]}"     → valid ✅

function isValid(s) {
  const stack = [];
  const map = { ")": "(", "}": "{", "]": "[" };

  for (const ch of s) {
    if ("({[".includes(ch)) {
      stack.push(ch);          // opening → push to stack
    } else {
      const top = stack.pop(); // closing → check if matches top
      if (top !== map[ch]) return false;
    }
  }

  return stack.length === 0; // must be empty at end
}

console.log(isValid("()[]{}")); // true
console.log(isValid("([)]"));   // false
console.log(isValid("{[]}"));   // true
```

### 🔴 Advanced — Min Stack (O(1) min retrieval)

```javascript
// Design a stack that supports push, pop, peek AND getMin in O(1)

class MinStack {
  constructor() {
    this.stack = [];
    this.minStack = []; // tracks minimums
  }

  push(val) {
    this.stack.push(val);
    // push to minStack only if val <= current min
    const min = this.minStack.length === 0
      ? val
      : Math.min(val, this.minStack[this.minStack.length - 1]);
    this.minStack.push(min);
  }

  pop() {
    this.stack.pop();
    this.minStack.pop(); // sync removal
  }

  top() {
    return this.stack[this.stack.length - 1];
  }

  getMin() {
    return this.minStack[this.minStack.length - 1]; // O(1)!
  }
}

const ms = new MinStack();
ms.push(5);
ms.push(3);
ms.push(7);
ms.push(2);
console.log(ms.getMin()); // 2
ms.pop();
console.log(ms.getMin()); // 3
```

---

## 7. Queues

### 🟢 Beginner

A **Queue** follows **FIFO** — First In, First Out.

```
Think of a ticket counter queue:
  Enqueue → join at back
  Dequeue → leave from front
```

```
  FRONT                    BACK
  ┌────┬────┬────┬────┐
  │ 10 │ 20 │ 30 │ 40 │
  └────┴────┴────┴────┘
   dequeue              enqueue
```

### Implementation

```javascript
class Queue {
  constructor() {
    this.items = {};   // Object for O(1) dequeue
    this.front = 0;
    this.back = 0;
  }

  enqueue(item) {
    this.items[this.back] = item;
    this.back++;
  }

  dequeue() {
    if (this.isEmpty()) return undefined;
    const item = this.items[this.front];
    delete this.items[this.front];
    this.front++;
    return item;
  }

  peek() {
    return this.items[this.front];
  }

  isEmpty() {
    return this.front === this.back;
  }

  size() {
    return this.back - this.front;
  }
}

const q = new Queue();
q.enqueue("Alice");
q.enqueue("Bob");
q.enqueue("Charlie");
console.log(q.dequeue()); // "Alice"
console.log(q.peek());    // "Bob"
console.log(q.size());    // 2
```

### 🟡 Intermediate — Deque (Double-Ended Queue)

```javascript
// Can add/remove from BOTH ends
class Deque {
  constructor() {
    this.items = [];
  }
  addFront(item) { this.items.unshift(item); }     // O(n)
  addBack(item)  { this.items.push(item); }         // O(1)
  removeFront()  { return this.items.shift(); }     // O(n)
  removeBack()   { return this.items.pop(); }       // O(1)
  peekFront()    { return this.items[0]; }
  peekBack()     { return this.items[this.items.length - 1]; }
  isEmpty()      { return this.items.length === 0; }
}

// Better Deque using doubly linked list → all O(1) operations
```

### 🔴 Advanced — BFS with Queue (Level Order Tree Traversal)

```javascript
function levelOrder(root) {
  if (!root) return [];

  const result = [];
  const queue = [root];          // start with root

  while (queue.length > 0) {
    const levelSize = queue.length;
    const currentLevel = [];

    for (let i = 0; i < levelSize; i++) {
      const node = queue.shift();          // dequeue
      currentLevel.push(node.val);

      if (node.left)  queue.push(node.left);   // enqueue children
      if (node.right) queue.push(node.right);
    }

    result.push(currentLevel);             // save this level
  }

  return result;
}
// Input tree:      3
//                /   \
//               9    20
//                   /  \
//                  15   7
//
// Output: [[3], [9, 20], [15, 7]]
```

---

## 8. Hash Tables (Hash Maps)

### 🟢 Beginner

A **Hash Table** (or Hash Map) stores **key-value pairs** and provides O(1) average access.

```
Key  →  Hash Function  →  Index  →  Value

"name" → hash() → 42 → "Alice"
"age"  → hash() → 17 → 30
```

```javascript
// JavaScript built-in Map
const map = new Map();

map.set("name", "Alice");
map.set("age", 30);
map.set("city", "Chennai");

console.log(map.get("name"));    // "Alice"
console.log(map.has("city"));    // true
console.log(map.size);           // 3
map.delete("age");
console.log(map.size);           // 2

// Iterate
for (const [key, value] of map) {
  console.log(`${key}: ${value}`);
}

// Plain Object (also acts as hash map for string keys)
const obj = {};
obj["name"] = "Alice";
obj["age"] = 30;
console.log(obj["name"]);        // "Alice"
console.log(Object.keys(obj));   // ["name", "age"]
```

### 🟡 Intermediate — Frequency Counter Pattern

```javascript
// Most hash map problems use this pattern:
// Build a frequency map → use it to answer questions

// Problem: Find first non-repeating character in string
function firstUniqueChar(s) {
  const freq = {};

  // Step 1: Count frequencies
  for (const ch of s) {
    freq[ch] = (freq[ch] || 0) + 1;
  }

  // Step 2: Find first with count = 1
  for (let i = 0; i < s.length; i++) {
    if (freq[s[i]] === 1) return i;
  }

  return -1;
}

console.log(firstUniqueChar("leetcode"));   // 0 → 'l'
console.log(firstUniqueChar("loveleetcode")); // 2 → 'v'
```

### 🔴 Advanced — Build a Hash Table from Scratch

```javascript
class HashTable {
  constructor(size = 53) {
    this.table = new Array(size);
    this.size = size;
  }

  // Simple hash function
  _hash(key) {
    let hash = 0;
    const PRIME = 31;
    for (let i = 0; i < Math.min(key.length, 100); i++) {
      hash = (hash * PRIME + key.charCodeAt(i)) % this.size;
    }
    return hash;
  }

  // Set key-value (with chaining for collision handling)
  set(key, value) {
    const idx = this._hash(key);
    if (!this.table[idx]) this.table[idx] = [];

    // Update if key already exists
    for (const pair of this.table[idx]) {
      if (pair[0] === key) { pair[1] = value; return; }
    }

    this.table[idx].push([key, value]);
  }

  // Get value by key
  get(key) {
    const idx = this._hash(key);
    const bucket = this.table[idx];
    if (!bucket) return undefined;

    for (const [k, v] of bucket) {
      if (k === key) return v;
    }
    return undefined;
  }

  // Get all keys
  keys() {
    const result = [];
    for (const bucket of this.table) {
      if (bucket) {
        for (const [key] of bucket) result.push(key);
      }
    }
    return result;
  }
}

const ht = new HashTable();
ht.set("name", "Alice");
ht.set("age", 30);
console.log(ht.get("name")); // "Alice"
console.log(ht.keys());      // ["name", "age"]
```

### Collision Handling Strategies

```
1. Chaining (above) — each bucket stores a list
   Pros: Simple, handles many collisions
   Cons: Extra memory for lists

2. Open Addressing (Linear Probing)
   If slot taken → try next slot: idx+1, idx+2...
   Pros: Cache-friendly, no extra allocations
   Cons: Clustering problem
```

---

## 9. Sets

### 🟢 Beginner

A **Set** stores **unique values only** — no duplicates.

```javascript
const set = new Set();

set.add(10);
set.add(20);
set.add(10);  // duplicate — ignored!
set.add(30);

console.log(set.size);       // 3 (not 4)
console.log(set.has(20));    // true
console.log(set.has(99));    // false

set.delete(20);
console.log([...set]);       // [10, 30]

// Remove duplicates from array
const arr = [1, 2, 2, 3, 3, 3, 4];
const unique = [...new Set(arr)];
console.log(unique); // [1, 2, 3, 4]
```

### 🟡 Intermediate — Set Operations

```javascript
const A = new Set([1, 2, 3, 4, 5]);
const B = new Set([3, 4, 5, 6, 7]);

// Union — all elements from both
const union = new Set([...A, ...B]);
// {1, 2, 3, 4, 5, 6, 7}

// Intersection — common elements
const intersection = new Set([...A].filter(x => B.has(x)));
// {3, 4, 5}

// Difference — in A but not in B
const difference = new Set([...A].filter(x => !B.has(x)));
// {1, 2}
```

---

## 10. Trees

### 🟢 Beginner — Concepts

A **Tree** is a hierarchical data structure.

```
         ROOT
          A
        /   \
       B     C
      / \     \
     D   E     F
```

Key terms:
- **Root** — top node (A)
- **Leaf** — node with no children (D, E, F)
- **Height** — longest path from root to leaf (2)
- **Depth** — distance from root (B has depth 1)
- **Parent / Child** — A is parent of B and C
- **Subtree** — any node + its descendants

```javascript
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

// Binary tree — each node has AT MOST 2 children
const root = new TreeNode(1);
root.left = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left = new TreeNode(4);
root.left.right = new TreeNode(5);

//       1
//      / \
//     2   3
//    / \
//   4   5
```

### Tree Traversals

```javascript
// 1. In-Order (Left → Root → Right) → gives SORTED output for BST
function inOrder(node) {
  if (!node) return;
  inOrder(node.left);
  console.log(node.value);
  inOrder(node.right);
}

// 2. Pre-Order (Root → Left → Right) → good for copying/serializing
function preOrder(node) {
  if (!node) return;
  console.log(node.value);
  preOrder(node.left);
  preOrder(node.right);
}

// 3. Post-Order (Left → Right → Root) → good for deletion
function postOrder(node) {
  if (!node) return;
  postOrder(node.left);
  postOrder(node.right);
  console.log(node.value);
}

// For tree above:
// In-Order:   4, 2, 5, 1, 3
// Pre-Order:  1, 2, 4, 5, 3
// Post-Order: 4, 5, 2, 3, 1
```

---

## 11. Binary Search Tree (BST)

### 🟡 Intermediate

A **BST** is a binary tree where:
- **Left subtree** has values **less than** root
- **Right subtree** has values **greater than** root

```
       8
      / \
     3   10
    / \    \
   1   6    14
      / \   /
     4   7 13
```

```javascript
class BST {
  constructor() {
    this.root = null;
  }

  // Insert — O(log n) average, O(n) worst (skewed tree)
  insert(value) {
    const node = new TreeNode(value);

    if (!this.root) {
      this.root = node;
      return;
    }

    let current = this.root;
    while (true) {
      if (value === current.value) return; // no duplicates

      if (value < current.value) {
        if (!current.left) { current.left = node; return; }
        current = current.left;
      } else {
        if (!current.right) { current.right = node; return; }
        current = current.right;
      }
    }
  }

  // Search — O(log n) average
  search(value) {
    let current = this.root;
    while (current) {
      if (value === current.value) return true;
      current = value < current.value ? current.left : current.right;
    }
    return false;
  }

  // Find Min — go left until null
  findMin(node = this.root) {
    while (node.left) node = node.left;
    return node.value;
  }

  // Find Max — go right until null
  findMax(node = this.root) {
    while (node.right) node = node.right;
    return node.value;
  }
}

const bst = new BST();
[8, 3, 10, 1, 6, 14, 4, 7, 13].forEach(v => bst.insert(v));
console.log(bst.search(6));    // true
console.log(bst.search(99));   // false
console.log(bst.findMin());    // 1
console.log(bst.findMax());    // 14
```

---

## 12. Heaps / Priority Queues

### 🟡 Intermediate

A **Heap** is a complete binary tree where:
- **Max-Heap**: Parent ≥ Children (root is maximum)
- **Min-Heap**: Parent ≤ Children (root is minimum)

Stored efficiently as an **array**:

```
Max-Heap tree:        Array representation:
        10            [10, 9, 8, 5, 6, 7, 3, 2, 4, 1]
      /    \           idx: 0  1  2  3  4  5  6  7  8  9
     9      8
    / \    / \
   5   6  7   3
  / \ /
 2  4 1

Formula:
  parent(i)  = Math.floor((i - 1) / 2)
  leftChild  = 2*i + 1
  rightChild = 2*i + 2
```

### Min-Heap Implementation

```javascript
class MinHeap {
  constructor() {
    this.heap = [];
  }

  // Get parent/children indices
  parent(i)     { return Math.floor((i - 1) / 2); }
  leftChild(i)  { return 2 * i + 1; }
  rightChild(i) { return 2 * i + 2; }

  swap(i, j) {
    [this.heap[i], this.heap[j]] = [this.heap[j], this.heap[i]];
  }

  // Insert — O(log n)
  push(val) {
    this.heap.push(val);
    this._bubbleUp(this.heap.length - 1);
  }

  _bubbleUp(i) {
    while (i > 0) {
      const p = this.parent(i);
      if (this.heap[p] > this.heap[i]) {
        this.swap(p, i);  // swap with parent if parent is bigger
        i = p;
      } else break;
    }
  }

  // Get min — O(1)
  peek() {
    return this.heap[0];
  }

  // Remove min — O(log n)
  pop() {
    if (this.heap.length === 0) return null;
    if (this.heap.length === 1) return this.heap.pop();

    const min = this.heap[0];
    this.heap[0] = this.heap.pop(); // move last to top
    this._sinkDown(0);
    return min;
  }

  _sinkDown(i) {
    const n = this.heap.length;
    while (true) {
      let smallest = i;
      const l = this.leftChild(i);
      const r = this.rightChild(i);

      if (l < n && this.heap[l] < this.heap[smallest]) smallest = l;
      if (r < n && this.heap[r] < this.heap[smallest]) smallest = r;

      if (smallest !== i) {
        this.swap(i, smallest);
        i = smallest;
      } else break;
    }
  }

  size() { return this.heap.length; }
}

const heap = new MinHeap();
[5, 3, 8, 1, 2].forEach(v => heap.push(v));
console.log(heap.pop()); // 1
console.log(heap.pop()); // 2
console.log(heap.pop()); // 3
```

### Use Cases
- Dijkstra's shortest path algorithm
- Top K elements problems
- Merge K sorted lists
- Huffman encoding

---

## 13. Graphs

### 🟢 Beginner — Concepts

A **Graph** is a collection of **nodes (vertices)** connected by **edges**.

```
Undirected Graph:         Directed Graph (Digraph):
  A — B                    A → B
  |   |                    ↑   ↓
  D — C                    D ← C
```

Types:
- **Directed / Undirected**
- **Weighted / Unweighted**
- **Cyclic / Acyclic**

### Representation

```javascript
// 1. Adjacency List (most common — space efficient)
const graph = {
  A: ["B", "D"],
  B: ["A", "C"],
  C: ["B", "D"],
  D: ["A", "C"]
};

// 2. Adjacency Matrix (fast edge lookup)
// Index: A=0, B=1, C=2, D=3
const matrix = [
//  A  B  C  D
  [ 0, 1, 0, 1 ],  // A
  [ 1, 0, 1, 0 ],  // B
  [ 0, 1, 0, 1 ],  // C
  [ 1, 0, 1, 0 ],  // D
];
```

### Graph Class

```javascript
class Graph {
  constructor() {
    this.adjacencyList = {};
  }

  addVertex(v) {
    if (!this.adjacencyList[v]) this.adjacencyList[v] = [];
  }

  addEdge(v1, v2) {
    this.adjacencyList[v1].push(v2);
    this.adjacencyList[v2].push(v1); // undirected
  }

  removeEdge(v1, v2) {
    this.adjacencyList[v1] = this.adjacencyList[v1].filter(v => v !== v2);
    this.adjacencyList[v2] = this.adjacencyList[v2].filter(v => v !== v1);
  }
}
```

### 🔴 Advanced — DFS and BFS on Graphs

```javascript
// DFS — Depth First Search (go deep first)
function dfs(graph, start, visited = new Set()) {
  visited.add(start);
  console.log(start);

  for (const neighbor of graph[start]) {
    if (!visited.has(neighbor)) {
      dfs(graph, neighbor, visited);
    }
  }
}

// BFS — Breadth First Search (level by level)
function bfs(graph, start) {
  const visited = new Set([start]);
  const queue = [start];

  while (queue.length > 0) {
    const node = queue.shift();
    console.log(node);

    for (const neighbor of graph[node]) {
      if (!visited.has(neighbor)) {
        visited.add(neighbor);
        queue.push(neighbor);
      }
    }
  }
}

const graph = {
  A: ["B", "D"],
  B: ["A", "C"],
  C: ["B", "D"],
  D: ["A", "C"]
};

// DFS from A: A → B → C → D
// BFS from A: A → B → D → C
```

### 🚀 Super Advanced — Dijkstra's Shortest Path

```javascript
function dijkstra(graph, start) {
  const distances = {};
  const visited = new Set();
  const pq = new MinHeap(); // [cost, node]

  // Initialize all distances as Infinity
  for (const node in graph) distances[node] = Infinity;
  distances[start] = 0;
  pq.push([0, start]); // cost, node

  while (pq.size() > 0) {
    const [cost, node] = pq.pop();

    if (visited.has(node)) continue; // already processed
    visited.add(node);

    for (const [neighbor, weight] of graph[node]) {
      const newDist = cost + weight;

      if (newDist < distances[neighbor]) {
        distances[neighbor] = newDist;
        pq.push([newDist, neighbor]);
      }
    }
  }

  return distances;
}

// Weighted graph
const weightedGraph = {
  A: [["B", 1], ["C", 4]],
  B: [["A", 1], ["C", 2], ["D", 5]],
  C: [["A", 4], ["B", 2], ["D", 1]],
  D: [["B", 5], ["C", 1]]
};

// dijkstra(weightedGraph, "A") 
// → { A: 0, B: 1, C: 3, D: 4 }
//   (A→B=1, A→B→C=3, A→B→C→D=4)
```

---

## 14. Tries (Prefix Trees)

### 🔴 Advanced

A **Trie** is a tree-like structure optimized for **string prefix operations**.

```
Words: ["cat", "car", "card", "care", "care", "dog"]

        root
       /    \
      c      d
      |      |
      a      o
     / \     |
    t   r    g
        |
        d  e
```

```javascript
class TrieNode {
  constructor() {
    this.children = {};     // map of char → TrieNode
    this.isEndOfWord = false;
  }
}

class Trie {
  constructor() {
    this.root = new TrieNode();
  }

  // Insert word — O(m) where m = word length
  insert(word) {
    let node = this.root;
    for (const ch of word) {
      if (!node.children[ch]) {
        node.children[ch] = new TrieNode();
      }
      node = node.children[ch];
    }
    node.isEndOfWord = true;
  }

  // Search exact word — O(m)
  search(word) {
    let node = this.root;
    for (const ch of word) {
      if (!node.children[ch]) return false;
      node = node.children[ch];
    }
    return node.isEndOfWord;
  }

  // Check if any word starts with prefix — O(m)
  startsWith(prefix) {
    let node = this.root;
    for (const ch of prefix) {
      if (!node.children[ch]) return false;
      node = node.children[ch];
    }
    return true;
  }

  // Get all words with prefix (autocomplete!)
  autocomplete(prefix) {
    let node = this.root;
    for (const ch of prefix) {
      if (!node.children[ch]) return [];
      node = node.children[ch];
    }

    const results = [];
    this._dfs(node, prefix, results);
    return results;
  }

  _dfs(node, current, results) {
    if (node.isEndOfWord) results.push(current);
    for (const [ch, child] of Object.entries(node.children)) {
      this._dfs(child, current + ch, results);
    }
  }
}

const trie = new Trie();
["cat", "car", "card", "care", "dog"].forEach(w => trie.insert(w));

console.log(trie.search("car"));         // true
console.log(trie.search("ca"));          // false (not a full word)
console.log(trie.startsWith("ca"));      // true
console.log(trie.autocomplete("car"));   // ["car", "card", "care"]
```

---

## 15. Segment Trees

### 🚀 Super Advanced

A **Segment Tree** is used for **range queries** (sum, min, max) and **point updates** in O(log n).

**Problem:** Given array, efficiently answer: "What is the sum of elements from index L to R?"

```javascript
class SegmentTree {
  constructor(arr) {
    this.n = arr.length;
    this.tree = new Array(4 * this.n).fill(0); // 4x for safety
    this.build(arr, 0, 0, this.n - 1);
  }

  // Build — O(n)
  build(arr, node, start, end) {
    if (start === end) {
      this.tree[node] = arr[start]; // leaf node
    } else {
      const mid = Math.floor((start + end) / 2);
      this.build(arr, 2*node+1, start, mid);         // left child
      this.build(arr, 2*node+2, mid+1, end);         // right child
      this.tree[node] = this.tree[2*node+1] + this.tree[2*node+2]; // sum
    }
  }

  // Range Sum Query — O(log n)
  query(node, start, end, l, r) {
    if (r < start || end < l) return 0;              // out of range
    if (l <= start && end <= r) return this.tree[node]; // fully in range

    const mid = Math.floor((start + end) / 2);
    const leftSum  = this.query(2*node+1, start, mid, l, r);
    const rightSum = this.query(2*node+2, mid+1, end, l, r);
    return leftSum + rightSum;
  }

  // Public query interface
  rangeSum(l, r) {
    return this.query(0, 0, this.n - 1, l, r);
  }

  // Point Update — O(log n)
  update(node, start, end, idx, newVal) {
    if (start === end) {
      this.tree[node] = newVal;
    } else {
      const mid = Math.floor((start + end) / 2);
      if (idx <= mid) this.update(2*node+1, start, mid, idx, newVal);
      else            this.update(2*node+2, mid+1, end, idx, newVal);
      this.tree[node] = this.tree[2*node+1] + this.tree[2*node+2];
    }
  }

  pointUpdate(idx, newVal) {
    this.update(0, 0, this.n - 1, idx, newVal);
  }
}

const arr = [1, 3, 5, 7, 9, 11];
const seg = new SegmentTree(arr);

console.log(seg.rangeSum(1, 3));   // 15 → arr[1]+arr[2]+arr[3] = 3+5+7
console.log(seg.rangeSum(0, 5));   // 36 → sum of all
seg.pointUpdate(1, 10);            // arr[1] = 10
console.log(seg.rangeSum(1, 3));   // 22 → 10+5+7
```

---

## 16. Fenwick Tree (Binary Indexed Tree)

### 🚀 Super Advanced

A **Fenwick Tree** (BIT) solves the same range sum problem as Segment Tree but with simpler code and less memory.

```javascript
class FenwickTree {
  constructor(n) {
    this.n = n;
    this.tree = new Array(n + 1).fill(0); // 1-indexed!
  }

  // Add delta to position i — O(log n)
  update(i, delta) {
    for (; i <= this.n; i += i & (-i)) { // i & (-i) = lowest set bit
      this.tree[i] += delta;
    }
  }

  // Prefix sum [1...i] — O(log n)
  prefixSum(i) {
    let sum = 0;
    for (; i > 0; i -= i & (-i)) {       // strip lowest set bit
      sum += this.tree[i];
    }
    return sum;
  }

  // Range sum [l...r] — O(log n)
  rangeSum(l, r) {
    return this.prefixSum(r) - this.prefixSum(l - 1);
  }
}

const arr = [1, 3, 5, 7, 9, 11]; // 1-indexed: indices 1-6
const bit = new FenwickTree(6);

arr.forEach((val, i) => bit.update(i + 1, val)); // 1-indexed build

console.log(bit.rangeSum(2, 4)); // 15 → 3+5+7
console.log(bit.rangeSum(1, 6)); // 36 → sum of all

bit.update(2, 7);                // add 7 to index 2 (arr[1] becomes 10)
console.log(bit.rangeSum(2, 4)); // 22 → 10+5+7
```

---

## 17. Disjoint Set Union (Union-Find)

### 🚀 Super Advanced

**DSU** efficiently answers: "Are these two nodes in the same connected group?"

Used in: network connectivity, Kruskal's MST algorithm, detecting cycles.

```javascript
class DSU {
  constructor(n) {
    this.parent = Array.from({ length: n }, (_, i) => i); // each is its own parent
    this.rank   = new Array(n).fill(0);
    this.count  = n; // number of components
  }

  // Find root with PATH COMPRESSION — O(α(n)) ≈ O(1)
  find(x) {
    if (this.parent[x] !== x) {
      this.parent[x] = this.find(this.parent[x]); // path compression!
    }
    return this.parent[x];
  }

  // Union by RANK — O(α(n)) ≈ O(1)
  union(x, y) {
    const px = this.find(x);
    const py = this.find(y);

    if (px === py) return false; // already in same component

    // Attach smaller rank tree under larger rank tree
    if (this.rank[px] < this.rank[py])      this.parent[px] = py;
    else if (this.rank[px] > this.rank[py]) this.parent[py] = px;
    else { this.parent[py] = px; this.rank[px]++; }

    this.count--;
    return true;
  }

  connected(x, y) {
    return this.find(x) === this.find(y);
  }
}

// Example: Detect cycle in undirected graph
function hasCycleGraph(n, edges) {
  const dsu = new DSU(n);

  for (const [u, v] of edges) {
    if (!dsu.union(u, v)) return true; // already connected → cycle!
  }
  return false;
}

console.log(hasCycleGraph(4, [[0,1],[1,2],[2,0]])); // true (0-1-2-0)
console.log(hasCycleGraph(4, [[0,1],[1,2],[2,3]])); // false (straight line)
```

---

## 18. AVL Trees (Self-Balancing BST)

### 🚀 Super Advanced

A regular BST can degenerate to a linked list (O(n) operations). An **AVL Tree** self-balances using **rotations**.

**Balance Factor** = height(left) - height(right)
- Must be -1, 0, or +1
- If |BF| > 1 → rotate to rebalance

```javascript
class AVLNode {
  constructor(value) {
    this.value = value;
    this.left = this.right = null;
    this.height = 1;
  }
}

class AVLTree {
  height(node) { return node ? node.height : 0; }

  balanceFactor(node) {
    return this.height(node.left) - this.height(node.right);
  }

  updateHeight(node) {
    node.height = 1 + Math.max(this.height(node.left), this.height(node.right));
  }

  // Right Rotation (for Left-Heavy case)
  rotateRight(y) {
    const x  = y.left;
    const T2 = x.right;

    x.right = y;   // y becomes right child of x
    y.left  = T2;  // T2 becomes left child of y

    this.updateHeight(y);
    this.updateHeight(x);
    return x; // x is new root
  }

  // Left Rotation (for Right-Heavy case)
  rotateLeft(x) {
    const y  = x.right;
    const T2 = y.left;

    y.left  = x;
    x.right = T2;

    this.updateHeight(x);
    this.updateHeight(y);
    return y;
  }

  // Insert with balancing — O(log n)
  insert(node, value) {
    if (!node) return new AVLNode(value);

    if (value < node.value)      node.left  = this.insert(node.left, value);
    else if (value > node.value) node.right = this.insert(node.right, value);
    else return node; // duplicate

    this.updateHeight(node);
    const bf = this.balanceFactor(node);

    // 4 cases:
    if (bf > 1 && value < node.left.value)  return this.rotateRight(node); // LL
    if (bf < -1 && value > node.right.value) return this.rotateLeft(node);  // RR
    if (bf > 1 && value > node.left.value) {                                // LR
      node.left = this.rotateLeft(node.left);
      return this.rotateRight(node);
    }
    if (bf < -1 && value < node.right.value) {                              // RL
      node.right = this.rotateRight(node.right);
      return this.rotateLeft(node);
    }

    return node;
  }
}
```

---

## 19. Red-Black Trees

### 🚀 Super Advanced — Concept Overview

Red-Black Trees are another self-balancing BST with these rules:

```
Rules:
1. Every node is RED or BLACK
2. Root is always BLACK
3. NULL leaves are BLACK
4. RED nodes can only have BLACK children (no two red in a row)
5. All paths from any node to its NULL descendants have the SAME number of BLACK nodes
```

```
        13(B)
       /      \
     8(R)     17(R)
    /    \    /    \
  1(B)  11(B) 15(B) 25(B)
```

Red-Black Trees are used in:
- JavaScript `Map` and `Set` (V8 engine)
- Java `TreeMap` and `TreeSet`
- C++ `std::map`
- Linux kernel scheduler

Operations are O(log n) guaranteed due to height constraint:
```
Height ≤ 2 * log₂(n+1)
```

---

## 20. Skip Lists

### 🚀 Super Advanced

A **Skip List** is a probabilistic data structure that allows fast search like a BST, but built on linked lists.

```
Level 3:  1 ─────────────────────────── 17
Level 2:  1 ─────── 7 ─────────── 17
Level 1:  1 ─── 4 ─ 7 ─── 11 ─── 17 ── 25
Level 0:  1 ─ 3─ 4 ─ 7 ─ 9─ 11 ─ 14─17 ─ 21 ─ 25
```

```javascript
class SkipListNode {
  constructor(value, level) {
    this.value = value;
    this.forward = new Array(level + 1).fill(null);
  }
}

class SkipList {
  constructor(maxLevel = 16, p = 0.5) {
    this.maxLevel = maxLevel;
    this.p = p;                                   // probability of level-up
    this.header = new SkipListNode(-Infinity, maxLevel);
    this.level = 0;
  }

  randomLevel() {
    let level = 0;
    while (Math.random() < this.p && level < this.maxLevel) level++;
    return level;
  }

  // Search — O(log n) average
  search(target) {
    let curr = this.header;
    for (let i = this.level; i >= 0; i--) {
      while (curr.forward[i] && curr.forward[i].value < target) {
        curr = curr.forward[i]; // jump ahead on this level
      }
    }
    curr = curr.forward[0];
    return curr && curr.value === target;
  }

  // Insert — O(log n) average
  insert(value) {
    const update = new Array(this.maxLevel + 1).fill(null);
    let curr = this.header;

    for (let i = this.level; i >= 0; i--) {
      while (curr.forward[i] && curr.forward[i].value < value) {
        curr = curr.forward[i];
      }
      update[i] = curr;
    }

    const newLevel = this.randomLevel();
    if (newLevel > this.level) {
      for (let i = this.level + 1; i <= newLevel; i++) update[i] = this.header;
      this.level = newLevel;
    }

    const newNode = new SkipListNode(value, newLevel);
    for (let i = 0; i <= newLevel; i++) {
      newNode.forward[i] = update[i].forward[i];
      update[i].forward[i] = newNode;
    }
  }
}
```

---

## 21. Bloom Filters

### 🚀 Super Advanced — Concept

A **Bloom Filter** is a space-efficient probabilistic structure used to test whether an element is in a set. It can say:
- **"Definitely NOT in set"** — 100% certain
- **"Possibly in set"** — may have false positives

Used by: Google Chrome (malicious URL detection), Redis (avoid cache misses), Databases (skip unnecessary disk lookups).

```javascript
// Conceptual implementation
class BloomFilter {
  constructor(size = 1000, numHashes = 3) {
    this.size = size;
    this.bits = new Uint8Array(size); // bit array
    this.numHashes = numHashes;
  }

  // k different hash functions (using seed variation)
  _hash(value, seed) {
    let hash = seed;
    for (let i = 0; i < value.length; i++) {
      hash = (hash * 31 + value.charCodeAt(i)) % this.size;
    }
    return Math.abs(hash);
  }

  add(value) {
    for (let i = 0; i < this.numHashes; i++) {
      const idx = this._hash(value, i * 7919); // different seeds
      this.bits[idx] = 1;
    }
  }

  contains(value) {
    for (let i = 0; i < this.numHashes; i++) {
      const idx = this._hash(value, i * 7919);
      if (!this.bits[idx]) return false; // definitely not present
    }
    return true; // possibly present (may be false positive)
  }
}

const bf = new BloomFilter();
bf.add("apple");
bf.add("banana");

console.log(bf.contains("apple"));   // true (definitely present)
console.log(bf.contains("cherry"));  // false (definitely not)
console.log(bf.contains("mango"));   // likely false, but could be true positive
```

---

## 22. Summary Cheat Sheet

### Time Complexity at a Glance

| Data Structure | Access | Search | Insert | Delete | Space |
|---|---|---|---|---|---|
| Array | O(1) | O(n) | O(n) | O(n) | O(n) |
| Linked List | O(n) | O(n) | O(1)* | O(1)* | O(n) |
| Stack | O(n) | O(n) | O(1) | O(1) | O(n) |
| Queue | O(n) | O(n) | O(1) | O(1) | O(n) |
| Hash Table | N/A | O(1) avg | O(1) avg | O(1) avg | O(n) |
| BST (balanced) | O(log n) | O(log n) | O(log n) | O(log n) | O(n) |
| Heap | O(1) top | O(n) | O(log n) | O(log n) | O(n) |
| Trie | O(m) | O(m) | O(m) | O(m) | O(n·m) |
| Segment Tree | O(1) | O(log n) | O(log n) | O(log n) | O(n) |

*At known node position

### When to Use What

| Scenario | Best Data Structure |
|---|---|
| Fast index access | Array |
| Frequent insert/delete at front | Linked List |
| Undo/Redo, function call stack | Stack |
| Job scheduling, BFS | Queue |
| Fast key-value lookup | Hash Map |
| Sorted data, range queries | BST |
| "Find minimum/maximum" quickly | Heap |
| Autocomplete, spell check | Trie |
| Range sum/min/max with updates | Segment Tree |
| Connected components, cycles | Union-Find (DSU) |
| Membership check, large datasets | Bloom Filter |
| Network, relationships | Graph |

---

> 💡 **Pro Tip:** Always analyze the TIME and SPACE complexity of your solution before coding in interviews. Then optimize step by step: Brute Force → Better → Optimal.

---

*Made with ❤️ for developers — from beginner to super advanced*
