Counting sort and radix sort are two non-comparison-based sorting algorithms that achieve better performance than comparison-based sorting algorithms for certain types
of input data.

### Counting Sort
Counting sort is a linear time complexity sorting algorithm that works by counting the number of occurrences of each distinct element in the input array and using this
information to determine the position of each element in the output array. It can only be used to sort a collection of non-negative integers, and its time complexity
is O(n + k), where n is the number of elements in the input array and k is the range of values that the input array can take.

Here is an example of how counting sort works:

Suppose we have an input array arr = [3, 1, 6, 2, 5, 2], and we want to sort it using counting sort.

- Find the range of values in the input array: min = 1 and max = 6.
- Create a count array count with size max - min + 1 and initialize all elements to 0.
- Count the occurrences of each distinct element in the input array by incrementing the corresponding count array element. In this example, the count array becomes
[1, 2, 0, 1, 0, 1].
- Modify the count array to hold the position of each element in the output array. In this example, the count array becomes [0, 1, 3, 3, 4, 4],
which means that the first occurrence of 1 goes in position 0, the two occurrences of 2 go in positions 1 and 2, the one occurrence of 3 goes in position 3, 
the one occurrence of 5 goes in position 4, and the one occurrence of 6 goes in position 5.
- Create an output array out with the same size as the input array.
- Traverse the input array from left to right, and for each element arr[i], find its position in the output array by looking up the count array: 
out[count[arr[i] - min]] = arr[i] and count[arr[i] - min]++.
- The output array out is the sorted version of the input array arr. In this example, the output array is [1, 2, 2, 3, 5, 6].

### Radix Sort

Radix sort is another linear time complexity sorting algorithm that works by sorting elements based on their digits or bits. 
It can be used to sort integers or strings, and its time complexity is O(d*(n+k)), where d is the maximum number of digits or bits,
n is the number of elements in the input array, and k is the range of values that each digit or bit can take.

Here is an example of how radix sort works:

Suppose we have an input array arr = [170, 45, 75, 90, 802, 24, 2, 66], and we want to sort it using radix sort.

- Find the maximum number of digits in the input array: max_digits = 3.
- For each digit position i (from least significant to most significant), sort the elements based on that digit using a stable sort algorithm,
such as counting sort. In this example, we use counting sort to sort the elements based on the ones digit, then the tens digit, and finally the hundreds digit.
- Sort based on the ones digit: [170, 90, 802, 2, 24, 45, 75, 66]
- Sort based on the tens digit: [802, 2, 24, 45, 66, 170, 75, 90]
- Sort based on the hundreds digit: [2, 24, 45, 66, 75, 90, 170, 802]
- After each sort operation, the input array becomes the sorted array, and we move on to the next digit position.
- The output array is the final sorted version of the input array. In this example, the output array is [2, 24, 45, 66, 75, 90, 170, 802].
In this example, we sorted the input array by sorting the elements based on each digit from least significant to most significant. 
Radix sort works because it exploits the fact that if a number a is less than a number b in some digit position,
then a is also less than b in all lower digit positions. Therefore, by sorting based on each digit position,
we can ensure that the elements are sorted correctly in the end. 
Radix sort can achieve linear time complexity for certain types of input data, such as integers with a limited range of digits.
