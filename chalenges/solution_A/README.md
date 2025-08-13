## 🧠 Section A: Logical Thinking & System Design

**Scenario:**  
You're building a system to track borrowed library books. Think through how you'd structure the data and design the system to handle scale and prevent errors.

---

### ✍️ Challenge Instructions

Answer the following questions **briefly and clearly**. Use bullet points or short sentences where helpful.

---

### 📚 1. Three pieces of data to store for each book:
- What key information would help identify and manage each book?

- **Book ID** (unique identifier for each book edition like ISNB)
- **Book Title & Author** (basic bibliographic information for user-friendly display and search)
- **Availability status** (e.g., "Available", "Borrowed" or "Reserved")


---

### 🚫 2. How to prevent the same book from being borrowed twice:
- What logic or system check would you implement?
- Implement a check on the Availability Status before borrowing: when a user attempts to borrow a book, the system first checks the book's Status field. If it's "Available," the status is immediately updated to "Borrowed" in the same operation.
- Use database-level locking or transactions to ensure only one borrow operation can occur at a time for a given book ID.


---

### 📈 3. Scaling to 10,000 books and 1,000 users — what needs to change:
- What would you update in your design or infrastructure to handle this growth?
- Use database indexing (e.g., on Book ID, User ID, status) for faster searches.
- Implement caching mechanisms to reduce database queries and improve performance.
- Move to a more scalable database such as PostgreSQL to handle concurrent access, structured data and transactions efficiently.
- Ensure the system supports concurrent transactions without conflicts.
- Implement search filters and pagination to manage UI and performance.

---

### 🔄 4. Store book info and borrowing record together or separately — why?
- Share your reasoning for how you'd structure the data.
- **Store separately** — Book info (ISBN, title, author) changes rarely, borrowing records (borrower, borrow date, return date) change often.

**Reasoning:**
Redundancy Reduction: Separating prevents duplicating book information every time it's borrowed.
Query Efficiency: Separating makes it easier to search for all books by an author (querying the books table) or find all books a user has ever borrowed (querying the borrows table).
Flexibility: Separating allows a single book to have multiple borrowing records over its lifetime without cluttering the book's main entry.

---

Take your time to think through each part. We're looking for clarity, logic, and practical design thinking. Good luck!
