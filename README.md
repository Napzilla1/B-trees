# 🌳 B+ Tree & Extendible Hashing

C++ implementations of two important **database indexing techniques**:

- 🌳 **B+ Tree** — efficient ordered search and range queries
- 🧮 **Extendible Hashing** — fast dynamic hash-based lookup

Both implementations include interactive CLI interfaces for **insertion, deletion, searching, and visualization**.

## 📁 Project Structure

```text
BPlusTree-ExtendibleHashing/
├── src/
│   ├── BPlusTree.cpp
│   └── ExtendibleHashing.cpp
├── README.md
└── LICENSE
```

## 🌳 B+ Tree

A balanced multi-way search tree where data is stored in linked leaf nodes.

```text
              [20 | 40]
             /    |    \
        [10|15] [25|30] [45|60]
             └─────→─────→
```

**Complexity:** `O(log n)` search, insertion, and deletion.

### Run

```bash
g++ -std=c++11 -O2 -o bptree src/BPlusTree.cpp
./bptree
```

Commands:

```text
i <value>   Insert
d <value>   Delete
s <value>   Search
p           Print tree
h           Help
q           Quit
```

## 🧮 Extendible Hashing

A dynamic hashing technique using a directory and buckets.

```text
Directory
00 ──┐
10 ──┴──> [4, 12]

01 ──┐
11 ──┴──> [7, 15]
```

It uses **global depth** and **local depth** to dynamically split buckets and expand the directory.

**Average complexity:** `O(1)` search, insertion, and deletion.

### Run

```bash
g++ -std=c++11 -O2 -o extendible src/ExtendibleHashing.cpp
./extendible
```

Menu:

```text
1 → Insert
2 → Delete
3 → Print Directory
4 → Exit
```

## ⚖️ Comparison

| Feature        | B+ Tree    | Extendible Hashing |
| -------------- | ---------- | ------------------ |
| Search         | `O(log n)` | `O(1)` avg.        |
| Ordered data   | ✅         | ❌                 |
| Range queries  | ✅         | ❌                 |
| Point lookup   | ✅         | ✅                 |
| Dynamic growth | Node split | Bucket split       |

## 🛠️ Requirements

- C++11 or later
- g++ / clang++ / MSVC
- No external libraries

