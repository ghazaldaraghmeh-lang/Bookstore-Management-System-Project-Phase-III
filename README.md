# COMP133 – Bookstore Management System (Phase 3)

## Project Description

In this phase, the Bookstore Management System is extended by adding book names to the functions implemented in Phase 2.

The program allows users to add, remove, search for, and print books. Each book contains the following information:

- **Book Name:** A string representing the book's name.
- **Bin Number:** An integer identifying the book.
- **Price:** A `double` representing the book's price.

The program uses parallel arrays to store book names, bin numbers, and prices. It also loads book information from `books.txt` when the program starts and saves all changes to the same file when the program exits.

## Main Menu

The `displayMainMenu()` function displays the main menu, which remains similar to the one used in Phase 2.

The menu includes the following operations:

1. Add a Book
2. Remove a Book
3. Search for a Book
4. Print Book List
5. Exit System

## Required Functions

### 1. `displayMainMenu()`

```c
void displayMainMenu();
```

Displays the main menu to the user. This function remains similar to its implementation in Phase 2.

### 2. `addBook()`

```c
void addBook(char names[][NAMESIZE], int bins[], double prices[], int *size);
```

This function receives the arrays containing book names, bin numbers, and prices. It also receives a pointer to an integer representing the current number of books in the list.

The function checks whether the list is full. If the list is not full (`size < MAXSIZE`), it searches for the correct position of the new book based on its bin number.

- If the bin number already exists, an error message is displayed.
- Otherwise, the function shifts the appropriate elements to the right and inserts the new book's name, bin number, and price into their corresponding arrays.

### 3. `removeBook()`

```c
void removeBook(char names[][NAMESIZE], int bins[], double prices[], int *size);
```

This function receives the arrays containing book names, bin numbers, and prices, along with a pointer to the current number of books.

The function checks whether the list is empty.

- If the list is empty, no book can be removed.
- If the list is not empty (`size > 0`), the function searches for the bin number to be removed.
- If the bin number does not exist, an error message is displayed.
- If the bin number exists, the function removes the book and shifts all following elements to the left in all three arrays.

### 4. `searchForBook()`

```c
void searchForBook(char names[][NAMESIZE], int bins[], double prices[], int size);
```

This function receives the arrays containing book names, bin numbers, and prices, along with the current number of books.

If the list is not empty, the function asks the user to enter a bin number and searches for that book.

- If the bin number is not found, an error message is displayed.
- If the bin number is found, the book's name, bin number, and price are displayed in a suitable format.

### 5. `uploadDataFile()`

```c
void uploadDataFile(char names[][NAMESIZE], int bins[], double prices[], int *size);
```

This function receives the arrays containing book names, bin numbers, and prices, along with a pointer to the current number of books.

It opens the file `books.txt` for reading and loads all book names, bin numbers, and prices into their corresponding arrays.

### 6. `updateDataFile()`

```c
void updateDataFile(char names[][NAMESIZE], int bins[], double prices[], int size);
```

This function receives the arrays containing book names, bin numbers, and prices, along with the current number of books.

It opens the file `books.txt` for writing and saves all book names, bin numbers, and prices stored in the arrays to the file.

### 7. `printBooks()`

```c
void printBooks(char names[][NAMESIZE], int bins[], double prices[], int size);
```

This function receives the arrays containing book names, bin numbers, and prices, along with the current number of books.

It prints the information currently stored in the arrays, including each book's name, bin number, and price, in a suitable format.

## Constants

The program must define the following constants:

```c
#define MAXSIZE 100
#define NAMESIZE 50
```

- `MAXSIZE`: The maximum number of books that can be stored.
- `NAMESIZE`: The maximum size of a book name.

## Book Name Requirements

A book name may contain only letters, numbers, and underscores (`_`).

- A book name must start with a letter.
- Book names must not contain spaces.
- No validation is required for these conditions; the program may assume that all book names follow these rules.

Examples of valid book names:

```text
Introduction_To_Geography
Computer_Fun
Introduction_To_Computers
Computer_Programming_Fun
Geography_1
```

## Important Requirements

### 1. Parallel Arrays

The project must use **parallel arrays** exactly as specified:

- `names[]` stores book names.
- `bins[]` stores book bin numbers.
- `prices[]` stores book prices.

**Structures (`struct`) must not be used anywhere in the project.**

### 2. Ascending Order

Book information must always be stored in ascending order according to the bin numbers in `bins[]`.

- Do not use sorting functions.
- In `addBook()`, shift elements to the right to insert a new book in the correct position.
- In `removeBook()`, shift elements to the left after removing a book.
- Ensure that the corresponding name and price remain associated with the correct bin number.

## Data File

The program uses a text file named `books.txt` to store book information.

Each record contains:

1. Book name
2. Bin number
3. Price

The program reads the records from the file when loading the book information and writes the updated records back to the file when saving changes.

## Sample Run

At the beginning of the program, the file `books.txt` contains the following information:

The first column represents the book name, the second column represents the bin number, and the third column represents the price.

```text
Introduction_To_Geography    1234    72.45
Computer_Fun                 2345    25.20
```
<img width="975" height="987" alt="image" src="https://github.com/user-attachments/assets/04553606-2a87-4831-b2f2-3a6cf76bb5e8" />
<img width="975" height="948" alt="image" src="https://github.com/user-attachments/assets/0c11b35a-54eb-4fb3-963d-34009d70918d" />
<img width="975" height="986" alt="image" src="https://github.com/user-attachments/assets/d95eaa39-0a9f-4d98-a87a-e3aed9230810" />


## Programming Language

C

## Submission Reminder
Make sure that your `main.c` file follows all the project requirements, uses parallel arrays, and maintains the books in ascending order by bin number.



