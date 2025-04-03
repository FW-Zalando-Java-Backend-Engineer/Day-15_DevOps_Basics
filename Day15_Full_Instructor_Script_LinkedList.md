
# 👨‍🏫 Full-Day Instructor Script – Day 15: Java Collections – LinkedList

---

## 🕘 00:00 - 00:10 | **Warm-up & Recap**

**Instructor says:**
> "Good morning, team! Let’s warm up with a quick recap of yesterday. Who can remind us what an `ArrayList` is great at?"

**Ask students:**
- "What are the benefits of ArrayList?"
- "Why is random access fast in an ArrayList?"

**Then say:**
> "Today we’ll explore a sibling of ArrayList – the `LinkedList`. While it looks similar on the surface, its internal structure is *very* different."

---

## 🕐 00:10 - 00:25 | **Theoretical Introduction: LinkedList**

### Instructor Explanation

> “A `LinkedList` is a sequence of nodes. Each node stores some data, and a reference to the previous and next node. This is called a **doubly-linked list**.”

### Whiteboard:
Draw the following:

```text
NULL <- [ A ] <-> [ B ] <-> [ C ] -> NULL
```

**Explain:**
- `addFirst()` inserts a node at the start in **O(1)** time.
- `removeLast()` removes from the end, also in **O(1)**.
- Access by index is **O(n)** because we must traverse the list.

---

## 🕑 00:25 - 00:40 | **Visual Comparison: LinkedList vs ArrayList**

### Whiteboard Table:

| Feature             | ArrayList | LinkedList |
|---------------------|-----------|------------|
| Random access       | O(1) ✅   | O(n) ❌    |
| Add/remove front    | O(n) ❌   | O(1) ✅    |
| Add/remove end      | O(1) ✅   | O(1) ✅    |
| Memory usage        | Less ✅   | More ❌    |

**Ask students:**
> “So, when would you use a LinkedList in a real app?”

---

## 🕒 00:40 - 01:00 | **Live Coding: RecentFilesTrackerApp**

**Explain:**
> “Let’s simulate a file history tracker, like in an IDE. New files are added to the top, and old files can be cleared from the end.”

Walk through each part of the `RecentFilesTrackerApp.java` code:
- `addFirst()`
- `removeLast()`
- Menu system using `Scanner`

Encourage questions at each step.

---

## 🕓 01:00 - 01:15 | **Live Discussion: What’s Happening Internally?**

Use ASCII diagram:

```text
addFirst("D")
NULL <- [ D ] <-> [ A ] <-> [ B ] -> NULL
```

**Ask:**
- “How many nodes were updated?”
- “What if this were an ArrayList?”

---

## 🕔 01:15 - 01:30 | **Mini Quiz Time**

Distribute or display the following questions:

1. What is the time complexity of `addFirst()`?
2. Which is better for random access: ArrayList or LinkedList?
3. Which one uses more memory?
4. How would you implement a queue using LinkedList?

**Discuss answers together.**

---

## 🕕 01:30 - 01:45 | **Student Exercise**

🧪 Challenge:
> "Extend the file tracker to only keep the last 5 files. When the 6th is added, remove the oldest."

🧩 Bonus:
- Add a search feature
- Allow reverse order printing

---

## 🕖 01:45 - 02:00 | **Wrap-Up and Takeaways**

Ask:
- “What real-life use cases need LinkedList behavior?”
- “Would you use it for storing customer records? Why or why not?”

📌 Summarize:
- LinkedList = great for dynamic insert/remove
- ArrayList = best for access-heavy logic
- Always think in terms of **access pattern + data volume**

---

## ✅ Homework / Extension

Assign:
- Create a navigation history app (like a browser)
- Implement undo/redo using LinkedList
- Read: [LinkedList in Oracle Docs](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html)

---

**End of Script** – You’re all set to lead a smooth and engaging Day 15 session!
