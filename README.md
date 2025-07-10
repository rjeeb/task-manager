# 📘 Problem Statement: Task Manager

You are required to build a **simple command-line task manager** in Java that allows users to manage their daily tasks. The application should support creating, viewing, updating, deleting, and filtering tasks.

## ✅ Features

- **Add a Task**
  - Title
  - Description
  - Due Date (in format `yyyy-MM-dd`)
  - Status (`pending` or `done`)

- **View All Tasks**
  - The user can list all tasks stored in the system.

- **Update a Task**
  - The user can update any task's title, description, due date, or status by providing the task ID.

- **Delete a Task**
  - The user can delete a task using its ID.

- **Filter Tasks**
  - Filter tasks by status (`pending` or `done`)
  - Filter tasks by due date

- **Persist Data in Files**
  - All tasks must be saved to a file.
  - The application must read tasks from the file on startup and write changes after any operation.
  - The file should be in a simple CSV format:

```
id,title,description,due_date,status
1,Buy groceries,Milk and eggs,2025-07-11,pending
2,Clean room,Clean bedroom and desk,2025-07-12,done
```

- **Recurring Tasks**
  - When adding a task, the user can optionally specify a `recurrence` value:
    - `none` (default)
    - `daily`
    - `weekly`
    - `monthly`
  - When a recurring task is marked as `done`, a new task should be automatically created with:
    - The same title and description
    - A new due date, based on the recurrence pattern
    - Status set to `pending`
    - The same recurrence value

  - **Behavior:**
    - If a task is marked as `done` after its due date, the new task should still be created based on the original recurrence pattern.
    - Only one new task is created per completion (no backfilling).
    - The system does **not** automatically create missed recurring tasks unless explicitly extended to do so.

  - **Example:**
    If a task is:
    ```
    id: 3
    title: Water the plants
    description: Balcony and living room
    due_date: 2025-07-10
    status: done
    recurrence: daily
    ```

    Then a new task should be automatically added:
    ```
    id: 4
    title: Water the plants
    description: Balcony and living room
    due_date: 2025-07-11
    status: pending
    recurrence: daily
    ```

## 📂 Technical Requirements

- The application must be written in **plain Java**.
- It must use **basic data types** and **standard data structures** (`List`, `Array`, `Map`, etc.).
- File operations must be handled using Java I/O (`FileReader`, `FileWriter`, `BufferedReader`, etc.).
- The application should run from the command line and use `Scanner` or similar classes for input.

## 📤 Deliverables

- The full Java project with all source files.
- All code must be pushed to a public GitHub repository.
- Commit messages must clearly describe the changes made.

## ❌ Restrictions

- Do **not** use any external libraries or frameworks.
- Do **not** use ChatGPT or similar tools to assist in solving the problem.
- Do **not** use any graphical user interface (GUI).
