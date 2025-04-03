
# 👨‍🏫 Instructor Guide – Day 15: Java Collections – LinkedList

## 📘 Topic Objective
Introduce students to Java's `LinkedList`, focusing on:
- Its structure and internal behavior
- When to use it over `ArrayList`
- Real-world example with live code and user interaction

---

## 🔬 What is a LinkedList?

A `LinkedList` is a linear data structure made up of **nodes**.  
Each node contains:
- A **data value**
- A **reference to the next node**
- A **reference to the previous node** (in doubly linked lists)

---

## 🧠 Key Properties

| Property            | LinkedList             | ArrayList             |
|---------------------|------------------------|------------------------|
| Access by index     | O(n) ❌               | O(1) ✅               |
| Insert at front     | O(1) ✅               | O(n) ❌               |
| Remove at front     | O(1) ✅               | O(n) ❌               |
| Memory              | Extra node overhead ❌ | More compact ✅       |
| Best for            | Queues, frequent inserts | Fast reads, random access |

---

## ✍️ Whiteboard Visualization

### Doubly Linked List Structure

```
NULL <- [ A ] <-> [ B ] <-> [ C ] -> NULL
```

- `addFirst("D")` inserts node before A:
```
NULL <- [ D ] <-> [ A ] <-> [ B ] <-> [ C ] -> NULL
```

- `removeLast()` removes the last node:
```
NULL <- [ D ] <-> [ A ] <-> [ B ] -> NULL
```

### LinkedList vs ArrayList
```
ArrayList: [A][B][C]
Add at index 0 → shift → [D][A][B][C] ❌ Slow

LinkedList: [A] <-> [B] <-> [C]
Add at front → link [D] → [D] <-> [A] ✅ Fast
```

---

## 🧑‍💻 Live Demo Code: RecentFilesTrackerApp

```java
import java.util.LinkedList;
import java.util.Scanner;

public class RecentFilesTrackerApp {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        LinkedList<String> recentFiles = new LinkedList<>();
        boolean running = true;

        System.out.println("📁 Welcome to the Recent Files Tracker!");

        while (running) {
            System.out.println("\nChoose an option:");
            System.out.println("1. Open a file");
            System.out.println("2. View recent files");
            System.out.println("3. Remove the oldest file");
            System.out.println("4. Exit");
            System.out.print("👉 Your choice: ");

            int choice = scanner.nextInt();
            scanner.nextLine(); // consume newline

            switch (choice) {
                case 1:
                    System.out.print("Enter file name to open: ");
                    String newFile = scanner.nextLine();
                    recentFiles.addFirst(newFile);
                    System.out.println("✅ " + newFile + " opened and added to the top of the list.");
                    break;
                case 2:
                    if (recentFiles.isEmpty()) {
                        System.out.println("📂 No files have been opened yet.");
                    } else {
                        System.out.println("🗂️ Recently Opened Files:");
                        for (int i = 0; i < recentFiles.size(); i++) {
                            System.out.println((i + 1) + ". " + recentFiles.get(i));
                        }
                    }
                    break;
                case 3:
                    if (!recentFiles.isEmpty()) {
                        String removedFile = recentFiles.removeLast();
                        System.out.println("🗑️ Removed the oldest file: " + removedFile);
                    } else {
                        System.out.println("⚠️ No files to remove.");
                    }
                    break;
                case 4:
                    running = false;
                    System.out.println("👋 Exiting the app. See you soon!");
                    break;
                default:
                    System.out.println("❌ Invalid choice. Please try again.");
            }
        }

        scanner.close();
    }
}
```

---

## 💬 Instructor Tips

- Simulate the structure with students (nodes holding hands).
- Use visual cues to explain how add/remove works in O(1).
- Compare performance with ArrayList when adding/removing.
- Bonus: Have students implement a "Recent Files" cap of 5 items.

---

## 🎯 Questions to Ask Students

1. Why is `LinkedList` better than `ArrayList` for this use case?
2. What would happen internally if we used `ArrayList.add(0, item)` repeatedly?
3. Why is `get(index)` slower in `LinkedList`?
4. What’s the time complexity of `addFirst()` and `removeLast()`?
5. How would you adapt this to act like a queue or stack?

---
