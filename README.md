# Sorting Algorithms Overview

## Introduction

Sorting is the process of changing the order of integers in a list so they start with the lowest number and end with the biggest number. For every number in the sorted list or array, the number to the right of it should be bigger than it, and the number to the left should be smaller than it. The exception is when the number is the same value, in which case it could be to the right or left of it.

Sorting seems like a simple process, but it can take a lot of computational power to perform sorting algorithms when the number of values to sort is very high. The difference in speed between different algorithms is very similar when sorting small lists or arrays, but as the array or list of integers that needs to be sorted grows, some algorithms are exponentially faster than others.

### Key Concepts

- **In-Place Sorting Algorithms**  
  In-place sorting algorithms sort the values by changing the order of values in the original array. Many sorting algorithms create new arrays and move the sorted values into the new array.

- **Stable Sorting Algorithms**  
  A stable sorting algorithm is when the order of duplicate values stays the same after the algorithm is finished sorting.

- **Comparator Functions**  
  Comparator functions are a component of sorting algorithms where two or more values are compared to each other to determine which order they should be in. For example:  
  ```plaintext
  if value 2 > value 1
      swap value 1 with value 2
  ```

- **Comparison-Based Sorting Algorithms**  
  Comparison-based sorting algorithms use comparator functions on each value in a list or array to compare the value against the surrounding values and determine how it should be ordered. An example is **merge sort**.

- **Non-Comparison-Based Sorting Algorithms**  
  Non-comparison-based algorithms don’t compare each value in an array to the surrounding values like comparison-based sorting algorithms. Instead, they order the values by creating separate arrays and putting the values into these other arrays. **Counting sort** is an example of a non-comparison-based sorting algorithm. Counting sort counts the number of duplicate values, then moves them into another array and assigns it a number based on how many duplicates exist in the original dataset. This number is put into the index of the number itself. Then a new array is created, and for each value in this new array, the values in the previous array are placed in the array in the original order and they are placed one after another until the count reaches the number of duplicates.

### Relevance and Importance of Sorting Algorithms

Sorting algorithms are very important for situations where millions of values need to be sorted. When the number of values that needs to be sorted is very high, it can be very time-consuming for a simple algorithm to sort, so more advanced algorithms are necessary. An example of one of these situations is the Google search algorithm. There are hundreds of millions of possible results for some search queries, and optimal sorting algorithms are necessary for this.

The speed of a sorting algorithm is measured using **Big O notation**, which describes the maximum time an algorithm could take.

## Explanations of Sorting Algorithms

### Bubble Sort

Bubble sort goes through the list and compares each value to the value before it. If the value before it is lower, then it swaps the values. It does this over and over again until the list is sorted. It is very time-consuming because the algorithm has to go through the entire list many times. Bubble sort has a Big O notation of **O(n²)**.

**Bubble Sort Example Using Student Number**  
- **First Loop**  
  ```plaintext
  00362689
  00326689
  ```
- **Second Loop**  
  ```plaintext
  00326689
  00236689
  ```

![Bubble Sort](https://github.com/user-attachments/assets/855931d8-bc16-46cd-af2b-e215de06af1d)

### Selection Sort

Selection sort works in the following way:
1. A current minimum number is chosen, starting with the first number.
2. The algorithm goes from left to right until it finds a number smaller than the current minimum number.
3. It checks if that number is smaller than the value on the left. If it is smaller, it swaps with the one on the left. It repeats this until the value on the right is bigger than the value on the left.
4. It repeats this process over and over until the list is sorted.

The complexity of selection sort is **O(n²)**.

**Selection Sort Example**  
- **First Loop**  
  ```plaintext
  00362689
  00263689
  ```
- **Second Loop**  
  ```plaintext
  00236689
  ```

The first number is chosen, then the algorithm checks every number one by one after the first number and picks the smallest number in the list that is smaller than the first number. Then it swaps the first number with the smallest number. Here, the first number is zero. The algorithm checks the rest of the numbers to the right of zero for a smaller one. There are none, so it doesn’t swap. Then 3 is chosen, the algorithm checks every number to the right of 3 and it finds 2, so 2 is swapped with 3. It does this for every number in the list.

![Selection Sort](https://github.com/user-attachments/assets/a33316f0-2b6f-4273-968c-fdbc0162b4b7)

### Quick Sort

Quick sort works by dividing the list into different parts and sorting them separately. The point at which the list is split is decided in the following way:
- The first value is chosen, and the algorithm goes right through the list until it finds a value bigger than it (this can be called A).
- On the opposite side of the list at the end, the algorithm moves left until it finds a value smaller than the first value in the list (this can be called B).
- Then both A and B are swapped, and the process repeats until both A and B meet.
- The list is then split into two lists at this point, and each list is sorted separately using the same algorithm used to split the initial list.

The complexity of quick sort is **O(n log n)**.

**Quick Sort Example**  
**Initial**:  
```plaintext
00362689
```

**STEP 1**  
9 is chosen as the pivot number. 0 is compared to 9, 0 is less than 9, so nothing happens. Then the next number is compared to 9; this number is also zero, so the same outcome happens. Then 3 is compared to 9; it is less than 9, so nothing happens. The same happens for all elements because 9 is the biggest element in the list.

**STEP 2**  
8 is also the biggest number in the list, so no changes happen in this loop. The same thing happens with 6.

**STEP 3**  
2 is compared to zero, and it is bigger than zero, so no changes happen. 2 is compared to 0 again, same outcome. 2 is compared to 3, and it is smaller than 3, so 2 is replaced with 3. 2 is compared with 6; it is smaller, so it stays in place.

**Result**:  
```plaintext
00236689
```

This list is now sorted.

![Quick Sort](https://github.com/user-attachments/assets/b95b0128-8def-4336-9037-690efcf20d1a)

### Bucket Sort

This algorithm divides the list into smaller lists called buckets, then iterates through each element in the list and puts it in its matching bucket. It then runs a different sorting algorithm on each bucket or no sorting algorithm if there is a bucket for each unique element. Bucket sort has a Big O notation of **O(n²)**.

**Bucket Sort Example**  
```plaintext
00362689
```

**STEP 1**  
There are 6 unique numbers, so 6 buckets are made:  
```plaintext
0 2 3 6 8 9
```

**STEP 2**  
Each number is chosen and compared to each bucket. If it is the correct number for the bucket, it goes into the bucket. This is done for each element. This is the end result:  
```plaintext
[Bucket-0] - 0,0
[Bucket-2] - 2
[Bucket-3] - 3
[Bucket-6] - 6,6
[Bucket-8] - 8
[Bucket-9] - 9
```

**STEP 3**  
All of the buckets are combined:  
```plaintext
00236689
```

![Bucket Sort](https://github.com/user-attachments/assets/4292bb5a-bc56-4a21-be30-aabb0d2cb47f)

## Results

The algorithms had similar times in the 100-500 range, with bubble sort being the slowest. However, the higher the number of elements in the list, the more pronounced the differences in speeds. At 10,000 elements:
- Bubble sort was by far the slowest.
- Quick sort was the fastest at **4 milliseconds**, and count sort was the second fastest at **34 milliseconds**.

Quick sort was the fastest because it has a worst-case scenario speed of **O(n log n)** complexity.  
- Bubble sort has a worst-case speed of **O(n²)** complexity.
- Count sort worst-case speed = **O(n + k)**.
- Insertion sort worst-case speed = **O(n²)**.
- Selection sort worst-case speed = **O(n²)**.

### Implementation & Benchmarking (25%)

Benchmarking was done by creating a random list of **10,000 random integers**, then making 100 different sublists from the original 10,000 integer list and running the algorithm on each sublist. Then this sublist was added to the previous sublist, i.e.:
- First benchmark: (100/10,000)
- Second benchmark: (200/10,000)
- Third benchmark: (300/10,000)
- ...

This was repeated 100 times until the algorithms were run on the entire list. Each time the algorithms were run, the time it took to sort the sublist was calculated and printed in milliseconds by simply starting a timer and ending it when the algorithm stops sorting.

## References

- Udacity (2016) *Quicksort – Udacity Technical Interview Prep* [YouTube video]. Available at: [https://www.youtube.com/watch?v=kUon6854joI](https://www.youtube.com/watch?v=kUon6854joI) (Accessed: 20 June 2025).
- Computerphile (2013) *Quick Sort - Computerphile* [YouTube video], 25 June. Available at: [https://www.youtube.com/watch?v=XE4VP_8Y0BU](https://www.youtube.com/watch?v=XE4VP_8Y0BU) (Accessed: 20 June 2025).
- KC Ang. (2014) *Quicksort: Partitioning an array* [Video]. Available at: [http://www.youtube.com/watch?v=MZaf_9IZCrc](http://www.youtube.com/watch?v=MZaf_9IZCrc) (Accessed: 18 June 2025).
- "Bubble Sort Explained." *YouTube*, Available at: [https://www.google.com/search?q=https://googleusercontent.com/youtube.com/0](https://www.google.com/search?q=https://googleusercontent.com/youtube.com/0) (Accessed: 18 June 2025).
- LabEx (n.d.) *Java: How to compile and run a Java application from the command line*. [online] LabEx. Available at: [https://labex.io/tutorials/java-how-to-compile-and-run-a-java-application-from-the-command-line-413959](https://labex.io/tutorials/java-how-to-compile-and-run-a-java-application-from-the-command-line-413959) (Accessed: 7 Jun. 2025).
- Kartik. (2024). *Bucket Sort – Data Structures and Algorithms Tutorials*. GeeksforGeeks. Available at: [https://www.geeksforgeeks.org/bucket-sort-2/](https://www.geeksforgeeks.org/bucket-sort-2/) (Accessed: 16 May 2025).
- Wikipedia. (n.d.). *Bubble sort*. Available at: [https://en.wikipedia.org/wiki/Bubble_sort](https://en.wikipedia.org/wiki/Bubble_sort) (Accessed: 16 May 2025).
- Scott, T. (2020) *Why My Teenage Code Was Terrible: Sorting Algorithms and Big O Notation*. Available at: [http://www.youtube.com/watch?v=RGuJga2Gl_k](http://www.youtube.com/watch?v=RGuJga2Gl_k) (Accessed: 16 May 2025).
- Sambol, M. (Jul 20, 2016) *Selection sort in 3 minutes*. [YouTube video] Available at: [https://www.youtube.com/watch?v=g-PGLbMth_g](https://www.youtube.com/watch?v=g-PGLbMth_g) (Accessed: 16 May 2025).
- Programming hub. (2025) *Sorting algorithms: Why they matter (and when to skip them)*. Medium, 26 February. Available at: [https://medium.com/writers-ocean/sorting-algorithms-why-they-matter-and-when-to-skip-them-112df5a0e883](https://medium.com/writers-ocean/sorting-algorithms-why-they-matter-and-when-to-skip-them-112df5a0e883) (Accessed: 16 May 2025).
- Thomas, M., May 30, 2024. *Non-Comparison Sort Algorithms for Dummies*. [online] Medium. Available at: [https://medium.com/marktech/non-comparison-sort-algorithms-for-dummies-af1be5351a4d](https://medium.com/marktech/non-comparison-sort-algorithms-for-dummies-af1be5351a4d) (Accessed: 16 May 2025).
- Thomas, M., May 30, 2024. *Comparison Sort Algorithms for Dummies*. [online] Medium. Available at: [https://medium.com/marktech/comparison-sort-algorithms-for-dummies-e621cbff2c3f](https://medium.com/marktech/comparison-sort-algorithms-for-dummies-e621cbff2c3f) (Accessed: 16 May 2025).
- Thakrani, S., Jul 21, 2023 *What are stable sorting algorithms and in-place sorting algorithms?* [online] Medium. Available at: [https://medium.com/@suhailthakrani12/what-are-stable-sorting-algorithms-and-in-place-sorting-algorithms-672820a8e36c](https://medium.com/@suhailthakrani12/what-are-stable-sorting-algorithms-and-in-place-sorting-algorithms-672820a8e36c) (Accessed: 16 May 2025).
- Kuvina Saydaki (2023) *Explaining EVERY Sorting Algorithm (part 1)*. Available at: [https://www.youtube.com/watch?v=AAwYzYkjNTg](https://www.youtube.com/watch?v=AAwYzYkjNTg) (Accessed: 16 May 2025).








