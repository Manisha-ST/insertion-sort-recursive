# insertion-sort-recursive

from __future__ import annotations

def rec_insertion_sort(collection: list, n: int):
    # Base condition
    if n <= 1:
        return

    # Sort first n-1 elements
    rec_insertion_sort(collection, n - 1)

    # Insert nth element at correct position
    insert_next(collection, n - 1)


def insert_next(collection: list, index: int):
    if index <= 0 or collection[index - 1] <= collection[index]:
        return

    # Swap if elements are in wrong order
    collection[index - 1], collection[index] = collection[index], collection[index - 1]
    insert_next(collection, index - 1)


# Test cases
nums = [4, 3, 5, 1, 2]
print("\nOriginal list:")
print(nums)
rec_insertion_sort(nums, len(nums))
print("After Recursive Insertion Sort:")
print(nums)

nums = [5, 9, 10, 3, -4, 5, 178, 92, 46, -18, 0, 7]
print("\nOriginal list:")
print(nums)
rec_insertion_sort(nums, len(nums))
print("After Recursive Insertion Sort:")
print(nums)

nums = [1.1, 1, 0, -1, -1.1, 0.1]
print("\nOriginal list:")
print(nums)
rec_insertion_sort(nums, len(nums))
print("After Recursive Insertion Sort:")
print(nums)

Output:
Original list:
[4, 3, 5, 1, 2]
After Recursive Insertion Sort:
[1, 2, 3, 4, 5]

Original list:
[5, 9, 10, 3, -4, 5, 178, 92, 46, -18, 0, 7]
After Recursive Insertion Sort:
[-18, -4, 0, 3, 5, 5, 7, 9, 10, 46, 92, 178]

Original list:
[1.1, 1, 0, -1, -1.1, 0.1]
After Recursive Insertion Sort:
[-1.1, -1, 0, 0.1, 1, 1.1]
