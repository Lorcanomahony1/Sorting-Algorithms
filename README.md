## **Introduction**

Sorting is the process of changing the order of integers in a list so they start with the lowest number and end with the biggest number,

for every number in the sorted list or array, the number to the right of it should be bigger than it

and the number to the left should be smaller than it.

The exception is when the number is the same value, in that case it could be to the right or left of it.

Sorting seems like a simple process but it can take lot of computational power to perform sorting algorithms when the number of values to sort is very high.

the difference in speed between different algorithms is very similar when sorting small lists or arrays

but as the array or list of integers that needs to be sorted grows, 

some algorithms are exponentially faster than others

- In place sorting algorithms

In place sorting algorithms sort the values by changing the order of values in the original array.

Many sorting algorithms create new arrays and move the sorted values into the new array

- Stable sorting algorithms

a stable sorting algorithm is when the order of duplicate values stays the same after the algorithm is finished sorting

- comparator functions

comparator functions are a component of sorting algorithms where two or more values are compared to each other in order to determine which order they should be in

for example

if value 2 > value 1

swap value 1 with value 2 

comparison based sorting algorithms are sorting algorithms that use comparator functions on each value in a list or array in order to compare the value against the surrounding values and determine how it should be ordered. 

an example of a comparison based sorting algorithm is merge sort 

non comparison based sorting algorithms

non comparison based algorithms don’t compare each value in an array to the surrounding values like comparison based sorting algorithms

instead, they order the values by creating separate arrays and putting the values into these other arrays

counting sort is an example of a non comparison based sorting algorithm

counting sort counts the number of duplicate values then moves them into another array and assigns it a number based on how many duplicates exist in the original dataset, and this number is put into the index of the number itself

then a new array is created 

and for each value in this new array the values in the previous array are placed in the array in the original order and they are placed one after another until the count reaches the number of duplicates

Relevance and importance of sorting algorithms

- Sorting algorithms are very important for situations where millions of values need to be sorted
    
    when the number of values that needs to be sorted is very high it can be very time consuming for a simple algorithm to sort
    
    so more advanced algorithms are necessary
    
    an example of one of these situations is the google search algorithm
    
    there are hundreds of millions of possible results for some search queries
    
    and optimal sorting algorithms are necessary for this. 
    

The speed of a sorting algorithm is measured using big 0 notation

big o notation describes the maximum time an algorithm could take

### Explanations of sorting algorithms

### Bubble Sort

Bubble sort goes through the list and compares each value to the value before it and if the value before it is lower then it swaps the values

it does this over and over again until the list is sorted

it is very time consuming because the algorithm has to go through the entire list many times 

Bubble sort has a big o notation of 0 (n^2)

 

Bubble sort example using student number

- First loop

00362689

00326689

- Second loop

00326689

00236689

![eg](https://github.com/user-attachments/assets/855931d8-bc16-46cd-af2b-e215de06af1d)


### **Selection Sort**

Selection sort works in the following way

1. a current minimum number is chosen, starting with the first number 
2. the algorithm goes from left to right until it finds a number smaller than the current minmum number
3. then it checks if that number is smaller than the value on the left, if it is smaller then it swaps with the one on the left
    
    it repeats this until the value on the right is bigger than the value on the left
    
4. It repeats this process over and over until the list is sorted

The complexity of selection sort is O(n^2)

- First loop

00362689

00263689

- Second loop

00236689

![j9oj](https://github.com/user-attachments/assets/a33316f0-2b6f-4273-968c-fdbc0162b4b7)

The first number is chosen, then the algorithm checks every number one by one after the first number and picks the smallest number in the list that is smaller than the first number

then it swaps the first number with the smallest number 

here the first number is zero

then the algorithm checks the rest of the numbers to the right of zero for a smaller one

there are none so it doesn’t swap

Then 3 is chosen, 

the algorithm checks every number to the right of 3 and it finds 2 

so 2 is swapped with 3

it does this for every number in the list

### Quick sort

Quick sort works by dividing the list into different parts and sorting them separately

The point at which the list is split is decided in the following way

the first value is chosen and the algorithm goes right through the list until it finds a value bigger than it, this can be called A

and on the opposite side of the list at the end

the algorithm moves left until it finds a value smaller than the first value in the list this can be called B

then both A and B are swapped and the process repeats until both A and B meet

The list is then split into two lists at this point

and each list is sorted separately using the same algorithm used to split the initial list 

the complexity of quick sort is O(n log n)

![mkm](https://github.com/user-attachments/assets/b95b0128-8def-4336-9037-690efcf20d1a)

### Initial:

00362689

#STEP 1 

9 is chosen as the pivot number 

0 is compared to 9, 0 is less than 9 so nothing happens

then next number is compared to 9, this number is also zero so the same outcome happens

then 3 is compared to 9, it is less than 9 so nothing happens

the same happens for all elements because 9 is the biggest element in the list

#STEP 2

8 is also the biggest number in the list so no changes happen in this loop

same thing with 6

#STEP 3

2 is compared to zero, and it is bigger than zero so no changes happen

2 is compared to 0 again, same outcome

2 is compared to 3 and it is smaller than 3 so 2 is replaced with 3

2 is compared with 6, it is smaller so it stays in place

### 00236689

This list is now sorted

### Bucket sort

This algorithm divides the list into smaller lists called buckets

then it iterates through each element in the list and puts it in its matching bucket

then runs a different sorting algorithm on each bucket   

or no sorting algorithm if there is a bucket for each unique element

bucket sort has a big o notation of O(n^2)


00362689

![iuhiub](https://github.com/user-attachments/assets/4292bb5a-bc56-4a21-be30-aabb0d2cb47f)



#STEP 1 

There are 6 uniqe numbers so 6 buckets are made

0 2 3 6 8 9 

#STEP 2

each number is chosen and it is compared to each bucket, 

if it is the correct number for the bucket, it goes into the bucket

this is done for each element

this is the end result

[Bucket-0] - 0,0

[Bucket-2] - 2

[Bucket-3] - 3 

[Bucket-6] 6, 6

[Bucket-8] 8 

[Bucket-9] 9 

#STEP 3 

All of the buckets are combined

00236689

### Results

The algorithms had similar times in the 100-500 range with bubble sort being the slowest

but the higher the number of elements in the list, the more pronounced the differences in speeds

at 10000 elements 

- bubble sort was by far the slowest
- quick sort was the fastest at 4 milliseconds and count sortwas the second fastest at 34 milliseconds

Quick sort was the fastest because it has a worst case scenario speed of O(n log(n)) complexity

bubble sort has a worst case speed of O(n2) complexity

count sort worst case speed = O(n +k)

insertion sort worst case speed = O(n2)

selection sort worst case speed = O(n2)

Implementation & Benchmarking (25%)

Benchmarking was done by creating a random list of 10,000 random integers

then making 100 different sublists from the original 10000 integer list

and running the algorithm on each sublist

then this sub list was added to the previous sublist 

ie 

first benchmark - (100/10,000)

second benchmark - (200/10,000)

second benchmark - (300/10,000)

…

This was repeated 100 times until the algorithms were run on the entire list

and each time the algorithms were run the time it took to sort the sublist was calculated and printed in milliseconds,

by simply starting a timer and ending it when the algorithm stops sorting



## References

> Udacity (2016) Quicksort – Udacity Technical Interview Prep [YouTube video], published 9 years ago. Available at: https://www.youtube.com/watch?v=kUon6854joI (Accessed: 20 June 2025).
> 

> Computerphile (2013) Quick Sort - Computerphile [YouTube video], 25 June. Available at: https://www.youtube.com/watch?v=XE4VP_8Y0BU (Accessed: 20 June 2025).
> 
- KC Ang. (2014) *Quicksort: Partitioning an array* . [Video]. Available from: http://www.youtube.com/watch?v=MZaf_9IZCrc
- "Bubble Sort Explained." *YouTube*, [googleusercontent.com/youtube.com/0](https://www.google.com/search?q=https://googleusercontent.com/youtube.com/0). Accessed 18 June 2025.
- LabEx (n.d.) Java: How to compile and run a Java application from the command line. [online] LabEx. Available at: https://labex.io/tutorials/java-how-to-compile-and-run-a-java-application-from-the-command-line-413959 [Accessed 7 Jun. 2025].
- Kartik. (2024). **Bucket Sort – Data Structures and Algorithms Tutorials**. GeeksforGeeks. Available at: https://www.geeksforgeeks.org/bucket-sort-2/ [Accessed May 16, 2025]
- Wikipedia. (n.d.). **Bubble sort**. Available at: https://en.wikipedia.org/wiki/Bubble_sort [Accessed May 16, 2025].
- Scott, T. (2020) *Why My Teenage Code Was Terrible: Sorting Algorithms and Big O Notation*. Available at: http://www.youtube.com/watch?v=RGuJga2Gl_k (Accessed: 16 May 2025).
- **Sambol, M.** (**Jul 20, 2016**) *Selection sort in 3 minutes*. [YouTube video] Available at: https://www.youtube.com/watch?v=g-PGLbMth_g (Accessed: 16 May 2025).
- **Programming hub.** (2025) *Sorting algorithms: Why they matter (and when to skip them)*. Medium, 26 February. Available at: https://medium.com/writers-ocean/sorting-algorithms-why-they-matter-and-when-to-skip-them-112df5a0e883 (Accessed: 16 May 2025).
- Thomas, M., May 30, 2024. *Non-Comparison Sort Algorithms for Dummies*. [online] Medium. Available at: https://medium.com/marktech/non-comparison-sort-algorithms-for-dummies-af1be5351a4d [Accessed 16 May 2025].
- Thomas, M. May 30, 2024. *Comparison Sort Algorithms for Dummies*. [online] Medium. Available at: https://medium.com/marktech/comparison-sort-algorithms-for-dummies-e621cbff2c3f [Accessed 16 May 2025].
- Thakrani, S., Jul 21, 2023 *What are stable sorting algorithms and in-place sorting algorithms?* [online] Medium. Available at: https://medium.com/@suhailthakrani12/what-are-stable-sorting-algorithms-and-in-place-sorting-algorithms-672820a8e36c [Accessed 16 May 2025]
- **Kuvina Saydaki** (2023) *Explaining EVERY Sorting Algorithm (part 1)*. Available at: https://www.youtube.com/watch?v=AAwYzYkjNTg (Accessed: 16 May 2025).











