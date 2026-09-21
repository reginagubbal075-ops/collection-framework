# Java Collection Framework

📄 Full PDF: [COLLECTION_FRAMEWORK.pdf](COLLECTION_FRAMEWORK.pdf)

---

## 1. Collection Framework Foundation

### 1. Introduction to Collections
- What is a Collection?
- What is Collection Framework?
- Why do we need Collections?
- Advantages of Collection Framework
- Real-life examples

### 2. Arrays vs Collections
- Limitations of arrays
- Fixed size vs dynamic size
- Arrays vs Collections
- When to use arrays
- When to use collections

### 3. Collection Framework Hierarchy

```text
                Iterable
                    │
               Collection
                    │
       ┌────────────┼────────────┐
       ↓            ↓            ↓
      List          Set         Queue
       │            │            │
       ↓            ↓            ↓
   ArrayList      HashSet     PriorityQueue
   LinkedList     LinkedHashSet
   Vector         TreeSet
   Stack
```

And separately:

```text
                    Map
                     │
          ┌──────────┼──────────┐
          ↓          ↓          ↓
      HashMap  LinkedHashMap  TreeMap
```

> **Very important:** Map is part of the Collection Framework, but Map does **not** extend the Collection interface.

### 4. Important Interfaces
- Iterable
- Collection
- List
- Set
- Queue
- Map

### 5. Generics

```java
ArrayList<String> names;
```

What does `<String>` mean?
- Generics
- Type safety
- Why generics are useful
- Basic generic syntax

---

## 2. The Main Collections

### 1. List
A List is used when:
- Order matters
- Duplicates are allowed
- Elements are accessed using indexes

Example: `10, 20, 20, 30` (duplicates allowed)

**A. ArrayList**
- Creating, adding, accessing, updating, removing, searching elements
- Iterating
- Size
- Common methods
- Advantages/disadvantages

```java
ArrayList<String> names = new ArrayList<>();
```

**B. LinkedList**
- Concept, basic working
- Adding/removing elements
- Common methods
- ArrayList vs LinkedList

**C. Vector**
- Concept, features, basic methods
- Vector vs ArrayList

**D. Stack** — LIFO (Last In → First Out)
- `push()`, `pop()`, `peek()`, `empty()`

### 2. Set
Used when you want **unique elements**: `10, 20, 10, 30` → `10, 20, 30`

| Type | Unique | Ordering |
|---|---|---|
| HashSet | ✅ | No guaranteed order |
| LinkedHashSet | ✅ | Insertion order |
| TreeSet | ✅ | Sorted order |

### 3. Queue
Follows **FIFO — First In, First Out** (like a line at a ticket counter).

- `add()`, `offer()`, `remove()`, `poll()`, `peek()`, `element()`

**PriorityQueue**
- Priority-based processing
- Basic operations
- Difference between Queue and PriorityQueue

### 4. Map
Stores data as **KEY → VALUE** (like a dictionary: WORD → MEANING).

```text
101 → Regina
102 → Priya
103 → Anjali
```

**A. HashMap**
- Keys must be unique; values can be duplicated
- `put()`, `get()`, `remove()`, `containsKey()`, `containsValue()`

```java
HashMap<Integer, String> students = new HashMap<>();
students.put(101, "Regina");
students.put(102, "Priya");
```

| Type | Behaviour |
|---|---|
| HashMap | Fast general-purpose map, no guaranteed order |
| LinkedHashMap | Maintains insertion order |
| TreeMap | Sorted by keys |

---

## 3. Collections in Real Java Programming

### 1. Iterating Through Collections

Enhanced for loop:
```java
for (String name : names) {
    System.out.println(name);
}
```

Iterator:
```java
Iterator<String> it = names.iterator();
```
- `hasNext()`, `next()`, `remove()`

ListIterator:
- Forward and backward traversal
- `hasPrevious()`, `previous()`

### 2. Collections Class
Utility class `Collections`: `sort()`, `reverse()`, `shuffle()`, `max()`, `min()`, `frequency()`, `swap()`

```java
Collections.sort(numbers);
```

### 3. Comparable
Defines the natural/default ordering of objects via `compareTo()`.

### 4. Comparator
Defines custom ordering via `compare()` — e.g. sort Students by Name, Age, or Marks.

| Comparable | Comparator |
|---|---|
| `compareTo()` | `compare()` |
| Natural ordering | Custom ordering |
| Usually defined inside the class | Separate comparison logic |
| One main ordering | Can define multiple orderings |

> **Memory trick:** Comparable = "I compare myself." Comparator = "Someone else compares the objects."

### 5. Important Collection Methods
`add()`, `addAll()`, `remove()`, `removeAll()`, `contains()`, `containsAll()`, `size()`, `isEmpty()`, `clear()`, `get()`, `set()`, `indexOf()`

Don't memorize them randomly — learn them according to the collection you're using.

### 6. Exception Handling with Collections
- `ConcurrentModificationException`
- `IndexOutOfBoundsException`
- `NoSuchElementException`
