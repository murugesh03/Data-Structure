# 📚 Data Structures — The Complete Visual Guide

### Every Concept Explained with Real-Life Stories, Visuals & Code

> **Stack:** JavaScript / TypeScript  
> **Style:** 🧠 Story-first → 👁️ Visual → 🔧 How it works → 💻 Code → ⏱️ Speed → 🎯 When to use  
> **Level:** Absolute Beginner → Super Advanced

-----

## 📋 Table of Contents

1. [What is a Data Structure?](#1-what-is-a-data-structure)
1. [Big O Notation — Time Complexity](#2-big-o-notation--time-complexity)
1. [Arrays](#3-arrays)
1. [Strings](#4-strings)
1. [Linked Lists](#5-linked-lists)
1. [Stacks](#6-stacks)
1. [Queues](#7-queues)
1. [Hash Tables (Hash Maps)](#8-hash-tables-hash-maps)
1. [Sets](#9-sets)
1. [Trees](#10-trees)
1. [Binary Search Tree (BST)](#11-binary-search-tree-bst)
1. [Heaps / Priority Queues](#12-heaps--priority-queues)
1. [Graphs](#13-graphs)
1. [Tries (Prefix Trees)](#14-tries-prefix-trees)
1. [Segment Trees](#15-segment-trees)
1. [Fenwick Tree (Binary Indexed Tree)](#16-fenwick-tree-binary-indexed-tree)
1. [Disjoint Set Union (Union-Find)](#17-disjoint-set-union-union-find)
1. [AVL Trees (Self-Balancing BST)](#18-avl-trees-self-balancing-bst)
1. [Red-Black Trees](#19-red-black-trees)
1. [Skip Lists](#20-skip-lists)
1. [Bloom Filters](#21-bloom-filters)
1. [Master Cheat Sheet](#22-master-cheat-sheet)

-----

## 1. What is a Data Structure?

### 🧠 The Story

Imagine you just moved into a new house and you have 500 books to store.

You have three choices:

```
Option A — Dump them all on the floor
  → Finding a book = search through 500 books one by one 😩

Option B — Stack them in a single pile
  → Finding a book = dig from the top 📚

Option C — Sort by subject on labelled shelves
  → Finding a book = go to the right shelf, find instantly ✅
```

All three options **store** the same 500 books. But only one lets you **find and use** them efficiently. That choice of how you organize the books — that is a **data structure**.

A data structure is a **decision about how to organize data** so that you can do things with it quickly.

-----

### 👁️ Visual — Why Organization Matters

```
❌ No structure (just a pile)
   [book][book][book][book][book][book]...[book]  500 books
   Want "Harry Potter"? Check every. single. one.

✅ With structure (named shelves)
   Shelf "Fiction A-M" → [book][book][book]...  ~30 books
   Want "Harry Potter"? Go to Fiction A-M shelf → done in seconds
```

-----

### 🗂️ The 8 Core Data Structures — One-Line Each

```
┌─────────────────────┬─────────────────────────────────────────────────┐
│ Data Structure      │ Real-Life Equivalent                             │
├─────────────────────┼─────────────────────────────────────────────────┤
│ Array               │ Numbered seats in a cinema row                  │
│ Linked List         │ Train carriages connected by couplings           │
│ Stack               │ A stack of plates — add/remove from top only     │
│ Queue               │ People waiting in line at a bank                 │
│ Hash Table          │ Numbered locker room — know the locker, instant  │
│ Tree                │ A family tree — parent → children                │
│ Graph               │ A city road map — locations + roads              │
│ Heap                │ Hospital ER triage — most critical served first  │
└─────────────────────┴─────────────────────────────────────────────────┘
```

-----

### 🎯 Why You MUST Learn This

```
Same task. Two different data structures. Wildly different outcomes:

Finding a contact in an unsorted list of 1,000,000 people:
  Array (unsorted)  → check up to 1,000,000 entries → 10 seconds
  Hash Table        → check exactly 1 entry          → 0.000001 seconds

The data is identical. The structure changes everything.
```

-----

## 2. Big O Notation — Time Complexity

### 🧠 The Core Question Big O Answers

> “If I give my program **10× more data**, does it take 10× longer? 100× longer? Or the same time?”

Big O is just a letter grade for speed. Nothing more.

-----

### 🌈 The Complexity Ladder

```
  BEST ◄──────────────────────────────────────────────► WORST

  O(1)   O(log n)   O(n)   O(n log n)   O(n²)   O(2ⁿ)   O(n!)
   🟢      🟢        🟡       🟡           🔴       💀       ☠️
```

-----

### 🎭 One Story Per Complexity

#### O(1) — The Light Switch

```
Flipping a light switch takes 1 second.
1-room house?    → 1 second
100-room house?  → 1 second
n doesn't matter. Always instant.
```

#### O(log n) — The Dictionary Trick

```
Finding "Zebra" in a dictionary:
  Open to middle → "M" section → too early → jump to 3/4 mark
  Each step cuts remaining pages in HALF.
  1,000 pages   → ~10 steps
  1,000,000 pages → ~20 steps  ← barely changes!
```

#### O(n) — The Lost Key

```
Lost your key somewhere in the house.
Check room 1 → room 2 → room 3 → ...
5 rooms  → 5 checks
50 rooms → 50 checks   ← grows at same rate as n
```

#### O(n²) — The Party Handshake

```
Every guest shakes hands with every other guest.
5  guests →   20 handshakes
10 guests →   90 handshakes
20 guests →  380 handshakes  ← explodes!
```

#### O(2ⁿ) — The WhatsApp Chain

```
You forward to 2 friends. Each forwards to 2 more.
Step 10 → 1,024 people
Step 30 → 1,073,741,824 people  ← impossible!
```

-----

### 📈 Growth Table — Exact Numbers

```
┌─────────────┬────────┬────────┬──────────┬──────────────────┐
│ Complexity  │  n=5   │  n=10  │  n=100   │     n=1000       │
├─────────────┼────────┼────────┼──────────┼──────────────────┤
│ O(1)        │    1   │    1   │      1   │           1      │
│ O(log n)    │    3   │    4   │      7   │          10      │
│ O(n)        │    5   │   10   │    100   │       1,000      │
│ O(n log n)  │   12   │   33   │    665   │      10,000      │
│ O(n²)       │   25   │  100   │ 10,000   │   1,000,000      │
│ O(2ⁿ)       │   32   │ 1,024  │  10³⁰ 🔥 │         ♾️ 🔥   │
│ O(n!)       │  120   │  3.6M  │   ♾️ ☠️  │         ♾️ ☠️   │
└─────────────┴────────┴────────┴──────────┴──────────────────┘
```

-----

### 🏎️ The Race — All at n=20

```
O(1)        ▓  1 step          "Done before you blinked"
O(log n)    ▓▓ 4 steps         "Lightning fast"
O(n)        ▓▓▓▓▓▓▓ 20 steps   "Reasonable"
O(n log n)  ▓▓▓▓▓▓▓▓▓ 80 steps "Still fine"
O(n²)       ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ 400 steps  "Getting slow"
O(2ⁿ)       [bar doesn't fit on screen] 1,048,576 steps  "Unusable"
O(n!)       [bar doesn't fit in the universe]              "Never"
```

-----

### 💡 4 Rules to Calculate Big O Yourself

```javascript
// Rule 1: One loop = O(n)
for (let i = 0; i < n; i++) { ... }           // O(n)

// Rule 2: Loop inside loop = O(n²)
for (let i = 0; i < n; i++) {
  for (let j = 0; j < n; j++) { ... }         // O(n²)
}

// Rule 3: Halving each step = O(log n)
while (n > 1) { n = Math.floor(n / 2); }      // O(log n)

// Rule 4: Drop constants, keep biggest term
// O(2n)     → O(n)
// O(n + 50) → O(n)
// O(n² + n) → O(n²)   ← n² dominates
```

-----

## 3. Arrays

### 🧠 The Story

Think of a **cinema row with numbered seats**.

```
Seat:  [ 1 ][ 2 ][ 3 ][ 4 ][ 5 ][ 6 ][ 7 ][ 8 ][ 9 ][10]
Data:  [ 🎬 ][ 📺 ][ 🎭 ][ 🎵 ][ 🎮 ][ 📚 ][ 🎨 ][ 🏀 ][ 🍕 ][ 🚗 ]
```

Key facts about cinema seats:

- Every seat has a **fixed number** (index)
- You can jump directly to **seat 7** without checking seats 1–6
- All seats are **side by side** — no gaps (contiguous memory)
- The row has a **fixed total length**

That’s exactly how an array works in memory.

-----

### 👁️ Visual — Array in Memory

```
Index:    0      1      2      3      4
        ┌──────┬──────┬──────┬──────┬──────┐
Value:  │  10  │  20  │  30  │  40  │  50  │
        └──────┴──────┴──────┴──────┴──────┘
Address: 1000   1004   1008   1012   1016

Each slot is 4 bytes apart (for 32-bit integers).
arr[3] → go to address 1000 + (3 × 4) = 1012 → read 40
One math calculation → instant access! That's why it's O(1).
```

-----

### 🔧 Operations — Step by Step

#### Reading (O(1) — Instant)

```
arr = [10, 20, 30, 40, 50]
Want arr[3]?

Step 1: Calculate memory address = start + (index × size) = 1000 + (3 × 4) = 1012
Step 2: Read value at address 1012 → 40
Done in 1 step no matter how big the array is! ✅
```

#### Inserting at the End (O(1) — Instant)

```
arr = [10, 20, 30, 40, 50]
Push 60:

Before: [10][20][30][40][50][ ]
Step 1: Write 60 at the next empty slot
After:  [10][20][30][40][50][60] ✅
```

#### Inserting in the Middle (O(n) — Slow)

```
arr = [10, 20, 30, 40, 50]
Insert 99 at index 2:

Before:  [10][20][30][40][50]
                ↑ insert here

Step 1: Shift 50 right  → [10][20][30][40][ ][50]
Step 2: Shift 40 right  → [10][20][30][ ][40][50]
Step 3: Shift 30 right  → [10][20][ ][30][40][50]
Step 4: Write 99        → [10][20][99][30][40][50] ✅

Needed to move 3 elements. For n elements, worst case = n moves → O(n)
```

#### Deleting from the Middle (O(n) — Slow)

```
arr = [10, 20, 30, 40, 50]
Delete index 1 (value 20):

Before:  [10][20][30][40][50]
              ↑ delete this

Step 1: Shift 30 left  → [10][30][30][40][50]
Step 2: Shift 40 left  → [10][30][40][40][50]
Step 3: Shift 50 left  → [10][30][40][50][ ]
After:   [10][30][40][50]  ✅

Had to shift 3 elements. → O(n)
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── CREATING ───────────────────────────────────────────────────────────────
const nums = [10, 20, 30, 40, 50];
const empty = new Array(5).fill(0); // [0, 0, 0, 0, 0]
const range = Array.from({ length: 5 }, (_, i) => i + 1); // [1, 2, 3, 4, 5]

// ─── READING ─────────────────────────────────────────────────────────────────
console.log(nums[0]);              // 10 — first element (index 0)
console.log(nums[nums.length - 1]); // 50 — last element
console.log(nums.length);          // 5 — total count

// ─── ADDING ──────────────────────────────────────────────────────────────────
nums.push(60);       // Add to END   → [10,20,30,40,50,60]  O(1)
nums.unshift(5);     // Add to START → [5,10,20,30,40,50,60] O(n) shifts all!

// ─── REMOVING ────────────────────────────────────────────────────────────────
nums.pop();          // Remove from END   → O(1)
nums.shift();        // Remove from START → O(n) shifts all!
nums.splice(2, 1);   // Remove 1 item at index 2 → O(n)

// ─── SEARCHING ───────────────────────────────────────────────────────────────
const arr = [3, 7, 1, 9, 4, 6, 2];

// Linear search — O(n) — works on ANY array
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) return i; // found at index i
  }
  return -1; // not found
}

// Binary search — O(log n) — ONLY works on SORTED array
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);

    if (arr[mid] === target) return mid;        // found!
    else if (arr[mid] < target) left = mid + 1; // target is in right half
    else right = mid - 1;                       // target is in left half
  }
  return -1;
}

// ─── TRANSFORMING ────────────────────────────────────────────────────────────
const nums2 = [3, 1, 4, 1, 5, 9, 2, 6];

const doubled  = nums2.map(n => n * 2);         // [6,2,8,2,10,18,4,12]
const evens    = nums2.filter(n => n % 2 === 0); // [4,2,6]
const total    = nums2.reduce((sum, n) => sum + n, 0); // 31
const sorted   = [...nums2].sort((a, b) => a - b);     // [1,1,2,3,4,5,6,9]
const reversed = [...nums2].reverse();

// ─── TWO POINTER PATTERN ─────────────────────────────────────────────────────
// Problem: Find two numbers in sorted array that sum to target
// Brute force: O(n²) — nested loops
// Two pointer: O(n) — smart!

function twoSum(sortedArr, target) {
  let left = 0;                       // start from beginning
  let right = sortedArr.length - 1;  // start from end

  while (left < right) {
    const sum = sortedArr[left] + sortedArr[right];

    if (sum === target) return [left, right]; // ✅ found!
    else if (sum < target) left++;            // sum too small → move left right
    else right--;                             // sum too big  → move right left
  }
  return null;
}

// Trace: arr=[1,3,5,7,9], target=10
// left=0(1), right=4(9)  → sum=10 ✅ → return [0,4]

// ─── SLIDING WINDOW PATTERN ──────────────────────────────────────────────────
// Problem: Maximum sum of any k consecutive elements
// Brute force: O(n²)
// Sliding window: O(n)

function maxSubarraySum(arr, k) {
  // Build first window
  let windowSum = 0;
  for (let i = 0; i < k; i++) windowSum += arr[i];

  let maxSum = windowSum;

  // Slide the window: add new right element, remove old left element
  for (let i = k; i < arr.length; i++) {
    windowSum = windowSum + arr[i] - arr[i - k]; // slide!
    maxSum = Math.max(maxSum, windowSum);
  }
  return maxSum;
}

// Trace: arr=[2,1,5,1,3,2], k=3
// Window [2,1,5] = 8
// Slide  [1,5,1] = 7  (add 1, remove 2)
// Slide  [5,1,3] = 9  ← max!
// Slide  [1,3,2] = 6
// Return 9 ✅
```

-----

### ⏱️ Complexity Table

```
┌─────────────────────────┬───────────┬───────────┐
│ Operation               │   Time    │   Space   │
├─────────────────────────┼───────────┼───────────┤
│ Read by index           │   O(1)    │   O(1)    │
│ Write by index          │   O(1)    │   O(1)    │
│ Push to end             │   O(1)*   │   O(1)    │
│ Pop from end            │   O(1)    │   O(1)    │
│ Insert at start/middle  │   O(n)    │   O(1)    │
│ Delete from start/mid   │   O(n)    │   O(1)    │
│ Search (unsorted)       │   O(n)    │   O(1)    │
│ Search (sorted, binary) │  O(log n) │   O(1)    │
│ Sort                    │ O(n log n)│   O(n)    │
└─────────────────────────┴───────────┴───────────┘
* amortized (occasionally resizes internally)
```

-----

### 🎯 When to Use Arrays

```
✅ USE Arrays when:
   - You need fast access by position/index
   - You know the size ahead of time (or it won't change much)
   - You need to iterate through all items in order
   - You're doing math/aggregation on numbers

❌ AVOID Arrays when:
   - You frequently insert/delete from the middle
   - You need to frequently search by value (use Hash Map instead)
   - You need a sorted structure with fast insert (use BST instead)
```

-----

### 💡 Memory Trick

> **“Cinema seats”** — numbered, fixed positions, instant access by seat number. Moving a seat means physically moving everyone around it.

-----

## 4. Strings

### 🧠 The Story

A string is like a **pearl necklace**. Each pearl is a character, strung together in a specific order. You can read any pearl, but to **add or remove** one in the middle, you must break and re-string the entire necklace.

```
"Hello"
  H  e  l  l  o
  🔵 🔵 🔵 🔵 🔵  ← each pearl has a fixed position
  0  1  2  3  4
```

The critical insight: **strings are immutable in most languages** — you cannot change one character. You must create a brand new string.

-----

### 👁️ Visual — String as Character Array

```
String: "Chennai"

Index:   0    1    2    3    4    5    6
       ┌────┬────┬────┬────┬────┬────┬────┐
Char:  │ C  │ h  │ e  │ n  │ n  │ a  │ i  │
       └────┴────┴────┴────┴────┴────┴────┘

                    ↑ Each character is stored separately
                      like an array element
```

-----

### 🔧 Key Operations — Step by Step

#### Reversing a String

```
Input: "hello"

Step 1: Split into array  → ['h','e','l','l','o']
Step 2: Reverse array     → ['o','l','l','e','h']
Step 3: Join back         → "olleh"

Why split first? Because strings are IMMUTABLE — 
you can't modify them in place, but arrays are mutable.
```

#### Checking a Palindrome

```
Input: "racecar"

Method: Two pointers — one from each end, move inward

  r  a  c  e  c  a  r
  ↑                 ↑   r === r ✅ → move both inward
     ↑           ↑      a === a ✅ → move both inward
        ↑     ↑         c === c ✅ → move both inward
           ↑            pointers met → PALINDROME! ✅
```

-----

### 💻 Code — Complete with Explanations

```javascript
const str = "Hello, Chennai!";

// ─── BASICS ──────────────────────────────────────────────────────────────────
console.log(str.length);           // 15
console.log(str[0]);               // "H"
console.log(str.charAt(7));        // "C"
console.log(str.indexOf("Chennai")); // 7
console.log(str.includes("Hello")); // true
console.log(str.slice(7, 14));     // "Chennai"
console.log(str.toUpperCase());    // "HELLO, CHENNAI!"
console.log(str.toLowerCase());    // "hello, chennai!"
console.log(str.replace("Chennai", "World")); // "Hello, World!"
console.log(str.split(", "));      // ["Hello", "Chennai!"]
console.log("  hello  ".trim());   // "hello"

// ─── IMMUTABILITY — CRITICAL CONCEPT ─────────────────────────────────────────
const s = "hello";
// s[0] = "H";  // ❌ This silently fails! Strings are immutable!

// To modify, convert to array first:
const modified = s.split("").map((ch, i) => i === 0 ? ch.toUpperCase() : ch).join("");
// "Hello" ✅

// ─── REVERSE A STRING ────────────────────────────────────────────────────────
function reverseString(s) {
  return s.split("")    // "hello" → ['h','e','l','l','o']
          .reverse()    //         → ['o','l','l','e','h']
          .join("");    //         → "olleh"
}
// O(n) time, O(n) space

// ─── CHECK PALINDROME ─────────────────────────────────────────────────────────
function isPalindrome(s) {
  // Clean: lowercase, remove non-alphanumeric
  s = s.toLowerCase().replace(/[^a-z0-9]/g, "");

  let left  = 0;
  let right = s.length - 1;

  while (left < right) {
    if (s[left] !== s[right]) return false; // mismatch → not palindrome
    left++;   // move inward from left
    right--;  // move inward from right
  }
  return true; // all matched ✅
}

console.log(isPalindrome("racecar"));                      // true
console.log(isPalindrome("A man, a plan, a canal: Panama")); // true
console.log(isPalindrome("hello"));                        // false

// ─── ANAGRAM CHECK ───────────────────────────────────────────────────────────
// Two words are anagrams if they contain the exact same characters
// "listen" and "silent" → both have {l,i,s,t,e,n} ✅

function isAnagram(s1, s2) {
  if (s1.length !== s2.length) return false; // different length → impossible

  const freq = {};

  // Count each character in s1
  for (const ch of s1) {
    freq[ch] = (freq[ch] || 0) + 1; // increment count
  }

  // For each character in s2, subtract count
  for (const ch of s2) {
    if (!freq[ch]) return false; // char not in s1, or used too many times
    freq[ch]--;
  }

  return true; // all counts balanced ✅
}

console.log(isAnagram("listen", "silent")); // true
console.log(isAnagram("hello",  "world"));  // false

// ─── FREQUENCY COUNTER — Most common pattern ─────────────────────────────────
function firstUniqueChar(s) {
  const freq = {};

  // Pass 1: count all characters
  for (const ch of s) freq[ch] = (freq[ch] || 0) + 1;

  // Pass 2: find first with count exactly 1
  for (let i = 0; i < s.length; i++) {
    if (freq[s[i]] === 1) return i; // first unique!
  }
  return -1;
}

console.log(firstUniqueChar("leetcode"));     // 0 → 'l'
console.log(firstUniqueChar("aabb"));         // -1 → none

// ─── SLIDING WINDOW ON STRING ─────────────────────────────────────────────────
// Find longest substring without repeating characters
function longestUniqueSubstring(s) {
  const seen = new Set();
  let left = 0;
  let maxLen = 0;

  for (let right = 0; right < s.length; right++) {
    // Shrink window from left until no duplicate
    while (seen.has(s[right])) {
      seen.delete(s[left]); // remove leftmost character
      left++;
    }
    seen.add(s[right]);
    maxLen = Math.max(maxLen, right - left + 1);
  }
  return maxLen;
}

// Trace: "abcabcbb"
// right=0: add 'a' → window="a"    maxLen=1
// right=1: add 'b' → window="ab"   maxLen=2
// right=2: add 'c' → window="abc"  maxLen=3
// right=3: 'a' seen! remove 'a', left++ → window="bc" → add 'a' → "bca" maxLen=3
// ... continues
console.log(longestUniqueSubstring("abcabcbb")); // 3 ("abc")
console.log(longestUniqueSubstring("pwwkew"));   // 3 ("wke")
```

-----

### ⏱️ Complexity Table

```
┌─────────────────────────┬───────────┬───────────┐
│ Operation               │   Time    │   Space   │
├─────────────────────────┼───────────┼───────────┤
│ Access character        │   O(1)    │   O(1)    │
│ Length                  │   O(1)    │   O(1)    │
│ Search / indexOf        │   O(n)    │   O(1)    │
│ Concatenation (+)       │   O(n)    │   O(n)    │
│ Slice / substring       │   O(k)    │   O(k)    │
│ Split / join            │   O(n)    │   O(n)    │
│ Reverse                 │   O(n)    │   O(n)    │
│ Replace                 │   O(n)    │   O(n)    │
└─────────────────────────┴───────────┴───────────┘
k = length of extracted portion
```

-----

### 💡 Memory Trick

> **“Pearl necklace”** — beautiful, ordered, but immutable. To change one pearl, you must restring the whole thing.

-----

## 5. Linked Lists

### 🧠 The Story

Imagine a **treasure hunt**. You get the first clue at home. That clue doesn’t give you the treasure — it gives you the **address of the next clue**. That clue gives you the next address, and so on, until finally one clue says “treasure is here!”

```
Home → [Clue 1: go to park]
Park → [Clue 2: go to library]
Library → [Clue 3: go to school]
School → [TREASURE! End of hunt]
```

That is a linked list. Each location (node) has:

- The **data** (what the clue says)
- A **pointer** to the next location (next clue’s address)

-----

### 👁️ Visual — Linked List vs Array

```
ARRAY — all items sit side by side in memory:
┌────┬────┬────┬────┬────┐
│ 10 │ 20 │ 30 │ 40 │ 50 │
└────┴────┴────┴────┴────┘
 1000 1004 1008 1012 1016   ← memory addresses, consecutive

LINKED LIST — items scattered in memory, connected by pointers:
┌──────────┐       ┌──────────┐       ┌──────────┐
│ val: 10  │──────▶│ val: 20  │──────▶│ val: 30  │──▶ null
│ next:────┘       │ next:────┘       │ next:────┘
└──────────┘       └──────────┘       └──────────┘
  at 1000            at 3500            at 2100    ← scattered!
    ↑
   head
```

-----

### 🔧 Operations — Step by Step

#### Inserting at the Start (O(1) — Instant)

```
Before: head → [10] → [20] → [30] → null
Insert 5:

Step 1: Create new node [5]
Step 2: Point new node's next → old head [10]
Step 3: Update head → new node [5]

After: head → [5] → [10] → [20] → [30] → null ✅

Only 2 pointer changes! O(1) regardless of list size.
```

#### Inserting in the Middle (O(n) — Must traverse)

```
Before: head → [10] → [20] → [30] → null
Insert 25 after node with value 20:

Step 1: Traverse from head: 10 → 20 → FOUND [20]
Step 2: Create new node [25]
Step 3: new_node.next = node_20.next  (point 25 → 30)
Step 4: node_20.next  = new_node      (point 20 → 25)

After: head → [10] → [20] → [25] → [30] → null ✅

O(n) because of the traversal in Step 1.
```

#### Deleting a Node (O(n) — Must find previous)

```
Before: head → [10] → [20] → [30] → null
Delete [20]:

Step 1: Traverse to find node BEFORE [20]: that's [10]
Step 2: Skip over [20]: node_10.next = node_30

After: head → [10] → [30] → null ✅
        [20] is now unreachable → garbage collected

The trick: you need the PREVIOUS node to delete any node.
```

#### Reversing a Linked List (Classic Interview Question)

```
Before: head → [1] → [2] → [3] → [4] → null
Goal:   head → [4] → [3] → [2] → [1] → null

Use three pointers: prev, curr, next

Initial:  prev=null, curr=[1], next=?

Step 1:   next=curr.next=[2]     save [2]
          curr.next=prev=null    reverse [1]'s arrow
          prev=curr=[1]          advance prev
          curr=next=[2]          advance curr
          State: null ←[1]  [2]→[3]→[4]→null

Step 2:   next=[3], curr.next=[1], prev=[2], curr=[3]
          State: null ←[1]←[2]  [3]→[4]→null

Step 3:   next=[4], curr.next=[2], prev=[3], curr=[4]
          State: null ←[1]←[2]←[3]  [4]→null

Step 4:   next=null, curr.next=[3], prev=[4], curr=null
          State: null ←[1]←[2]←[3]←[4]
          curr is null → STOP. Return prev=[4] as new head ✅
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── NODE ────────────────────────────────────────────────────────────────────
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;  // pointer to next node (null = end of list)
  }
}

// ─── SINGLY LINKED LIST ───────────────────────────────────────────────────────
class LinkedList {
  constructor() {
    this.head = null; // first node
    this.tail = null; // last node (track for O(1) append)
    this.size = 0;
  }

  // Add to END — O(1) with tail pointer
  append(value) {
    const node = new Node(value);
    if (!this.head) {
      this.head = this.tail = node; // first item
    } else {
      this.tail.next = node; // link old tail to new node
      this.tail = node;      // update tail
    }
    this.size++;
  }

  // Add to START — O(1)
  prepend(value) {
    const node = new Node(value);
    node.next = this.head; // new node points to old head
    this.head = node;      // head is now new node
    if (!this.tail) this.tail = node; // if list was empty
    this.size++;
  }

  // Delete by value — O(n) — must search
  delete(value) {
    if (!this.head) return false; // empty list

    // Special case: deleting the head node
    if (this.head.value === value) {
      this.head = this.head.next;
      if (!this.head) this.tail = null; // list is now empty
      this.size--;
      return true;
    }

    // Find the node BEFORE the one to delete
    let current = this.head;
    while (current.next) {
      if (current.next.value === value) {
        if (current.next === this.tail) this.tail = current; // update tail
        current.next = current.next.next; // skip over the deleted node
        this.size--;
        return true;
      }
      current = current.next;
    }
    return false; // value not found
  }

  // Search — O(n)
  find(value) {
    let current = this.head;
    let index = 0;
    while (current) {
      if (current.value === value) return index;
      current = current.next;
      index++;
    }
    return -1;
  }

  // Reverse — O(n) time, O(1) space — classic interview question!
  reverse() {
    let prev    = null;
    let current = this.head;
    this.tail   = this.head; // old head becomes new tail

    while (current) {
      const next  = current.next; // save next before overwriting
      current.next = prev;        // flip the arrow
      prev    = current;          // advance prev
      current = next;             // advance current
    }
    this.head = prev; // prev is now the last node we visited (new head)
  }

  // Convert to array for easy viewing
  toArray() {
    const result = [];
    let current = this.head;
    while (current) {
      result.push(current.value);
      current = current.next;
    }
    return result;
  }

  // Print
  print() {
    console.log(this.toArray().join(" → ") + " → null");
  }
}

// Usage
const list = new LinkedList();
list.append(10);
list.append(20);
list.append(30);
list.prepend(5);
list.print();     // 5 → 10 → 20 → 30 → null
list.delete(20);
list.print();     // 5 → 10 → 30 → null
list.reverse();
list.print();     // 30 → 10 → 5 → null

// ─── DOUBLY LINKED LIST ───────────────────────────────────────────────────────
// Each node has BOTH a next and a prev pointer
// Allows traversal in BOTH directions and O(1) deletion of tail

class DNode {
  constructor(value) {
    this.value = value;
    this.next = null; // pointer forward
    this.prev = null; // pointer backward ← this is the new part
  }
}

// Visual of doubly linked list:
// null ←← [5] ↔ [10] ↔ [20] ↔ [30] →→ null
//          ↑                     ↑
//         head                  tail

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
      node.prev = this.tail;  // new node points back to old tail
      this.tail.next = node;  // old tail points forward to new node
      this.tail = node;       // update tail
    }
    this.size++;
  }

  // DELETE TAIL — O(1) ← impossible with singly linked list!
  removeTail() {
    if (!this.tail) return null;
    const val = this.tail.value;
    this.tail = this.tail.prev; // go to previous node
    if (this.tail) {
      this.tail.next = null;    // cut off old tail
    } else {
      this.head = null;         // list is now empty
    }
    this.size--;
    return val;
  }
}

// ─── FLOYD'S CYCLE DETECTION ──────────────────────────────────────────────────
// Two pointers: slow moves 1 step, fast moves 2 steps
// If they ever meet → there's a cycle (infinite loop in the list)

function hasCycle(head) {
  let slow = head; // tortoise — 1 step
  let fast = head; // hare     — 2 steps

  while (fast && fast.next) {
    slow = slow.next;       // 1 step
    fast = fast.next.next;  // 2 steps

    if (slow === fast) return true; // they met → cycle exists
  }
  return false; // fast fell off the end → no cycle
}
```

-----

### ⏱️ Complexity Table

```
┌─────────────────────────┬───────────┬───────────┬───────────┐
│ Operation               │  Singly   │  Doubly   │   Array   │
├─────────────────────────┼───────────┼───────────┼───────────┤
│ Access by index         │   O(n)    │   O(n)    │   O(1) ✅  │
│ Search by value         │   O(n)    │   O(n)    │   O(n)    │
│ Insert at head          │   O(1) ✅  │   O(1) ✅  │   O(n)    │
│ Insert at tail          │   O(1) ✅  │   O(1) ✅  │   O(1) ✅  │
│ Insert in middle        │   O(n)    │   O(n)    │   O(n)    │
│ Delete head             │   O(1) ✅  │   O(1) ✅  │   O(n)    │
│ Delete tail             │   O(n)    │   O(1) ✅  │   O(1) ✅  │
│ Delete known node       │   O(n)    │   O(1) ✅  │   O(n)    │
└─────────────────────────┴───────────┴───────────┴───────────┘
```

-----

### 🎯 When to Use Linked Lists

```
✅ USE when:
   - You frequently insert/delete at the beginning (O(1) vs O(n) for array)
   - You don't know the size in advance
   - You need a Queue or Stack implementation
   - You're implementing LRU Cache (Doubly Linked List + Hash Map)

❌ AVOID when:
   - You need fast access by index (use Array instead)
   - Memory efficiency is critical (each node has extra pointer overhead)
   - Cache performance matters (arrays are cache-friendly, linked lists are not)
```

-----

### 💡 Memory Trick

> **“Treasure hunt”** — each clue (node) tells you where the next clue is. You can’t jump to clue #5 without following the chain from clue #1.

-----

## 6. Stacks

### 🧠 The Story

You’re washing dishes after a dinner party. You place clean plates in a stack. When someone needs a plate, they take from the **top**. The last plate you placed is the first one taken.

That is the golden rule of stacks: **LIFO — Last In, First Out**.

```
     ┌───────┐
     │ Plate │  ← you just added this (take it first!)
     │ Plate │
     │ Plate │
     │ Plate │
     └───────┘ ← first plate ever added (taken last)
     
You can ONLY interact with the TOP plate.
```

Real-world stack examples:

- Browser **Back button** — each page you visit is pushed onto a stack; back button pops it
- **Ctrl+Z (Undo)** — each action is pushed; undo pops the most recent
- **Function call stack** — when function A calls B calls C, they stack up; C finishes first

-----

### 👁️ Visual — Push and Pop

```
Start:    []

Push 10:  [10]
           ↑ top

Push 20:  [10][20]
               ↑ top

Push 30:  [10][20][30]
                   ↑ top

Pop:      [10][20]  → returns 30
               ↑ top

Pop:      [10]      → returns 20
           ↑ top

Peek:     [10]      → returns 10 (does NOT remove it)
           ↑ top
```

-----

### 🔧 Operations — Step by Step

```
PUSH (add to top)     — O(1)
  1. Place item on top
  2. Done. (No shifting needed — always goes to the same spot)

POP (remove from top) — O(1)
  1. Take item from top
  2. Done.

PEEK (look at top)    — O(1)
  1. Read item at top WITHOUT removing it

isEmpty               — O(1)
  1. Check if size === 0
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── STACK IMPLEMENTATION ────────────────────────────────────────────────────
class Stack {
  constructor() {
    this.items = []; // use array as internal storage
  }

  // Add to top — O(1)
  push(item) {
    this.items.push(item); // array.push adds to end = top of stack
  }

  // Remove from top — O(1)
  pop() {
    if (this.isEmpty()) return undefined;
    return this.items.pop(); // array.pop removes from end = top of stack
  }

  // Look at top without removing — O(1)
  peek() {
    return this.items[this.items.length - 1];
  }

  isEmpty() { return this.items.length === 0; }
  size()    { return this.items.length; }

  print() {
    console.log([...this.items].reverse().join("\n") + "\n--- bottom ---");
  }
}

// ─── CLASSIC PROBLEM 1: Valid Parentheses ────────────────────────────────────
// Input: string of brackets. Are they properly opened and closed?
// "()[]{}"   → valid ✅    "(]"   → invalid ❌
// "{[]}"     → valid ✅    "([)]" → invalid ❌

function isValidParentheses(s) {
  const stack = new Stack();
  const matchMap = { ")": "(", "}": "{", "]": "[" };

  for (const ch of s) {
    if ("({[".includes(ch)) {
      stack.push(ch);        // opening bracket → push onto stack
    } else {
      // closing bracket → must match the most recent opening
      const top = stack.pop();
      if (top !== matchMap[ch]) return false; // mismatch!
    }
  }

  return stack.isEmpty(); // valid only if all brackets were matched
}

// Trace: "({[]})"
// '(' → push     stack: ['(']
// '{' → push     stack: ['(', '{']
// '[' → push     stack: ['(', '{', '[']
// ']' → pop '['  matches ']' → ✅  stack: ['(', '{']
// '}' → pop '{'  matches '}' → ✅  stack: ['(']
// ')' → pop '('  matches ')' → ✅  stack: []
// stack empty → return true ✅

// ─── CLASSIC PROBLEM 2: Min Stack ────────────────────────────────────────────
// A stack that also gives you the MINIMUM element in O(1)
// Trick: maintain a second "minStack" that tracks mins

class MinStack {
  constructor() {
    this.stack    = [];
    this.minStack = []; // tracks the minimum at each level
  }

  push(val) {
    this.stack.push(val);

    // Push to minStack: either this val or current min (whichever is smaller)
    const currentMin = this.minStack.length === 0
      ? val
      : this.minStack[this.minStack.length - 1];

    this.minStack.push(Math.min(val, currentMin));
  }

  pop() {
    this.minStack.pop(); // keep them in sync
    return this.stack.pop();
  }

  getMin() {
    return this.minStack[this.minStack.length - 1]; // O(1)!
  }
}

// Trace:
// push(5) → stack:[5]   minStack:[5]
// push(3) → stack:[5,3] minStack:[5,3]
// push(7) → stack:[5,3,7] minStack:[5,3,3] ← min is still 3
// push(2) → stack:[5,3,7,2] minStack:[5,3,3,2]
// getMin() → 2 (top of minStack) O(1) ✅
// pop()    → removes 2
// getMin() → 3 ✅

// ─── CLASSIC PROBLEM 3: Reverse a String using Stack ─────────────────────────
function reverseWithStack(str) {
  const stack = new Stack();

  // Push all characters
  for (const ch of str) stack.push(ch); // "hello" → ['h','e','l','l','o']

  // Pop all characters (comes out in reverse order due to LIFO)
  let reversed = "";
  while (!stack.isEmpty()) {
    reversed += stack.pop(); // pops 'o','l','l','e','h'
  }
  return reversed; // "olleh"
}

// ─── CLASSIC PROBLEM 4: Browser Back Button simulation ───────────────────────
class BrowserHistory {
  constructor() {
    this.history = new Stack();
    this.current = null;
  }

  visit(url) {
    if (this.current) this.history.push(this.current); // save current to history
    this.current = url;
    console.log(`Visiting: ${url}`);
  }

  back() {
    if (this.history.isEmpty()) {
      console.log("No history!");
      return;
    }
    this.current = this.history.pop();
    console.log(`Back to: ${this.current}`);
  }
}

const browser = new BrowserHistory();
browser.visit("google.com");
browser.visit("github.com");
browser.visit("stackoverflow.com");
browser.back(); // "Back to: github.com"
browser.back(); // "Back to: google.com"
```

-----

### ⏱️ Complexity Table

```
┌────────────────┬────────┬────────┐
│ Operation      │  Time  │  Space │
├────────────────┼────────┼────────┤
│ Push           │  O(1)  │  O(1)  │
│ Pop            │  O(1)  │  O(1)  │
│ Peek           │  O(1)  │  O(1)  │
│ isEmpty        │  O(1)  │  O(1)  │
│ Search         │  O(n)  │  O(1)  │
└────────────────┴────────┴────────┘
Space overall: O(n) — proportional to items stored
```

-----

### 💡 Memory Trick

> **“Stack of plates”** — you can only add or remove from the top. The LAST plate you put on is the FIRST one you take off. LIFO.

-----

## 7. Queues

### 🧠 The Story

Picture the **ticket counter at Chennai Central railway station**. People join the line from the back. The person at the front gets served first. Nobody cuts in. Nobody joins from the front.

That is a Queue: **FIFO — First In, First Out**.

```
   FRONT                              BACK
   ┌──────┬──────┬──────┬──────┬──────┐
   │Ravi  │Priya │Kumar │Meena │Arjun │  ← Arjun just joined
   └──────┴──────┴──────┴──────┴──────┘
      ↑ Ravi gets served next (dequeue)      ↑ next person joins here (enqueue)
```

Real-world queue examples:

- **Printer queue** — documents print in the order they were sent
- **Customer service** call centers — calls answered in order received
- **CPU task scheduling** — processes get CPU time in order
- **BFS graph traversal** — explore nodes level by level

-----

### 👁️ Visual — Enqueue and Dequeue

```
Start:     front → [] ← back

Enqueue A: front → [A] ← back
Enqueue B: front → [A][B] ← back
Enqueue C: front → [A][B][C] ← back

Dequeue:   front → [B][C] ← back    returns A
Dequeue:   front → [C] ← back       returns B

Peek:      front → [C] ← back       returns C (no removal)
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── QUEUE using Object (O(1) dequeue!) ──────────────────────────────────────
// Using an array, shift() is O(n). Using an object with indices is O(1).

class Queue {
  constructor() {
    this.store = {}; // { 0: 'A', 1: 'B', 2: 'C' }
    this.front = 0;  // index of first item
    this.back  = 0;  // index of next empty slot
  }

  // Add to back — O(1)
  enqueue(item) {
    this.store[this.back] = item;
    this.back++;
  }

  // Remove from front — O(1)
  dequeue() {
    if (this.isEmpty()) return undefined;
    const item = this.store[this.front];
    delete this.store[this.front]; // free memory
    this.front++;
    return item;
  }

  peek()    { return this.store[this.front]; }
  isEmpty() { return this.front === this.back; }
  size()    { return this.back - this.front; }
}

// ─── CIRCULAR QUEUE ───────────────────────────────────────────────────────────
// Fixed size queue that reuses positions to avoid wasted space
// Used in: OS scheduling, streaming buffers, networking

class CircularQueue {
  constructor(capacity) {
    this.queue    = new Array(capacity);
    this.capacity = capacity;
    this.front    = 0;
    this.size     = 0;
  }

  enqueue(item) {
    if (this.size === this.capacity) return false; // full!
    const back = (this.front + this.size) % this.capacity; // wrap around
    this.queue[back] = item;
    this.size++;
    return true;
  }

  dequeue() {
    if (this.size === 0) return undefined;
    const item  = this.queue[this.front];
    this.front  = (this.front + 1) % this.capacity; // wrap around
    this.size--;
    return item;
  }
}

// ─── DEQUE (Double-Ended Queue) ───────────────────────────────────────────────
// Can add/remove from BOTH front and back — more flexible

class Deque {
  constructor() {
    this.items = new DoublyLinkedList(); // use DLL for O(1) on both ends
    // For simplicity, array version:
    this.arr = [];
  }
  addFront(item)  { this.arr.unshift(item); }  // O(n) with array — use DLL for O(1)
  addBack(item)   { this.arr.push(item); }     // O(1)
  removeFront()   { return this.arr.shift(); } // O(n) — use DLL for O(1)
  removeBack()    { return this.arr.pop(); }   // O(1)
  peekFront()     { return this.arr[0]; }
  peekBack()      { return this.arr[this.arr.length - 1]; }
  isEmpty()       { return this.arr.length === 0; }
}

// ─── CLASSIC PROBLEM: Level Order Tree Traversal using Queue ──────────────────
// Visit all nodes level by level (top to bottom, left to right)

function levelOrder(root) {
  if (!root) return [];

  const result = [];
  const queue = new Queue();
  queue.enqueue(root);

  while (!queue.isEmpty()) {
    const levelSize = queue.size(); // number of nodes at this level
    const currentLevel = [];

    for (let i = 0; i < levelSize; i++) {
      const node = queue.dequeue();
      currentLevel.push(node.val);

      if (node.left)  queue.enqueue(node.left);  // add children for next level
      if (node.right) queue.enqueue(node.right);
    }

    result.push(currentLevel);
  }
  return result;
}

// Tree:       1
//            / \
//           2   3
//          / \
//         4   5
//
// Queue starts: [1]
// Level 1: dequeue 1 → currentLevel=[1], enqueue 2,3 → queue:[2,3]
// Level 2: dequeue 2,3 → currentLevel=[2,3], enqueue 4,5 → queue:[4,5]
// Level 3: dequeue 4,5 → currentLevel=[4,5], no children
// Result: [[1],[2,3],[4,5]] ✅

// ─── CLASSIC PROBLEM: Hot Potato (Josephus) ───────────────────────────────────
// n people stand in a circle, pass a potato, every kth person is eliminated
// Last person standing wins

function hotPotato(names, num) {
  const queue = new Queue();
  names.forEach(name => queue.enqueue(name));

  while (queue.size() > 1) {
    // Pass the potato num times: move from front to back
    for (let i = 0; i < num - 1; i++) {
      queue.enqueue(queue.dequeue()); // take from front, put at back
    }
    // The person holding the potato is eliminated
    console.log(`Eliminated: ${queue.dequeue()}`);
  }

  return queue.dequeue(); // last person standing
}

console.log(hotPotato(["Ravi","Priya","Kumar","Meena","Arjun"], 3));
// Eliminated: Kumar, then Ravi, then Arjun, then Meena
// Winner: Priya
```

-----

### ⏱️ Complexity Table

```
┌────────────────┬────────┬────────┐
│ Operation      │  Time  │  Space │
├────────────────┼────────┼────────┤
│ Enqueue        │  O(1)  │  O(1)  │
│ Dequeue        │  O(1)  │  O(1)  │
│ Peek front     │  O(1)  │  O(1)  │
│ isEmpty        │  O(1)  │  O(1)  │
│ Search         │  O(n)  │  O(1)  │
└────────────────┴────────┴────────┘
```

-----

### 🎯 Stack vs Queue — At a Glance

```
┌──────────────────┬────────────────────┬────────────────────┐
│                  │      STACK         │      QUEUE         │
├──────────────────┼────────────────────┼────────────────────┤
│ Rule             │ LIFO               │ FIFO               │
│ Real life        │ Plate stack        │ Bank line          │
│ Add to           │ Top only           │ Back only          │
│ Remove from      │ Top only           │ Front only         │
│ Use case         │ Undo, call stack   │ Scheduling, BFS    │
│ Operations       │ push / pop / peek  │ enqueue / dequeue  │
└──────────────────┴────────────────────┴────────────────────┘
```

-----

### 💡 Memory Trick

> **“Railway ticket counter”** — join at the back, get served at the front. First come, first served. FIFO.

-----

## 8. Hash Tables (Hash Maps)

### 🧠 The Story

You work at a **library with 10,000 books**. A student asks for “Harry Potter and the Philosopher’s Stone.” Two options:

```
Option A — Linear search: walk every row, check every spine
  → Could check all 10,000 books. Very slow.

Option B — Dewey Decimal System (like a Hash Table):
  1. Convert book name to a shelf number using a formula
  2. Go directly to that shelf
  3. The book is right there!
  → Always just 1 lookup, no matter how many books exist. 🚀
```

That “formula that converts a name to a shelf number” is a **hash function**.

```
"Harry Potter" → hash("Harry Potter") → 47 → shelf 47 → book is there!
"React Docs"   → hash("React Docs")   → 92 → shelf 92 → book is there!
```

-----

### 👁️ Visual — How Hashing Works

```
Hash Function converts keys into array indices:

"name"  → hash() → index 3
"age"   → hash() → index 7
"city"  → hash() → index 1

Internal array:
index: [0][1][2][3][4][5][6][7][8][9]
value: [ ][city][ ][name][ ][ ][ ][age][ ][ ]

map.get("name") → hash("name")=3 → arr[3] → "Alice"  O(1) ✅
```

#### Collision — When Two Keys Hash to Same Index

```
"name" → hash() → index 3
"mane" → hash() → index 3  ← COLLISION! Same index!

Solution: Chaining — store a list at each index
index 3: [["name","Alice"], ["mane","Bob"]]

Now lookup:
map.get("mane") → hash()=3 → arr[3] → scan list → find "mane" → "Bob" ✅
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── BUILT-IN MAP (use this in practice) ─────────────────────────────────────
const map = new Map();

// Set key-value pairs
map.set("name", "Murugesh");
map.set("city", "Chennai");
map.set("role", "Tech Lead");
map.set(42, "the answer");    // keys can be ANY type!
map.set(true, "boolean key"); // even booleans!

// Get values — O(1)
console.log(map.get("name")); // "Murugesh"
console.log(map.get(42));     // "the answer"

// Check existence — O(1)
console.log(map.has("city")); // true
console.log(map.has("age"));  // false

// Delete — O(1)
map.delete("role");

// Size
console.log(map.size); // 4

// Iterate
for (const [key, value] of map) {
  console.log(`${key} → ${value}`);
}

// ─── HASH TABLE FROM SCRATCH ──────────────────────────────────────────────────
class HashTable {
  constructor(capacity = 53) {
    this.buckets  = new Array(capacity); // array of "buckets"
    this.capacity = capacity;
    this.count    = 0;
  }

  // Hash function: converts string key → index
  _hash(key) {
    let hash = 0;
    for (let i = 0; i < Math.min(key.length, 100); i++) {
      hash = (hash * 31 + key.charCodeAt(i)) % this.capacity;
    }
    return hash;
    // This is a simplified polynomial hash.
    // Real hash tables use MurmurHash3, xxHash etc.
  }

  // Set — O(1) average
  set(key, value) {
    const idx = this._hash(key);
    if (!this.buckets[idx]) this.buckets[idx] = []; // create bucket if empty

    // Check if key already exists (update it)
    for (const pair of this.buckets[idx]) {
      if (pair[0] === key) { pair[1] = value; return; }
    }

    // Add new key-value pair
    this.buckets[idx].push([key, value]);
    this.count++;
  }

  // Get — O(1) average
  get(key) {
    const idx    = this._hash(key);
    const bucket = this.buckets[idx];
    if (!bucket) return undefined;

    for (const [k, v] of bucket) {
      if (k === key) return v; // found!
    }
    return undefined;
  }

  // Delete — O(1) average
  delete(key) {
    const idx    = this._hash(key);
    const bucket = this.buckets[idx];
    if (!bucket) return false;

    const i = bucket.findIndex(pair => pair[0] === key);
    if (i === -1) return false;
    bucket.splice(i, 1);
    this.count--;
    return true;
  }

  // Get all keys
  keys() {
    const result = [];
    for (const bucket of this.buckets) {
      if (bucket) result.push(...bucket.map(pair => pair[0]));
    }
    return result;
  }
}

// ─── CLASSIC PROBLEMS WITH HASH MAPS ─────────────────────────────────────────

// Problem 1: Two Sum — find pair that adds to target — O(n) with hash map
function twoSum(nums, target) {
  const seen = new Map(); // value → index

  for (let i = 0; i < nums.length; i++) {
    const complement = target - nums[i]; // what do we need?

    if (seen.has(complement)) {
      return [seen.get(complement), i]; // found the pair!
    }
    seen.set(nums[i], i); // remember this value and its index
  }
  return null;
}
// Trace: nums=[2,7,11,15], target=9
// i=0: need 7, seen={} → not found → seen={2:0}
// i=1: need 2, seen={2:0} → FOUND! return [0,1] ✅

// Problem 2: Group Anagrams
function groupAnagrams(words) {
  const groups = new Map();

  for (const word of words) {
    const key = word.split("").sort().join(""); // sort chars = canonical form
    // "eat" → "aet", "tea" → "aet", "tan" → "ant"

    if (!groups.has(key)) groups.set(key, []);
    groups.get(key).push(word);
  }

  return [...groups.values()];
}
// groupAnagrams(["eat","tea","tan","ate","nat","bat"])
// → [["eat","tea","ate"], ["tan","nat"], ["bat"]]

// Problem 3: Longest Consecutive Sequence — O(n)
function longestConsecutive(nums) {
  const numSet = new Set(nums); // O(1) lookup
  let maxLen = 0;

  for (const num of numSet) {
    // Only start counting from the BEGINNING of a sequence
    if (numSet.has(num - 1)) continue; // not the start

    let current = num;
    let length  = 1;

    while (numSet.has(current + 1)) {
      current++;
      length++;
    }

    maxLen = Math.max(maxLen, length);
  }
  return maxLen;
}
// nums=[100,4,200,1,3,2]
// Sequences: [1,2,3,4] length 4, [100] length 1, [200] length 1
// Returns 4 ✅
```

-----

### ⏱️ Complexity Table

```
┌─────────────────────────┬──────────────┬──────────────┐
│ Operation               │ Average Case │  Worst Case  │
├─────────────────────────┼──────────────┼──────────────┤
│ Insert (set)            │    O(1)      │    O(n)      │
│ Lookup (get)            │    O(1)      │    O(n)      │
│ Delete                  │    O(1)      │    O(n)      │
│ Search by value         │    O(n)      │    O(n)      │
└─────────────────────────┴──────────────┴──────────────┘
Worst case is rare (many collisions). Average is almost always O(1).
Space: O(n)
```

-----

### 💡 Memory Trick

> **“Dewey Decimal Library”** — the book title (key) is converted to a shelf number (hash) and you go straight there. No searching needed.

-----

## 9. Sets

### 🧠 The Story

You’re collecting **unique stamps**. Your rule is: **no two stamps can be the same**. If someone gives you a stamp you already have, you simply don’t add it.

That’s a Set — it stores only **unique values**, automatically ignoring duplicates.

```
My collection: { 🇮🇳, 🇺🇸, 🇯🇵 }
Someone gives me 🇮🇳 (already have it!) → collection stays: { 🇮🇳, 🇺🇸, 🇯🇵 }
Someone gives me 🇫🇷 (new!) → collection becomes: { 🇮🇳, 🇺🇸, 🇯🇵, 🇫🇷 }
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── BUILT-IN SET ─────────────────────────────────────────────────────────────
const set = new Set();

set.add(10);
set.add(20);
set.add(10); // duplicate → silently ignored!
set.add(30);

console.log(set.size);       // 3  (not 4!)
console.log(set.has(20));    // true
console.log(set.has(99));    // false

set.delete(20);
console.log([...set]);       // [10, 30]

// ─── MOST COMMON USE: Remove duplicates from array ───────────────────────────
const arr = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4];
const unique = [...new Set(arr)];
console.log(unique); // [1, 2, 3, 4]

// ─── SET OPERATIONS ───────────────────────────────────────────────────────────
const A = new Set([1, 2, 3, 4, 5]);
const B = new Set([3, 4, 5, 6, 7]);

// UNION — all elements from both sets (no duplicates)
const union = new Set([...A, ...B]);
// {1, 2, 3, 4, 5, 6, 7}

// INTERSECTION — only elements in BOTH sets
const intersection = new Set([...A].filter(x => B.has(x)));
// {3, 4, 5}

// DIFFERENCE — elements in A but NOT in B
const difference = new Set([...A].filter(x => !B.has(x)));
// {1, 2}

// SYMMETRIC DIFFERENCE — elements in either but NOT both
const symDiff = new Set([
  ...[...A].filter(x => !B.has(x)),
  ...[...B].filter(x => !A.has(x))
]);
// {1, 2, 6, 7}

// ─── PRACTICAL: Fast lookup instead of array.includes ────────────────────────
// array.includes = O(n)   ← scans whole array
// set.has        = O(1)   ← instant hash lookup

const blockedUsers = new Set(["spam1", "bot99", "troll42"]);

function isBlocked(user) {
  return blockedUsers.has(user); // O(1)!
}

// ─── CLASSIC PROBLEM: Contains Duplicate ─────────────────────────────────────
function containsDuplicate(nums) {
  const seen = new Set();
  for (const n of nums) {
    if (seen.has(n)) return true; // seen before → duplicate!
    seen.add(n);
  }
  return false;
}
```

-----

### ⏱️ Complexity Table

```
┌────────────────┬────────┬────────┐
│ Operation      │  Time  │  Space │
├────────────────┼────────┼────────┤
│ Add            │  O(1)  │  O(1)  │
│ Has (lookup)   │  O(1)  │  O(1)  │
│ Delete         │  O(1)  │  O(1)  │
│ Iteration      │  O(n)  │  O(1)  │
│ Union          │  O(n)  │  O(n)  │
│ Intersection   │  O(n)  │  O(n)  │
└────────────────┴────────┴────────┘
```

-----

### 💡 Memory Trick

> **“Unique stamp collection”** — no duplicates allowed, and you can instantly check if you already have a stamp. O(1) lookup, like a hash table.

-----

## 10. Trees

### 🧠 The Story

Your **family tree** is the perfect mental model. You have grandparents at the top, parents below them, then children, then grandchildren. Each person can have multiple children, but only one set of parents.

```
                   👴 Grandfather
                  /               \
          👨 Uncle              👨 Dad
         /       \             /       \
       👦 Cousin  👧 Cousin  👦 You    👧 Sister
```

Key vocabulary:

- **Root** — the top node (Grandfather) — has no parent
- **Leaf** — nodes with no children (Cousin, You, Sister)
- **Parent** — the node directly above
- **Child** — nodes directly below a node
- **Subtree** — any node and all its descendants
- **Height** — longest path from root to a leaf
- **Depth** — distance from root to a given node

-----

### 👁️ Visual — Binary Tree (Most Common Type)

```
A binary tree: each node has AT MOST 2 children (left and right)

              10          ← Root (depth 0)
            /    \
           5      15     ← depth 1
          / \    /  \
         3   7  12   20  ← depth 2 (leaves here)

Height = 2 (longest root-to-leaf path)
Total nodes = 7
```

-----

### 🔧 Three Traversal Orders — With Step by Step

Every tree traversal is a variation of: visit **Left**, **Root**, **Right**.

```
Tree:       1
           / \
          2   3
         / \
        4   5

In-Order   (Left → Root → Right): 4, 2, 5, 1, 3
Pre-Order  (Root → Left → Right): 1, 2, 4, 5, 3
Post-Order (Left → Right → Root): 4, 5, 2, 3, 1
```

#### In-Order Trace (Left → Root → Right)

```
Call inOrder(1):
  → Call inOrder(2):
      → Call inOrder(4):
          → Call inOrder(null) → return  [left of 4]
          → Print 4
          → Call inOrder(null) → return  [right of 4]
      → Print 2
      → Call inOrder(5):
          → Call inOrder(null) → return
          → Print 5
          → Call inOrder(null) → return
  → Print 1
  → Call inOrder(3):
      → Call inOrder(null) → return
      → Print 3
      → Call inOrder(null) → return

Output: 4 2 5 1 3 ✅
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── TREE NODE ────────────────────────────────────────────────────────────────
class TreeNode {
  constructor(val) {
    this.val   = val;
    this.left  = null; // left child
    this.right = null; // right child
  }
}

// Build example tree:
//       1
//      / \
//     2   3
//    / \
//   4   5
const root = new TreeNode(1);
root.left  = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left  = new TreeNode(4);
root.left.right = new TreeNode(5);

// ─── THREE TRAVERSALS ─────────────────────────────────────────────────────────

// In-Order: Left → Root → Right
// → for BST, this gives SORTED order!
function inOrder(node, result = []) {
  if (!node) return result;
  inOrder(node.left, result);   // go left first
  result.push(node.val);        // visit root
  inOrder(node.right, result);  // go right
  return result;
}

// Pre-Order: Root → Left → Right
// → useful for COPYING/CLONING a tree or SERIALIZING
function preOrder(node, result = []) {
  if (!node) return result;
  result.push(node.val);        // visit root FIRST
  preOrder(node.left, result);
  preOrder(node.right, result);
  return result;
}

// Post-Order: Left → Right → Root
// → useful for DELETING a tree (delete children before parent)
function postOrder(node, result = []) {
  if (!node) return result;
  postOrder(node.left, result);
  postOrder(node.right, result);
  result.push(node.val);        // visit root LAST
  return result;
}

console.log(inOrder(root));   // [4, 2, 5, 1, 3]
console.log(preOrder(root));  // [1, 2, 4, 5, 3]
console.log(postOrder(root)); // [4, 5, 2, 3, 1]

// ─── TREE HEIGHT ──────────────────────────────────────────────────────────────
function maxHeight(node) {
  if (!node) return 0;
  const leftH  = maxHeight(node.left);  // height of left subtree
  const rightH = maxHeight(node.right); // height of right subtree
  return 1 + Math.max(leftH, rightH);   // 1 (this node) + taller subtree
}

// ─── COUNT NODES ──────────────────────────────────────────────────────────────
function countNodes(node) {
  if (!node) return 0;
  return 1 + countNodes(node.left) + countNodes(node.right);
}

// ─── CHECK IF TREE IS SYMMETRIC (mirror of itself) ───────────────────────────
function isSymmetric(root) {
  function isMirror(left, right) {
    if (!left && !right) return true;   // both null → symmetric
    if (!left || !right) return false;  // one null → asymmetric
    return left.val === right.val       // values match
      && isMirror(left.left, right.right)  // outer pair matches
      && isMirror(left.right, right.left); // inner pair matches
  }
  return isMirror(root.left, root.right);
}

// ─── LEVEL ORDER (BFS) with queue ─────────────────────────────────────────────
function levelOrderTraversal(root) {
  if (!root) return [];
  const result = [];
  const queue  = [root];

  while (queue.length > 0) {
    const size  = queue.length;
    const level = [];

    for (let i = 0; i < size; i++) {
      const node = queue.shift();
      level.push(node.val);
      if (node.left)  queue.push(node.left);
      if (node.right) queue.push(node.right);
    }
    result.push(level);
  }
  return result;
}
// Returns: [[1],[2,3],[4,5]]
```

-----

### ⏱️ Complexity Table

```
┌─────────────────────────┬────────────┬────────────┐
│ Operation               │  Average   │  Worst     │
├─────────────────────────┼────────────┼────────────┤
│ All traversals          │   O(n)     │   O(n)     │
│ Height calculation      │   O(n)     │   O(n)     │
│ Level order (BFS)       │   O(n)     │   O(n)     │
│ Count nodes             │   O(n)     │   O(n)     │
└─────────────────────────┴────────────┴────────────┘
Space: O(h) for recursive calls where h = height
       O(n) worst case for skewed tree
```

-----

### 💡 Memory Trick

> **“Family tree”** — grandfather at top (root), no one above him. Leaves are people with no kids. You can visit everyone by going left subtree → root → right subtree (In-Order).

-----

## 11. Binary Search Tree (BST)

### 🧠 The Story

You manage a **school library** and want a rule so students can find books instantly:

> “Every book on the **left shelf** has a title that comes **alphabetically before** this shelf’s book. Every book on the **right shelf** comes **after**.”

That’s a BST rule:

- **Left child < Parent < Right child**

This one rule makes searching incredibly efficient — at each step you know exactly which direction to go.

```
           8
          / \
         3   10
        / \    \
       1   6    14
          / \   /
         4   7 13
```

Want 6? Start at 8 → 6 < 8, go left → arrive at 3 → 6 > 3, go right → arrive at 6 ✅
Only 3 steps for a 9-node tree!

-----

### 🔧 Operations — Step by Step

#### Search for 7

```
          8          Is 7 < 8? Yes → go left
         / \
        3   10       Is 7 > 3? Yes → go right
       / \
      1   6          Is 7 > 6? Yes → go right
         / \
        4   7        Is 7 = 7? Yes → FOUND! ✅

4 steps for 9 nodes. With 1,000,000 nodes → only ~20 steps!
```

#### Insert 5

```
Start at root (8), follow the same path as search:
8 → go left (5<8)
3 → go right (5>3)
6 → go left (5<6)
4 → go right (5>4)
null → INSERT HERE

Result: 4's right child becomes 5 ✅
```

-----

### 💻 Code — Complete with Explanations

```javascript
class BST {
  constructor() {
    this.root = null;
  }

  // INSERT — O(log n) avg, O(n) worst (skewed tree)
  insert(value) {
    const node = new TreeNode(value);
    if (!this.root) { this.root = node; return; }

    let curr = this.root;
    while (true) {
      if (value === curr.val) return;       // no duplicates
      if (value < curr.val) {
        if (!curr.left)  { curr.left  = node; return; }
        curr = curr.left;                   // go left
      } else {
        if (!curr.right) { curr.right = node; return; }
        curr = curr.right;                  // go right
      }
    }
  }

  // SEARCH — O(log n) avg
  search(value) {
    let curr = this.root;
    while (curr) {
      if (value === curr.val) return true;
      curr = value < curr.val ? curr.left : curr.right;
    }
    return false;
  }

  // FIND MIN — always the leftmost node — O(log n)
  findMin(node = this.root) {
    if (!node) return null;
    while (node.left) node = node.left;
    return node.val;
  }

  // FIND MAX — always the rightmost node — O(log n)
  findMax(node = this.root) {
    if (!node) return null;
    while (node.right) node = node.right;
    return node.val;
  }

  // DELETE — O(log n) avg — 3 cases:
  delete(value, node = this.root, parent = null, isLeft = false) {
    if (!node) return;

    if (value < node.val) {
      this.delete(value, node.left, node, true);
    } else if (value > node.val) {
      this.delete(value, node.right, node, false);
    } else {
      // FOUND the node to delete — 3 cases:

      if (!node.left && !node.right) {
        // Case 1: Leaf node — just remove it
        if (!parent) this.root = null;
        else if (isLeft) parent.left = null;
        else parent.right = null;

      } else if (!node.right) {
        // Case 2: Only left child — replace with left child
        if (!parent) this.root = node.left;
        else if (isLeft) parent.left = node.left;
        else parent.right = node.left;

      } else if (!node.left) {
        // Case 2: Only right child — replace with right child
        if (!parent) this.root = node.right;
        else if (isLeft) parent.left = node.right;
        else parent.right = node.right;

      } else {
        // Case 3: Two children — replace with in-order successor
        // In-order successor = smallest node in right subtree
        let successor = node.right;
        let succParent = node;
        while (successor.left) {
          succParent = successor;
          successor  = successor.left;
        }
        node.val = successor.val;         // copy successor value here
        this.delete(successor.val, node.right, node, false); // delete successor
      }
    }
  }

  // VALIDATE — check if a tree is a valid BST
  isValidBST(node = this.root, min = -Infinity, max = Infinity) {
    if (!node) return true;
    if (node.val <= min || node.val >= max) return false; // violates BST rule

    return this.isValidBST(node.left, min, node.val)   // left must be < node
        && this.isValidBST(node.right, node.val, max); // right must be > node
  }
}

// Usage
const bst = new BST();
[8, 3, 10, 1, 6, 14, 4, 7, 13].forEach(v => bst.insert(v));
console.log(bst.search(7));   // true
console.log(bst.search(99));  // false
console.log(bst.findMin());   // 1
console.log(bst.findMax());   // 14
```

-----

### ⏱️ Complexity Table

```
┌─────────────────┬──────────────┬──────────────┐
│ Operation       │ Average Case │  Worst Case  │
├─────────────────┼──────────────┼──────────────┤
│ Search          │  O(log n)    │    O(n)      │
│ Insert          │  O(log n)    │    O(n)      │
│ Delete          │  O(log n)    │    O(n)      │
│ Find Min/Max    │  O(log n)    │    O(n)      │
│ In-Order        │  O(n)        │    O(n)      │
└─────────────────┴──────────────┴──────────────┘

Worst case = skewed tree (like a linked list):
  1 → 2 → 3 → 4 → 5   (all inserted in order)
Space: O(n)
```

-----

### 💡 Memory Trick

> **“School library rule”** — left shelf = alphabetically before, right shelf = alphabetically after. You never check the whole library; you just follow the rule at each shelf.

-----

## 12. Heaps / Priority Queues

### 🧠 The Story

You’re in the **Emergency Room** of a hospital. Patients arrive and are seen **not in arrival order**, but by **severity**. The patient with the most critical condition always goes first.

```
Patients waiting:
  Patient A — broken finger   (priority 3)
  Patient B — heart attack    (priority 10) ← seen FIRST!
  Patient C — headache        (priority 2)
  Patient D — severe bleeding (priority 9) ← seen SECOND!

New patient arrives:
  Patient E — sprained ankle  (priority 4)

Who goes next? → Always the HIGHEST priority person. Always.
```

That is a **Max-Heap (Priority Queue)**.

-----

### 👁️ Visual — Heap as Array

```
Max-Heap Tree:         Array:
        10             [10, 9, 8, 5, 6, 7, 3]
       /    \           0   1  2  3  4  5  6
      9      8
     / \    / \
    5   6  7   3

Key formulas (1-indexed or 0-indexed):
  parent(i)     = Math.floor((i - 1) / 2)
  leftChild(i)  = 2 * i + 1
  rightChild(i) = 2 * i + 2

So: parent of index 3 (value 5) = floor((3-1)/2) = 1 (value 9) ✅
```

#### Inserting 11 into Max-Heap

```
Step 1: Add 11 at end → [10, 9, 8, 5, 6, 7, 3, 11]
                                                  ↑ at index 7
Step 2: Compare with parent: parent(7) = 3 (value 8)
        11 > 8 → SWAP! → [10, 9, 11, 5, 6, 7, 3, 8]
Step 3: Compare with parent: parent(2) = 0 (value 10)
        11 > 10 → SWAP! → [11, 9, 10, 5, 6, 7, 3, 8]
Step 4: At index 0 (root) → done!

Result: 11 is now the new max at root ✅
```

#### Removing Max (Extract-Max)

```
Array: [11, 9, 10, 5, 6, 7, 3]
Step 1: Save max = 11
Step 2: Move LAST element to root → [3, 9, 10, 5, 6, 7]
Step 3: Sink 3 down:
        Compare 3 with children 9 and 10. Max child is 10.
        10 > 3 → SWAP → [10, 9, 3, 5, 6, 7]
        Compare 3 with children 5 and 7. Max child is 7.
        7 > 3 → SWAP → [10, 9, 7, 5, 6, 3]
        No more children → DONE.
Return 11 ✅
```

-----

### 💻 Code — Complete with Explanations

```javascript
class MinHeap {
  constructor() {
    this.heap = []; // 0-indexed array
  }

  parent(i)     { return Math.floor((i - 1) / 2); }
  leftChild(i)  { return 2 * i + 1; }
  rightChild(i) { return 2 * i + 2; }

  swap(i, j) {
    [this.heap[i], this.heap[j]] = [this.heap[j], this.heap[i]];
  }

  // INSERT — O(log n)
  push(val) {
    this.heap.push(val);         // add to bottom
    this._bubbleUp(this.heap.length - 1); // float up to correct position
  }

  _bubbleUp(i) {
    while (i > 0) {
      const p = this.parent(i);
      if (this.heap[p] > this.heap[i]) {
        this.swap(p, i); // parent is bigger → swap (we're a min-heap)
        i = p;           // continue from parent's position
      } else break;      // parent is smaller → we're in the right place
    }
  }

  // PEEK MIN — O(1)
  peek() { return this.heap[0]; }

  // EXTRACT MIN — O(log n)
  pop() {
    if (this.heap.length === 0) return null;
    if (this.heap.length === 1) return this.heap.pop();

    const min = this.heap[0];          // save the min to return
    this.heap[0] = this.heap.pop();    // move last to top
    this._sinkDown(0);                  // sink down to correct position
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
        i = smallest; // continue sinking from swapped position
      } else break;   // already in right place
    }
  }

  size()    { return this.heap.length; }
  isEmpty() { return this.heap.length === 0; }
}

// ─── CLASSIC PROBLEM: Find K Largest Elements ────────────────────────────────
// Use a MIN-heap of size k. When size exceeds k, pop the smallest.
// What's left are the k largest values.

function kLargest(nums, k) {
  const minHeap = new MinHeap();

  for (const n of nums) {
    minHeap.push(n);
    if (minHeap.size() > k) minHeap.pop(); // remove smallest, keep k largest
  }

  const result = [];
  while (!minHeap.isEmpty()) result.push(minHeap.pop());
  return result.sort((a, b) => b - a); // sort descending
}

// nums=[3,1,5,12,2,11,6,7], k=4
// → after processing: heap contains [5,6,11,12]
// → sorted: [12,11,6,5] ✅

// ─── CLASSIC PROBLEM: Kth Largest in Stream ───────────────────────────────────
class KthLargest {
  constructor(k, nums) {
    this.k    = k;
    this.heap = new MinHeap();
    nums.forEach(n => this.add(n)); // initialize
  }

  add(val) {
    this.heap.push(val);
    if (this.heap.size() > this.k) this.heap.pop(); // keep only k largest
    return this.heap.peek(); // kth largest = min of the k largest = heap root
  }
}
```

-----

### ⏱️ Complexity Table

```
┌─────────────────────────┬───────────┐
│ Operation               │   Time    │
├─────────────────────────┼───────────┤
│ Push (insert)           │ O(log n)  │
│ Pop (extract min/max)   │ O(log n)  │
│ Peek (view min/max)     │  O(1) ✅   │
│ Build from array        │  O(n) ✅   │
│ Search                  │  O(n)     │
└─────────────────────────┴───────────┘
Space: O(n)
```

-----

### 💡 Memory Trick

> **“Hospital ER”** — the most critical patient (min/max priority) is always at the top of the waiting list. New patients are inserted and bubble up if more critical than others.

-----

## 13. Graphs

### 🧠 The Story

Open **Google Maps** on your phone. You see cities (nodes) connected by roads (edges). You want the shortest route from Chennai to Mumbai. Google Maps solves this using graph algorithms.

```
Cities = NODES (vertices)
Roads  = EDGES (connections)

        Chennai ──── Bangalore ──── Hyderabad
           |               |             |
         Madurai       Coimbatore    Vijayawada
                                         |
                                       Mumbai

Every "network" problem is a graph problem:
  Social networks    → people = nodes, friendships = edges
  Internet           → computers = nodes, cables = edges
  Dependencies       → tasks = nodes, "must be done first" = edges
```

-----

### 👁️ Visual — Two Ways to Store a Graph

```
Graph:   A ─── B
         |     |
         D ─── C

1. Adjacency List (memory-efficient, preferred):
   {
     A: [B, D],
     B: [A, C],
     C: [B, D],
     D: [A, C]
   }

2. Adjacency Matrix (fast edge lookup):
       A  B  C  D
   A [ 0, 1, 0, 1 ]
   B [ 1, 0, 1, 0 ]
   C [ 0, 1, 0, 1 ]
   D [ 1, 0, 1, 0 ]
   
   matrix[A][B] = 1 means there IS an edge A→B
   matrix[A][C] = 0 means there is NO edge A→C
```

-----

### 🔧 DFS vs BFS — The Two Fundamental Traversals

```
Graph:      A
           / \
          B   C
         / \   \
        D   E   F

DFS (Depth First Search) — go as deep as possible first:
  A → B → D (dead end, backtrack) → E (dead end, backtrack)
    → C → F (dead end, backtrack)
  Visit order: A, B, D, E, C, F
  Uses: STACK (or recursion)

BFS (Breadth First Search) — visit all neighbours first:
  Level 0: A
  Level 1: B, C       (A's neighbours)
  Level 2: D, E, F    (B's and C's neighbours)
  Visit order: A, B, C, D, E, F
  Uses: QUEUE
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── GRAPH CLASS ──────────────────────────────────────────────────────────────
class Graph {
  constructor(directed = false) {
    this.adjacencyList = {};
    this.directed = directed;
  }

  addVertex(v) {
    if (!this.adjacencyList[v]) this.adjacencyList[v] = [];
  }

  addEdge(v1, v2, weight = 1) {
    this.adjacencyList[v1].push({ node: v2, weight });
    if (!this.directed) {
      this.adjacencyList[v2].push({ node: v1, weight }); // undirected: add both ways
    }
  }

  removeEdge(v1, v2) {
    this.adjacencyList[v1] = this.adjacencyList[v1].filter(e => e.node !== v2);
    if (!this.directed) {
      this.adjacencyList[v2] = this.adjacencyList[v2].filter(e => e.node !== v1);
    }
  }
}

// ─── DFS — Depth First Search ─────────────────────────────────────────────────
// Goes as DEEP as possible before backtracking
// Think: exploring a maze — go until you hit a wall, then backtrack

// Recursive DFS
function dfsRecursive(graph, start) {
  const visited = new Set();
  const result  = [];

  function dfs(vertex) {
    if (!vertex) return;
    visited.add(vertex);
    result.push(vertex);

    for (const { node: neighbor } of graph[vertex]) {
      if (!visited.has(neighbor)) {
        dfs(neighbor); // go deeper!
      }
    }
  }

  dfs(start);
  return result;
}

// Iterative DFS (uses explicit stack)
function dfsIterative(graph, start) {
  const visited = new Set();
  const result  = [];
  const stack   = [start]; // explicit stack

  while (stack.length > 0) {
    const vertex = stack.pop(); // take from TOP of stack

    if (!visited.has(vertex)) {
      visited.add(vertex);
      result.push(vertex);

      for (const { node: neighbor } of graph[vertex]) {
        if (!visited.has(neighbor)) stack.push(neighbor);
      }
    }
  }
  return result;
}

// ─── BFS — Breadth First Search ───────────────────────────────────────────────
// Explores all neighbours at current depth before going deeper
// Think: ripples in a pond — expanding circles

function bfs(graph, start) {
  const visited = new Set([start]);
  const result  = [];
  const queue   = [start]; // use queue!

  while (queue.length > 0) {
    const vertex = queue.shift(); // take from FRONT of queue
    result.push(vertex);

    for (const { node: neighbor } of graph[vertex]) {
      if (!visited.has(neighbor)) {
        visited.add(neighbor);
        queue.push(neighbor); // add to back of queue
      }
    }
  }
  return result;
}

// ─── SHORTEST PATH with BFS (unweighted graph) ────────────────────────────────
// BFS guarantees shortest path in UNWEIGHTED graphs
// because it explores layer by layer

function shortestPath(graph, start, end) {
  if (start === end) return [start];

  const visited  = new Set([start]);
  const queue    = [[start]]; // queue of PATHS (not just nodes)

  while (queue.length > 0) {
    const path   = queue.shift();
    const vertex = path[path.length - 1]; // last node in current path

    for (const { node: neighbor } of graph[vertex]) {
      if (!visited.has(neighbor)) {
        const newPath = [...path, neighbor]; // extend the path

        if (neighbor === end) return newPath; // FOUND shortest path!

        visited.add(neighbor);
        queue.push(newPath);
      }
    }
  }
  return null; // no path found
}

// ─── DIJKSTRA — Shortest Path in WEIGHTED graph ──────────────────────────────
// When roads have different distances (weights), BFS isn't enough
// Dijkstra's algorithm finds the shortest WEIGHTED path

function dijkstra(graph, start) {
  const distances = {};  // shortest known distance to each node
  const visited   = new Set();
  const prev      = {};  // to reconstruct the path
  const heap      = new MinHeap(); // [distance, node]

  // Initialize all distances as Infinity
  for (const node in graph) {
    distances[node] = Infinity;
    prev[node] = null;
  }
  distances[start] = 0;
  heap.push([0, start]); // [cost, node] — sort by cost

  while (!heap.isEmpty()) {
    const [cost, node] = heap.pop();

    if (visited.has(node)) continue; // already found shortest path to this node
    visited.add(node);

    for (const { node: neighbor, weight } of graph[node]) {
      const newDist = cost + weight; // distance through current node

      if (newDist < distances[neighbor]) {
        distances[neighbor] = newDist; // found a shorter path!
        prev[neighbor] = node;         // track path
        heap.push([newDist, neighbor]);
      }
    }
  }

  return { distances, prev };
}

// Reconstruct the actual path
function getPath(prev, start, end) {
  const path = [];
  let current = end;
  while (current) {
    path.unshift(current);
    current = prev[current];
  }
  return path[0] === start ? path : null;
}

// ─── DETECT CYCLE in Undirected Graph ────────────────────────────────────────
function hasCycleUndirected(graph) {
  const visited = new Set();

  function dfs(vertex, parent) {
    visited.add(vertex);

    for (const { node: neighbor } of graph[vertex]) {
      if (!visited.has(neighbor)) {
        if (dfs(neighbor, vertex)) return true; // cycle found deeper
      } else if (neighbor !== parent) {
        return true; // visited AND not parent → cycle!
      }
    }
    return false;
  }

  for (const vertex in graph) {
    if (!visited.has(vertex)) {
      if (dfs(vertex, null)) return true;
    }
  }
  return false;
}

// ─── TOPOLOGICAL SORT (for Directed Acyclic Graph) ───────────────────────────
// Orders nodes so every directed edge A→B has A before B
// Used for: build dependencies, course prerequisites, task scheduling

function topologicalSort(graph) {
  const visited = new Set();
  const stack   = [];

  function dfs(vertex) {
    visited.add(vertex);
    for (const { node: neighbor } of graph[vertex]) {
      if (!visited.has(neighbor)) dfs(neighbor);
    }
    stack.push(vertex); // push AFTER visiting all descendants
  }

  for (const vertex in graph) {
    if (!visited.has(vertex)) dfs(vertex);
  }

  return stack.reverse(); // reverse gives topological order
}
```

-----

### ⏱️ Complexity Table

```
┌─────────────────────────┬────────────────────────────────────────────┐
│ Operation               │ Adjacency List        Adjacency Matrix     │
├─────────────────────────┼──────────────────────────────────────────── │
│ Add vertex              │     O(1)                    O(V²)          │
│ Add edge                │     O(1)                    O(1)           │
│ Remove edge             │     O(E)                    O(1)           │
│ Check edge exists       │     O(V)                    O(1)           │
│ DFS / BFS               │   O(V + E)                O(V²)           │
│ Dijkstra                │ O((V+E) log V)             O(V²)           │
│ Space                   │   O(V + E)                  O(V²)          │
└─────────────────────────┴────────────────────────────────────────────┘
V = vertices (nodes), E = edges (connections)
```

-----

### 💡 Memory Trick

> **“Google Maps”** — cities are nodes, roads are edges. DFS explores one road all the way to its end before turning back. BFS checks every nearby city before going further out.

-----

## 14. Tries (Prefix Trees)

### 🧠 The Story

Have you noticed when you type on your phone, it suggests the **rest of the word** automatically?

```
You type: "Ch"
Phone suggests: "Chennai", "Chicken", "Check", "Chrome"

You type: "Che"
Phone suggests: "Chennai", "Check", "Cheese"

You type: "Che n"
Phone suggests: "Chennai"
```

This instant word lookup is powered by a **Trie**. Every character you type narrows the search through the tree, one level at a time.

-----

### 👁️ Visual — Trie Structure

```
Words stored: ["cat", "car", "card", "care", "dog"]

        (root)
       /      \
      c        d
      |        |
      a        o
     / \       |
    t   r      g ← "dog" ends here ✅
    ✅  |
       / \
      d   e   ← "car" ends at r
      ✅   ✅   "card" ends at d ✅
               "care" ends at e ✅

Each path from root to a ✅ node = one stored word
```

-----

### 💻 Code — Complete with Explanations

```javascript
// ─── TRIE NODE ────────────────────────────────────────────────────────────────
class TrieNode {
  constructor() {
    this.children    = {};     // map: char → TrieNode
    this.isEndOfWord = false;  // marks complete word
  }
}

// ─── TRIE ─────────────────────────────────────────────────────────────────────
class Trie {
  constructor() {
    this.root = new TrieNode();
  }

  // INSERT a word — O(m) where m = word length
  insert(word) {
    let node = this.root;

    for (const ch of word) {
      if (!node.children[ch]) {
        node.children[ch] = new TrieNode(); // create path if missing
      }
      node = node.children[ch]; // walk down
    }

    node.isEndOfWord = true; // mark the end
  }

  // SEARCH exact word — O(m)
  search(word) {
    let node = this.root;

    for (const ch of word) {
      if (!node.children[ch]) return false; // path broken → not found
      node = node.children[ch];
    }

    return node.isEndOfWord; // must be marked as complete word
    // "car" exists, but "ca" might not be a complete word!
  }

  // STARTS WITH prefix — O(m)
  startsWith(prefix) {
    let node = this.root;

    for (const ch of prefix) {
      if (!node.children[ch]) return false;
      node = node.children[ch];
    }

    return true; // the prefix path exists (don't need isEndOfWord)
  }

  // AUTOCOMPLETE — find all words with given prefix — O(m + output)
  autocomplete(prefix) {
    let node = this.root;

    // Navigate to the end of the prefix
    for (const ch of prefix) {
      if (!node.children[ch]) return []; // no words with this prefix
      node = node.children[ch];
    }

    // DFS from that node to find all complete words
    const results = [];
    this._collectWords(node, prefix, results);
    return results;
  }

  _collectWords(node, currentWord, results) {
    if (node.isEndOfWord) results.push(currentWord); // found a complete word!

    for (const [ch, childNode] of Object.entries(node.children)) {
      this._collectWords(childNode, currentWord + ch, results);
    }
  }

  // DELETE a word — O(m)
  delete(word) {
    this._deleteHelper(this.root, word, 0);
  }

  _deleteHelper(node, word, depth) {
    if (!node) return false;

    if (depth === word.length) {
      if (!node.isEndOfWord) return false; // word doesn't exist
      node.isEndOfWord = false; // unmark end
      return Object.keys(node.children).length === 0; // true if we can delete this node
    }

    const ch   = word[depth];
    const canDelete = this._deleteHelper(node.children[ch], word, depth + 1);

    if (canDelete) {
      delete node.children[ch]; // remove dead branch
      return Object.keys(node.children).length === 0 && !node.isEndOfWord;
    }
    return false;
  }
}

// Usage
const trie = new Trie();
["cat", "car", "card", "care", "dog", "dot"].forEach(w => trie.insert(w));

console.log(trie.search("car"));         // true
console.log(trie.search("ca"));          // false (not a full word)
console.log(trie.startsWith("ca"));      // true (prefix exists)
console.log(trie.autocomplete("car"));   // ["car", "card", "care"]
console.log(trie.autocomplete("do"));    // ["dog", "dot"]
console.log(trie.autocomplete("xyz"));   // [] (no words)
```

-----

### ⏱️ Complexity Table

```
┌────────────────────────┬───────────────────────────────────────────┐
│ Operation              │     Time           Space                  │
├────────────────────────┼───────────────────────────────────────────┤
│ Insert word            │  O(m)              O(m)                   │
│ Search word            │  O(m)              O(1)                   │
│ Starts with prefix     │  O(m)              O(1)                   │
│ Autocomplete           │  O(m + results)    O(results)             │
│ Delete word            │  O(m)              O(1)                   │
│ Total space            │  O(n × m)          n=words, m=avg length  │
└────────────────────────┴───────────────────────────────────────────┘
```

-----

### 🎯 When to Use Trie

```
✅ USE when:
   - Autocomplete / search suggestions
   - Spell checking
   - IP routing (longest prefix match)
   - Word games (Boggle, Scrabble word lookup)
   - Counting words with a given prefix

❌ AVOID when:
   - Keys are not strings
   - Memory is very tight (each node can have up to 26 children)
   - Simple key-value lookup (use Hash Map instead)
```

-----

### 💡 Memory Trick

> **“Phone autocomplete”** — each letter you type walks one step deeper in the tree. The suggestions are all the complete words reachable from where you’ve typed so far.

-----

## 15. Segment Trees

### 🧠 The Story

You manage a **cricket scoreboard** tracking ball-by-ball runs for 120 balls. The audience keeps asking:

```
"What were total runs between ball 5 and ball 32?"
"What were total runs between ball 61 and ball 99?"
"Ball 10 score was actually 6, not 4 — update it!"
```

**Naive approach:** Add up scores ball by ball each time → O(n) per query.

**Segment Tree approach:** Pre-build a tree that stores partial sums → O(log n) per query!

-----

### 👁️ Visual — How a Segment Tree Works

```
Array: [1, 3, 5, 7, 9, 11]   (indices 0–5)

Segment Tree (each node = sum of its range):

                  36 [0-5]
                 /         \
           9 [0-2]         27 [3-5]
           /     \         /      \
       4 [0-1]  5[2]   16[3-4]  11[5]
       /     \         /     \
     1[0]   3[1]    7[3]   9[4]

Query sum(1,4): "sum of indices 1 to 4"
  = sum(1,2) + sum(3,4)
  = 3+5 + 7+9
  = 24  (answered in O(log n) steps!)
```

-----

### 💻 Code — Complete with Explanations

```javascript
class SegmentTree {
  constructor(arr) {
    this.n    = arr.length;
    this.tree = new Array(4 * this.n).fill(0); // 4× size for safety
    this._build(arr, 0, 0, this.n - 1);
  }

  // Build the tree — O(n)
  _build(arr, node, start, end) {
    if (start === end) {
      this.tree[node] = arr[start]; // leaf: store the element itself
    } else {
      const mid = Math.floor((start + end) / 2);
      this._build(arr, 2*node+1, start, mid);     // build left child
      this._build(arr, 2*node+2, mid+1, end);     // build right child
      this.tree[node] = this.tree[2*node+1]        // parent = sum of children
                      + this.tree[2*node+2];
    }
  }

  // Range Sum Query [l...r] — O(log n)
  _query(node, start, end, l, r) {
    if (r < start || end < l) return 0;         // completely outside range
    if (l <= start && end <= r) return this.tree[node]; // completely inside
    const mid = Math.floor((start + end) / 2);
    return this._query(2*node+1, start, mid, l, r)  // partial overlap: split
         + this._query(2*node+2, mid+1, end, l, r);
  }

  rangeSum(l, r) {
    return this._query(0, 0, this.n - 1, l, r);
  }

  // Point Update — O(log n)
  _update(node, start, end, idx, newVal) {
    if (start === end) {
      this.tree[node] = newVal; // update the leaf
    } else {
      const mid = Math.floor((start + end) / 2);
      if (idx <= mid) this._update(2*node+1, start, mid, idx, newVal);
      else            this._update(2*node+2, mid+1, end, idx, newVal);
      this.tree[node] = this.tree[2*node+1] + this.tree[2*node+2]; // recompute
    }
  }

  pointUpdate(idx, newVal) {
    this._update(0, 0, this.n - 1, idx, newVal);
  }
}

// Cricket scoreboard
const balls = [2, 4, 1, 6, 0, 4, 3, 1, 6, 2]; // runs per ball
const seg = new SegmentTree(balls);

console.log(seg.rangeSum(1, 4)); // 4+1+6+0 = 11
console.log(seg.rangeSum(0, 9)); // total = 29
seg.pointUpdate(3, 0);           // ball 3 was a no-ball, zero it out
console.log(seg.rangeSum(1, 4)); // 4+1+0+0 = 5
```

-----

### ⏱️ Complexity

```
┌─────────────────┬───────────┬───────────┐
│ Operation       │   Time    │   Space   │
├─────────────────┼───────────┼───────────┤
│ Build           │   O(n)    │   O(n)    │
│ Range query     │  O(log n) │   O(1)    │
│ Point update    │  O(log n) │   O(1)    │
└─────────────────┴───────────┴───────────┘
```

-----

### 💡 Memory Trick

> **“Cricket scoreboard”** — pre-compute sums for every possible range. Any range query answered in log n steps by combining pre-computed sub-ranges.

-----

## 16. Fenwick Tree (Binary Indexed Tree)

### 🧠 The Story

Same cricket scoreboard problem, but with **simpler code and less memory** than a Segment Tree. A Fenwick Tree is a clever array where each index stores a “partial sum” covering a different range of elements.

The magic: **every number stores the count of its lowest set bit worth of elements**.

-----

### 👁️ Visual — What Each Index Stores

```
Array (1-indexed): [2, 4, 1, 6, 0, 4, 3, 1]
                    1  2  3  4  5  6  7  8

Fenwick tree[i] stores sum of:
  index 1 (001): covers [1..1]    → 2
  index 2 (010): covers [1..2]    → 2+4 = 6
  index 3 (011): covers [3..3]    → 1
  index 4 (100): covers [1..4]    → 2+4+1+6 = 13
  index 5 (101): covers [5..5]    → 0
  index 6 (110): covers [5..6]    → 0+4 = 4
  index 7 (111): covers [7..7]    → 3
  index 8 (1000): covers [1..8]   → 2+4+1+6+0+4+3+1 = 21

i & (-i) = isolates the lowest set bit
  6 (110) & -6 (010) = 2  → index 6 covers 2 elements
```

-----

### 💻 Code — Complete with Explanations

```javascript
class FenwickTree {
  constructor(n) {
    this.n    = n;
    this.tree = new Array(n + 1).fill(0); // 1-indexed!
  }

  // Update: add delta to position i — O(log n)
  update(i, delta) {
    for (; i <= this.n; i += i & (-i)) { // i & (-i) = lowest set bit
      this.tree[i] += delta;             // update all responsible indices
    }
  }

  // Prefix sum [1...i] — O(log n)
  prefixSum(i) {
    let sum = 0;
    for (; i > 0; i -= i & (-i)) {      // strip lowest set bit
      sum += this.tree[i];
    }
    return sum;
  }

  // Range sum [l...r] — O(log n)
  rangeSum(l, r) {
    return this.prefixSum(r) - this.prefixSum(l - 1);
  }
}

// Build from array
function buildFenwick(arr) {
  const bit = new FenwickTree(arr.length);
  arr.forEach((val, i) => bit.update(i + 1, val)); // 1-indexed
  return bit;
}

const balls = [2, 4, 1, 6, 0, 4, 3, 1];
const bit = buildFenwick(balls);
console.log(bit.rangeSum(2, 5)); // 4+1+6+0 = 11
bit.update(4, 2);                // add 2 to index 4 (6 becomes 8)
console.log(bit.rangeSum(2, 5)); // 4+1+8+0 = 13
```

-----

### ⏱️ Complexity

```
┌─────────────────┬───────────┬───────────┐
│ Operation       │   Time    │   Space   │
├─────────────────┼───────────┼───────────┤
│ Build           │  O(n log n)│   O(n)   │
│ Prefix sum      │  O(log n) │   O(1)    │
│ Range sum       │  O(log n) │   O(1)    │
│ Point update    │  O(log n) │   O(1)    │
└─────────────────┴───────────┴───────────┘
Simpler to implement than Segment Tree. Use when you only need sum queries.
```

-----

### 💡 Memory Trick

> **“Clever array”** — each cell stores a partial sum determined by its binary representation. Simpler code than segment trees for the same range-sum problem.

-----

## 17. Disjoint Set Union (Union-Find)

### 🧠 The Story

You’re managing a **company merger**. Multiple small companies are merging into groups:

```
Day 1: Company A and Company B merge → Group {A, B}
Day 2: Company C and Company D merge → Group {C, D}
Day 3: Company B and Company C merge → Group {A, B, C, D}

Questions you get daily:
  "Are companies A and D in the same group?" → YES (after day 3)
  "Are companies A and E in the same group?" → NO (E never merged)
```

DSU answers: **“Are these two elements in the same group?”** in nearly O(1) time.

-----

### 👁️ Visual — How Union-Find Works

```
Initial state (each is its own group):
  parent: [0, 1, 2, 3, 4]
           A  B  C  D  E   ← each points to itself

After union(A, B): B's parent → A
  parent: [0, 0, 2, 3, 4]
           A  A  C  D  E

After union(C, D): D's parent → C
  parent: [0, 0, 2, 2, 4]
           A  A  C  C  E

After union(B, C): find(B)=A, find(C)=C, so A's parent → C
  parent: [2, 0, 2, 2, 4]
           C  A  C  C  E

Now find(A): A→C→C (root). find(E): E (root). A≠E → different groups ✅
```

-----

### 💻 Code — Complete with Explanations

```javascript
class DSU {
  constructor(n) {
    this.parent = Array.from({ length: n }, (_, i) => i); // each = own parent
    this.rank   = new Array(n).fill(0); // rank for union by rank
    this.count  = n; // number of distinct groups
  }

  // FIND root with PATH COMPRESSION — O(α(n)) ≈ O(1)
  // Path compression: make every node point directly to root
  find(x) {
    if (this.parent[x] !== x) {
      this.parent[x] = this.find(this.parent[x]); // compress the path!
    }
    return this.parent[x];
  }

  // UNION by rank — O(α(n)) ≈ O(1)
  // Attach smaller tree under larger tree to keep height minimal
  union(x, y) {
    const px = this.find(x);
    const py = this.find(y);

    if (px === py) return false; // already in same group!

    if (this.rank[px] < this.rank[py])       this.parent[px] = py;
    else if (this.rank[px] > this.rank[py])  this.parent[py] = px;
    else {
      this.parent[py] = px;
      this.rank[px]++;
    }

    this.count--;
    return true; // successfully merged two groups
  }

  connected(x, y) {
    return this.find(x) === this.find(y);
  }

  numGroups() {
    return this.count;
  }
}

// ─── CLASSIC PROBLEM 1: Detect cycle in undirected graph ─────────────────────
function hasCycleGraph(n, edges) {
  const dsu = new DSU(n);

  for (const [u, v] of edges) {
    if (!dsu.union(u, v)) return true; // already connected = cycle!
  }
  return false;
}
// edges=[[0,1],[1,2],[2,0]] → hasCycle? Yes → return true ✅

// ─── CLASSIC PROBLEM 2: Number of Connected Components ───────────────────────
function countComponents(n, edges) {
  const dsu = new DSU(n);
  for (const [u, v] of edges) dsu.union(u, v);
  return dsu.numGroups();
}

// ─── CLASSIC PROBLEM 3: Kruskal's MST (Minimum Spanning Tree) ────────────────
// Find the minimum cost to connect all cities (nodes) with minimum total edge weight

function kruskalMST(n, edges) {
  const dsu  = new DSU(n);
  const mst  = [];
  let   cost = 0;

  // Sort edges by weight (cheapest first)
  edges.sort((a, b) => a[2] - b[2]);

  for (const [u, v, w] of edges) {
    if (dsu.union(u, v)) { // only add if it doesn't create a cycle
      mst.push([u, v, w]);
      cost += w;
      if (mst.length === n - 1) break; // MST has n-1 edges
    }
  }

  return { mst, cost };
}
// edges = [[0,1,4],[0,2,3],[1,2,1],[1,3,2],[2,3,4]]
// MST: [(1,2,1),(1,3,2),(0,2,3)] cost=6
```

-----

### ⏱️ Complexity

```
┌───────────────────┬───────────────────────────────────────┐
│ Operation         │           Time                         │
├───────────────────┼───────────────────────────────────────┤
│ find(x)           │ O(α(n)) ≈ O(1) with path compression  │
│ union(x, y)       │ O(α(n)) ≈ O(1) with union by rank     │
│ connected(x, y)   │ O(α(n)) ≈ O(1)                        │
└───────────────────┴───────────────────────────────────────┘
α(n) = inverse Ackermann function ≈ 4 for any practical n
Space: O(n)
```

-----

### 💡 Memory Trick

> **“Company mergers”** — each company belongs to a group. Merging two companies joins their groups. “Are they in the same group?” is answered nearly instantly.

-----

## 18. AVL Trees (Self-Balancing BST)

### 🧠 The Story

A regular BST has a problem. If you insert numbers in sorted order:

```
Insert: 1, 2, 3, 4, 5

BST becomes:
  1
   \
    2
     \
      3
       \
        4
         \
          5

This is a LINKED LIST in disguise! O(n) search, not O(log n)!
```

An **AVL Tree** automatically **rotates** itself to stay balanced. No matter what order you insert, it maintains O(log n) operations.

```
AVL rule: For EVERY node, |height(left) - height(right)| ≤ 1
```

-----

### 👁️ Visual — Rotations

```
LEFT-LEFT case (insert 1 into 3-2-1):

Unbalanced:     3          Balanced:    2
               /                       / \
              2          ──rotate──▶  1   3
             /
            1

RIGHT-RIGHT case (insert 5 into 3-4-5):

Unbalanced: 3              Balanced:   4
             \                        / \
              4            ──────▶  3   5
               \
                5
```

-----

### 💻 Code — Key Concepts

```javascript
class AVLNode {
  constructor(val) {
    this.val    = val;
    this.left   = null;
    this.right  = null;
    this.height = 1; // new node starts at height 1
  }
}

class AVLTree {
  height(node) { return node ? node.height : 0; }

  balanceFactor(node) {
    return this.height(node.left) - this.height(node.right);
    // +2 = too left-heavy → rotate right
    // -2 = too right-heavy → rotate left
  }

  updateHeight(node) {
    node.height = 1 + Math.max(this.height(node.left), this.height(node.right));
  }

  // RIGHT rotation — fixes Left-Left imbalance
  rotateRight(y) {
    const x  = y.left;    // x becomes the new root
    const T2 = x.right;   // T2 moves to y's left

    x.right = y;   // y becomes x's right child
    y.left  = T2;  // T2 becomes y's left child

    this.updateHeight(y); // update heights bottom-up
    this.updateHeight(x);
    return x; // x is now the root of this subtree
  }

  // LEFT rotation — fixes Right-Right imbalance
  rotateLeft(x) {
    const y  = x.right;
    const T2 = y.left;

    y.left  = x;
    x.right = T2;

    this.updateHeight(x);
    this.updateHeight(y);
    return y;
  }

  // INSERT with auto-balancing — O(log n)
  insert(node, val) {
    if (!node) return new AVLNode(val); // base case

    // 1. Normal BST insert
    if (val < node.val)      node.left  = this.insert(node.left, val);
    else if (val > node.val) node.right = this.insert(node.right, val);
    else return node; // duplicate → no change

    // 2. Update height
    this.updateHeight(node);

    // 3. Check balance factor
    const bf = this.balanceFactor(node);

    // 4. Fix imbalance with 4 rotation cases:
    if (bf > 1  && val < node.left.val)  return this.rotateRight(node);      // LL
    if (bf < -1 && val > node.right.val) return this.rotateLeft(node);       // RR
    if (bf > 1  && val > node.left.val) {                                     // LR
      node.left = this.rotateLeft(node.left);
      return this.rotateRight(node);
    }
    if (bf < -1 && val < node.right.val) {                                    // RL
      node.right = this.rotateRight(node.right);
      return this.rotateLeft(node);
    }

    return node; // no rotation needed
  }
}
```

-----

### ⏱️ Complexity

```
┌─────────────────┬──────────────────────────────┐
│ Operation       │           Time               │
├─────────────────┼──────────────────────────────┤
│ Search          │  O(log n) — GUARANTEED!       │
│ Insert          │  O(log n) — GUARANTEED!       │
│ Delete          │  O(log n) — GUARANTEED!       │
└─────────────────┴──────────────────────────────┘
Unlike regular BST which degrades to O(n) on sorted data.
Space: O(n)
```

-----

### 💡 Memory Trick

> **“Self-correcting BST”** — like a yoga instructor that constantly adjusts posture. If the tree leans too far one way, it rotates to restore balance. Always O(log n).

-----

## 19. Red-Black Trees

### 🧠 The Story

Another self-balancing BST, but with different (relaxed) rules. Instead of measuring heights, it uses **colors** (red/black) to maintain rough balance.

```
Rules:
  1. Every node is RED or BLACK
  2. Root is always BLACK
  3. NULL leaves are BLACK
  4. RED nodes can ONLY have BLACK children (no two consecutive reds)
  5. All paths from any node to NULL have the SAME number of BLACK nodes
```

These rules guarantee: **height ≤ 2 × log₂(n+1)**

-----

### 👁️ Visual

```
        13(B)
       /      \
     8(R)     17(R)
    /    \    /    \
  1(B)  11(B) 15(B) 25(B)

Property 4: No red-red parent-child pairs ✅
Property 5: Every path to NULL has 2 black nodes ✅
```

-----

### 🎯 AVL vs Red-Black

```
┌─────────────────────┬────────────┬───────────────────┐
│ Property            │  AVL Tree  │  Red-Black Tree   │
├─────────────────────┼────────────┼───────────────────┤
│ Balance             │  Strict    │  Loose            │
│ Height              │ ≤1.44 log n│ ≤2 log n          │
│ Search speed        │ Slightly + │  OK               │
│ Insert/Delete       │ More rot.  │ Fewer rotations   │
│ Best for            │ Lookup-heavy│Insert/delete-heavy│
│ Used in             │ DB indexes │ Linux, C++ STL    │
└─────────────────────┴────────────┴───────────────────┘
```

-----

### 💡 Memory Trick

> **“Traffic light tree”** — nodes are colored red or green. The coloring rules ensure the tree never becomes lopsided. Used in Linux scheduler and C++ maps.

-----

## 20. Skip Lists

### 🧠 The Story

You’re traveling from Chennai to Delhi by train. Instead of stopping at every small station, express trains **skip intermediate stops** and only stop at major cities. Local trains stop at every station.

A Skip List works the same way:

- **Bottom level** — every element (local train, all stops)
- **Level above** — every other element (semi-express)
- **Level above that** — every fourth element (express)
- **Top level** — only the largest elements (superfast express)

To find an element: start at the top (fast lane), drop down when you overshoot.

-----

### 👁️ Visual

```
Level 3: 1 ─────────────────────────────── 25
Level 2: 1 ─────── 7 ─────────────── 17 ─ 25
Level 1: 1 ─── 4 ─ 7 ─── 11 ─── 17 ───── 25
Level 0: 1 ─ 3─ 4 ─ 7 ─ 9─ 11 ─ 14─17 ─21─25

Finding 14:
  Start at Level 3: 1 → 25 (too far) → drop to Level 2
  Level 2: 1 → 7 → 17 (too far) → drop to Level 1
  Level 1: 7 → 11 → 17 (too far) → drop to Level 0
  Level 0: 11 → 14 ✅ FOUND!
```

-----

### 💻 Code — Key Concepts

```javascript
class SkipListNode {
  constructor(val, level) {
    this.val     = val;
    this.forward = new Array(level + 1).fill(null); // pointers for each level
  }
}

class SkipList {
  constructor(maxLevel = 16, probability = 0.5) {
    this.maxLevel = maxLevel;
    this.p        = probability;
    this.head     = new SkipListNode(-Infinity, maxLevel);
    this.level    = 0;
  }

  // Random level: coin-flip until tails
  randomLevel() {
    let level = 0;
    while (Math.random() < this.p && level < this.maxLevel) level++;
    return level;
  }

  // Search — O(log n) expected
  search(target) {
    let curr = this.head;
    for (let i = this.level; i >= 0; i--) {
      while (curr.forward[i] && curr.forward[i].val < target) {
        curr = curr.forward[i]; // move forward on this level
      }
    }
    curr = curr.forward[0]; // bottom level
    return curr && curr.val === target;
  }

  // Insert — O(log n) expected
  insert(val) {
    const update   = new Array(this.maxLevel + 1).fill(this.head);
    let curr = this.head;

    // Find insertion positions at each level
    for (let i = this.level; i >= 0; i--) {
      while (curr.forward[i] && curr.forward[i].val < val) {
        curr = curr.forward[i];
      }
      update[i] = curr;
    }

    const newLevel = this.randomLevel();
    if (newLevel > this.level) {
      for (let i = this.level + 1; i <= newLevel; i++) update[i] = this.head;
      this.level = newLevel;
    }

    const newNode = new SkipListNode(val, newLevel);
    for (let i = 0; i <= newLevel; i++) {
      newNode.forward[i]   = update[i].forward[i];
      update[i].forward[i] = newNode;
    }
  }
}
```

-----

### ⏱️ Complexity

```
┌─────────────────┬──────────────┬──────────────┐
│ Operation       │   Expected   │  Worst Case  │
├─────────────────┼──────────────┼──────────────┤
│ Search          │  O(log n)    │    O(n)      │
│ Insert          │  O(log n)    │    O(n)      │
│ Delete          │  O(log n)    │    O(n)      │
└─────────────────┴──────────────┴──────────────┘
Space: O(n log n) — extra pointers for multiple levels
```

-----

### 💡 Memory Trick

> **“Express train”** — skip over unimportant stops at high levels, drop down to local level only when near your destination.

-----

## 21. Bloom Filters

### 🧠 The Story

Google Chrome needs to warn you about **malicious websites**. There are billions of known malicious URLs. Chrome can’t download the entire list to your computer.

Instead, it downloads a tiny **Bloom Filter** that can answer:

```
"Is google.com safe?"    → "Definitely NOT malicious"  (100% certain)
"Is evil.com malicious?" → "Possibly malicious"         (might be wrong!)
"Is phish.net malicious?"→ "Definitely NOT malicious"  (100% certain)
```

A Bloom Filter never misses a malicious site (no false negatives), but occasionally flags a safe site as suspicious (false positives are OK — just do a full check then).

-----

### 👁️ Visual — How Bloom Filter Works

```
Bit array: [0,0,0,0,0,0,0,0,0,0]  (size 10, all zeros)

Add "apple":
  hash1("apple") = 3 → set bit 3
  hash2("apple") = 6 → set bit 6
  hash3("apple") = 9 → set bit 9
  Bit array: [0,0,0,1,0,0,1,0,0,1]

Add "cat":
  hash1("cat") = 1 → set bit 1
  hash2("cat") = 4 → set bit 4
  hash3("cat") = 7 → set bit 7
  Bit array: [0,1,0,1,1,0,1,1,0,1]

Check "dog":
  hash1("dog") = 2 → bit 2 = 0 → "dog" DEFINITELY NOT in set ✅

Check "app":
  hash1("app") = 3 → bit 3 = 1 ✓
  hash2("app") = 6 → bit 6 = 1 ✓
  hash3("app") = 1 → bit 1 = 1 ✓
  All bits set → "app" POSSIBLY in set
  (It's actually NOT, but all 3 hash positions were set by "apple" and "cat")
  This is a FALSE POSITIVE.
```

-----

### 💻 Code — Conceptual Implementation

```javascript
class BloomFilter {
  constructor(size = 1000, numHashes = 3) {
    this.size      = size;
    this.bits      = new Uint8Array(size); // compact bit array
    this.numHashes = numHashes;
  }

  // k different hash functions (simulated with seeds)
  _hash(value, seed) {
    let hash = seed;
    for (let i = 0; i < value.length; i++) {
      hash = (hash * 31 + value.charCodeAt(i)) % this.size;
    }
    return Math.abs(hash);
  }

  // Add element — set k bits
  add(value) {
    for (let i = 0; i < this.numHashes; i++) {
      const idx = this._hash(value, i * 7919); // different seed per hash fn
      this.bits[idx] = 1;
    }
  }

  // Check membership — O(k) ≈ O(1)
  contains(value) {
    for (let i = 0; i < this.numHashes; i++) {
      const idx = this._hash(value, i * 7919);
      if (!this.bits[idx]) return false; // definitely NOT present
    }
    return true; // POSSIBLY present (may be false positive)
  }
}

const bf = new BloomFilter(100, 3);
["apple", "cat", "dog", "react", "node"].forEach(w => bf.add(w));

console.log(bf.contains("apple"));  // true  (100% correct — added it)
console.log(bf.contains("react"));  // true  (100% correct — added it)
console.log(bf.contains("java"));   // likely false (not added)
// NOTE: A false positive means contains() returns true for something never added
// This is rare but possible. The benefit: O(1) lookup, tiny memory footprint.
```

-----

### ⏱️ Complexity

```
┌────────────────┬────────┬────────────────────────────────────┐
│ Operation      │  Time  │  Notes                             │
├────────────────┼────────┼────────────────────────────────────┤
│ Add element    │  O(k)  │ k = number of hash functions ≈ O(1)│
│ Check (lookup) │  O(k)  │ ≈ O(1)                             │
│ Delete         │  ❌     │ NOT supported in basic Bloom filter│
└────────────────┴────────┴────────────────────────────────────┘
Space: O(m) where m = bit array size (much smaller than storing actual items!)
False positive rate decreases with more bits and more hash functions.
```

-----

### 💡 Memory Trick

> **“Chrome safe-browsing”** — a tiny filter that instantly tells you if a site is safe. Never misses a dangerous site (no false negatives), but occasionally suspects an innocent site (false positive). Space-efficient masterpiece.

-----

## 22. Master Cheat Sheet

### 🗂️ All Data Structures — One-Line Story + Speed

```
┌───────────────────────┬────────────────────────────────┬────────────────────────────────────────┐
│ Data Structure        │ Real-Life Story                │ Best For                               │
├───────────────────────┼────────────────────────────────┼────────────────────────────────────────┤
│ Array                 │ Cinema row with seat numbers   │ Fast index access, iteration           │
│ String                │ Pearl necklace                 │ Text manipulation, pattern matching    │
│ Linked List           │ Treasure hunt (follow pointers)│ Frequent insert/delete at head         │
│ Doubly Linked List    │ Train with forward+back doors  │ LRU Cache, deque, fast tail delete     │
│ Stack                 │ Stack of plates (LIFO)         │ Undo/redo, call stack, DFS             │
│ Queue                 │ Bank line (FIFO)               │ Scheduling, BFS, producer-consumer     │
│ Hash Table/Map        │ Library Dewey Decimal system   │ Fast key-value lookup O(1)             │
│ Set                   │ Unique stamp collection        │ Deduplication, fast membership check   │
│ Binary Tree           │ Family tree (parent+2 children)│ Hierarchical data representation       │
│ BST                   │ School library left-right rule │ Sorted data, range queries             │
│ Heap/Priority Queue   │ Hospital ER triage             │ Min/Max in O(1), priority scheduling  │
│ Graph                 │ Google Maps (cities + roads)   │ Networks, shortest path, dependencies  │
│ Trie                  │ Phone autocomplete             │ String prefix search, autocomplete     │
│ Segment Tree          │ Cricket scoreboard ranges      │ Range queries + point updates          │
│ Fenwick Tree          │ Clever partial-sum array       │ Prefix sums, simpler than segment tree │
│ Union-Find (DSU)      │ Company mergers                │ Connected components, cycle detection  │
│ AVL Tree              │ Self-correcting BST (yoga pose)│ Guaranteed O(log n), lookup-heavy apps │
│ Red-Black Tree        │ Color-coded balanced BST       │ Insert/delete-heavy apps (Linux, STL)  │
│ Skip List             │ Express train skipping stops   │ Sorted sets, alternative to BST        │
│ Bloom Filter          │ Chrome malware URL check       │ Membership with tiny memory footprint  │
└───────────────────────┴────────────────────────────────┴────────────────────────────────────────┘
```

-----

### ⏱️ Complete Time Complexity Reference

```
┌──────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
│ Structure        │ Access   │ Search   │ Insert   │ Delete   │ Min/Max  │  Space   │
├──────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
│ Array            │  O(1)✅  │  O(n)    │  O(n)    │  O(n)    │  O(n)    │  O(n)    │
│ Linked List      │  O(n)    │  O(n)    │  O(1)*   │  O(1)*   │  O(n)    │  O(n)    │
│ Stack            │  O(n)    │  O(n)    │  O(1)✅  │  O(1)✅  │  O(n)    │  O(n)    │
│ Queue            │  O(n)    │  O(n)    │  O(1)✅  │  O(1)✅  │  O(n)    │  O(n)    │
│ Hash Table       │  O(1)✅  │  O(1)✅  │  O(1)✅  │  O(1)✅  │  O(n)    │  O(n)    │
│ BST (balanced)   │ O(logn)✅│ O(logn)✅│ O(logn)✅│ O(logn)✅│ O(logn)✅│  O(n)    │
│ BST (skewed)     │  O(n)    │  O(n)    │  O(n)    │  O(n)    │  O(n)    │  O(n)    │
│ AVL Tree         │ O(logn)✅│ O(logn)✅│ O(logn)✅│ O(logn)✅│ O(logn)✅│  O(n)    │
│ Red-Black Tree   │ O(logn)✅│ O(logn)✅│ O(logn)✅│ O(logn)✅│ O(logn)✅│  O(n)    │
│ Heap (Min/Max)   │  O(n)    │  O(n)    │ O(logn)  │ O(logn)  │  O(1)✅  │  O(n)    │
│ Trie             │  O(m)    │  O(m)    │  O(m)    │  O(m)    │  O(m)    │ O(n×m)   │
│ Segment Tree     │ O(logn)  │  O(n)    │ O(logn)  │ O(logn)  │ O(logn)  │  O(n)    │
│ Skip List (avg)  │ O(logn)  │ O(logn)  │ O(logn)  │ O(logn)  │ O(logn)  │O(n logn) │
│ Bloom Filter     │   N/A    │  O(k)✅  │  O(k)✅  │   N/A    │   N/A    │  O(m)✅  │
└──────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

* at known position     m = key/word length     k = num hash functions
✅ = particularly good for this operation
```

-----

### 🎯 “Which Structure Should I Use?” — Decision Tree

```
What do you need most?
│
├── Fast access by POSITION/INDEX?
│     → Array ✅
│
├── Fast KEY-VALUE lookup?
│     → Hash Map ✅
│
├── Unique values only?
│     → Set ✅
│
├── LIFO (undo, call stack)?
│     → Stack ✅
│
├── FIFO (scheduling, BFS)?
│     → Queue ✅
│
├── Always get MIN or MAX instantly?
│     → Heap (Priority Queue) ✅
│
├── String PREFIX search / autocomplete?
│     → Trie ✅
│
├── SORTED data + fast search/insert/delete?
│     ├── Guaranteed balance needed?
│     │     → AVL Tree or Red-Black Tree ✅
│     └── Accept occasional degradation?
│           → BST ✅
│
├── Network / relationship data?
│     → Graph ✅
│     ├── Shortest path (unweighted)?
│     │     → BFS
│     ├── Shortest path (weighted)?
│     │     → Dijkstra's
│     └── Connected components?
│           → Union-Find (DSU) ✅
│
├── Range queries (sum/min/max) with updates?
│     ├── Need range updates too?
│     │     → Segment Tree ✅
│     └── Only prefix sum / point update?
│           → Fenwick Tree ✅
│
├── Frequent insert/delete at start?
│     → Linked List ✅
│
└── Membership check with tiny memory?
      → Bloom Filter ✅
```

-----

### 🧠 Pattern → Data Structure Mapping

```
Problem Pattern                    Best Data Structure
─────────────────────────────────  ──────────────────────────────
"Is X in the collection?"          Hash Set or Bloom Filter
"How many times does X appear?"    Hash Map (frequency counter)
"What came most recently?"         Stack
"What came first?"                 Queue
"What is the maximum/minimum?"     Heap
"Find X in sorted data"            BST or Binary Search on Array
"Words starting with prefix"       Trie
"Shortest route between A and B"   BFS (unweighted) / Dijkstra (weighted)
"Are A and B connected?"           Union-Find (DSU)
"Sum of elements from i to j"      Segment Tree / Fenwick Tree
"Undo the last N operations"       Stack
"Rank items by priority"           Heap (Priority Queue)
"Store parent-child relationship"  Tree
"Find all groups/clusters"         Graph + DFS/BFS or Union-Find
"Maintain sorted order quickly"    AVL Tree / Red-Black Tree
```

-----

### 💡 All Memory Tricks — One Page

```
Array         → Cinema seats. Numbered, instant access, shift to rearrange
String        → Pearl necklace. Immutable — restring to change one pearl
Linked List   → Treasure hunt. Follow clues; can't skip to clue #7 directly
Stack         → Plate stack. Last in, first out (LIFO). Always work the top
Queue         → Bank line. First in, first out (FIFO). Join back, leave front
Hash Map      → Library Dewey Decimal. Name → number → direct shelf access
Set           → Unique stamp collection. No duplicates. Instant membership
Binary Tree   → Family tree. One root, each parent has at most two children
BST           → Left shelf = smaller, right shelf = larger. Always
Heap          → Hospital ER. Most critical always at top. Auto-rebalances
Graph         → Google Maps. Cities = nodes, roads = edges
Trie          → Phone autocomplete. Each letter = one step deeper in tree
Segment Tree  → Cricket scoreboard. Pre-computed range sums. O(log n) queries
Fenwick Tree  → Clever partial-sum array. Simpler version of segment tree
Union-Find    → Company mergers. Instantly answer "same group?" queries
AVL Tree      → Yoga-pose BST. Auto-rotates to stay perfectly balanced
Red-Black     → Traffic-light BST. Colored nodes ensure rough balance
Skip List     → Express train. Skip stops using fast-lane lanes
Bloom Filter  → Chrome safety check. Tiny memory, possible false positives
```

-----

### 📊 Visual Speed Comparison — n = 1000

```
Operation: SEARCH for a value

Array (unsorted)  [██████████████████████████████████████████] 1,000 steps
Linked List       [██████████████████████████████████████████] 1,000 steps
Hash Table        [█] 1 step (with good hash)
BST (balanced)    [████] ~10 steps (log₂ 1000 ≈ 10)
Binary Search     [████] ~10 steps (array must be sorted)
Trie              [███] ~m steps (m = word length ≈ 5-10)

Operation: INSERT a value

Array (at start)  [██████████████████████████████████████████] 1,000 shifts
Linked List (head)[█] 1 step
Hash Table        [█] 1 step (average)
BST (balanced)    [████] ~10 steps
Heap              [████] ~10 steps (log n)
Stack/Queue       [█] 1 step

Operation: GET MINIMUM

Array (unsorted)  [██████████████████████████████████████████] 1,000 checks
BST (balanced)    [████] ~10 steps (leftmost node)
Heap              [█] 1 step ← best for this!
```

-----

*“Choose the right tool for the job.  
An Array is not always wrong — it’s wrong when you need something else.”*

-----

> 🎯 **Key Takeaway:** There is no single “best” data structure. Each one is optimized for a different set of operations. Understanding the trade-offs between them — speed, memory, ordering, flexibility — is what separates a good developer from a great one.

-----

*Made with ❤️ for Murugesh — from absolute beginner to super advanced*