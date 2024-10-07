# Pseudocode: Sorting a Pile of Books in Alphabetical Order

## Problem Description

You have a pile of books that need to be sorted in alphabetical order based on the book titles. You do not know how many books there are, but this method will work for any number of books.

## Assumptions

- Each book has a title, and we will sort the books based on their titles.
- The titles are compared alphabetically (case-insensitive).

## Pseudocode

1. **Start**

   - Let `books` be the list of book titles that you need to sort.

2. **Check if sorting is needed**

   - If `books` is empty or contains only one book, the list is already sorted. Return the list as-is.

3. **Sorting process**

   - Use Selection Sort algorithm to sort the books.
   - For each position `i` in the list from 0 to `n-1` (where `n` is the number of books):
     1. Find the book with the smallest title from positions `i` to `n-1`.
        - Set `smallest` to `i` (assume the smallest book is at position `i` for now).
        - For each position `j` from `i+1` to `n-1`:
          - **How to determine the smaller title**:
            - Convert both `books[j]` and `books[smallest]` to lowercase for comparison.
            - Compare the titles letter by letter, starting from the first letter:
              - If the first letter of `books[j]` comes before the first letter of `books[smallest]` in the alphabet, `books[j]` is smaller.
              - If both letters are the same, compare the next letters in sequence until a difference is found.
              - If one title is a prefix of the other (e.g., "Cat" and "Catherine"), the shorter title is considered smaller.
            - If `books[j]` is smaller than `books[smallest]`, set `smallest` to `j`.
     2. Swap the smallest book with the book at position `i`.

4. **Return the sorted list**

   - Once all books are in alphabetical order, return the list of sorted books.

5. **End**
