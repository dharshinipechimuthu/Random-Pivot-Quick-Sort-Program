# Random-Pivot-Quick-Sort-Program
import random

def partition(A, left, right):
    pivot = A[left]
    i = left + 1

    for j in range(left + 1, right):
        if A[j] < pivot:
            A[j], A[i] = A[i], A[j]
            i += 1

    A[left], A[i - 1] = A[i - 1], A[left]
    return i - 1


def quick_sort_random(A, left, right):
    if left < right:
        pivot = random.randint(left, right - 1)
        A[left], A[pivot] = A[pivot], A[left]
        p = partition(A, left, right)
        quick_sort_random(A, left, p)
        quick_sort_random(A, p + 1, right)


nums = [4, 3, 5, 1, 2]
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 0, len(nums))
print("After applying Random Pivot Quick Sort the said list becomes:")
print(nums)

nums = [5, 9, 10, 3, -4, 5, 178, 92, 46, -18, 0, 7]
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 0, len(nums))
print("After applying Random Pivot Quick Sort the said list becomes:")
print(nums)

nums = [1.1, 1, 0, -1, -1.1, 0.1]
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 0, len(nums))
print("After applying Random Pivot Quick Sort the said list becomes:")
print(nums)

nums = ['z', 'a', 'y', 'b', 'x', 'c']
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 0, len(nums))
print("After applying Random Pivot Quick Sort the said list becomes:")
print(nums)

Output:
Original list:
[4, 3, 5, 1, 2]
After applying Random Pivot Quick Sort the said list becomes:
[1, 2, 3, 4, 5]

Original list:
[5, 9, 10, 3, -4, 5, 178, 92, 46, -18, 0, 7]
After applying Random Pivot Quick Sort the said list becomes:
[-18, -4, 0, 3, 5, 5, 7, 9, 10, 46, 92, 178]

Original list:
[1.1, 1, 0, -1, -1.1, 0.1]
After applying Random Pivot Quick Sort the said list becomes:
[-1.1, -1, 0, 0.1, 1, 1.1]

Original list:
['z', 'a', 'y', 'b', 'x', 'c']
After applying Random Pivot Quick Sort the said list becomes:
['a', 'b', 'c', 'x', 'y', 'z']
