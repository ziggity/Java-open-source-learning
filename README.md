

 # Java open source 

*This is an open source knowledge share on all things Java CS related*

## Algorithms

## Time Complexity

## Arrays
*The following example is how to create an array and fill it with numbers using Java.

int[] myArray = new int[20];  //Creates an array of size 20 to store integers
String[] myArray = new String[20];  //Creates an array of size 20 to store String and type this out in your code 	System.out.println(myArray.length); which will result in 20


for(int i = 0; i < myArray.length; i++) { 

    myArray[i] = i;

}
//myArray.length = 20, i = 0, loop until i > 19
//On each iteration, myArray at index i will contain the current value of i
//When this loop finishes, myArray will contain 0,1,2,3,4,5,6,7,8,9... 19 in that order
Arrays are the simplest data structure you will be dealing with, but they are incredibly useful and have a huge amount of applications. Many complex data structures use arrays in some way. For example, you can represent a graph structure as a matrix, or two dimensional array, of connected edges. You can efficiently sort data without using any extra memory using a heap structure, which at its most basic form is just an array that can be sorted in place. Once you grasp arrays, you will be able to grasp the more complex structures much more easily.*

## Sorting
*There are many algorithms/ways to sort an array. Among them the most commonly used are

Bubble Sort(code is below)
Heap Sort
Merge Sort
Bucket Sort
Insertion Sort(code is below)
Selection Sort(code is below)
Before going into a discussion on these type of sorting, we must learn the basics of arranging elements in one order(ASC or DSC).

import java.util.Arrays;
import java.util.Collections;
import java.util.List;
public class Demon implements Cloneable {
	public static void main(String[] args) {
		//First way using sorting algorithm
		Integer a[]={11,2,2,33,33,4,5,6,0,9};
		for(int i=0;i<a.length;i++)
			for(int j=0;j<a.length;j++){
				if(a[i]<a[j]){
					a[i]=a[i]+a[j];
					a[j]=a[i]-a[j];
					a[i]=a[i]-a[j];
					
				}
			}
		System.out.println("First way using sorting algorithm");
		System.out.println("maximum element is "+a[a.length-1]);
		System.out.println("minimum element is "+a[0]);
		
		//Second way.....
		System.out.println("Second way using Arrays.sort()...");
		Integer b[]={11,2,2,33,33,4,5,6,0,9};
		Arrays.sort(b);
		System.out.println("maximum element is "+b[b.length-1]);
		System.out.println("minimum element is "+b[0]);
		
		//Third way.......
		System.out.println("Third way using Collections.sort()...");
		Integer c[]={11,2,2,33,33,4,5,6,0,9};
		List<Integer> list = Arrays.asList(c);
		Collections.sort(list);
		c = (Integer[]) list.toArray();
		System.out.println("maximum element is "+c[c.length-1]);
		System.out.println("minimum element is "+c[0]);
	
	}
} 
Selection Sort:


In the above example, it has an array [ 4,2,5,1,3] which need to be sorted in ascending order [1,2,3,4,5] using selection sort.

import java.util.Arrays;
public class Demo {
	public static void main(String[] args) {
		int a[] = { 4, 2, 5, 1, 3, 0 };
		System.out.println("Array before sorting " + Arrays.toString(a));
		a = selectionSortAlg(a, a.length);
		System.out.println("Array after sorting " + Arrays.toString(a));
	}
	private static int[] selectionSortAlg(int[] a, int n) {
		for (int i = 0; i < n - 1; i++) {
			int iMin = i;
			for (int j = i + 1; j < n; j++) {
				if (a[j] < a[iMin]) {
					iMin = j; // index of smallest element
				}
			}
			int temp = a[i];
			a[i] = a[iMin];
			a[iMin] = temp;
			System.out.println("Pass..." + i + "..." + Arrays.toString(a));
		}
		return a;
	}
}
ouput

Array before sorting [4, 2, 5, 1, 3, 0]
Pass...0...[0, 2, 5, 1, 3, 4]
Pass...1...[0, 1, 5, 2, 3, 4]
Pass...2...[0, 1, 2, 5, 3, 4]
Pass...3...[0, 1, 2, 3, 5, 4]
Pass...4...[0, 1, 2, 3, 4, 5]
Array after sorting [0, 1, 2, 3, 4, 5]
….

Bubble Sort


workflow

Before sorting...[7, 2, 4, 1, 5, 3]
[2, 4, 1, 5, 3, 7]
[2, 1, 4, 3, 5, 7]
[1, 2, 3, 4, 5, 7]
[1, 2, 3, 4, 5, 7]
[1, 2, 3, 4, 5, 7]
Before sorting...[1, 2, 3, 4, 5, 7]
code: This is a simplest and easiest algorithm, which I love very much

public int[] bubbleSort(int n, int... a) {
		for (int j = 0; j < n - 1; j++){
			for (int i = 0; i < n - 1; i++) {
				if (a[i] > a[i + 1]) {
					int temp = a[i];
					a[i] = a[i + 1];
					a[i + 1] = temp;
				}
			}
			System.out.println(Arrays.toString(a));
		}
		return a;
	}
Insertion Sort:


code

import java.util.Arrays;
public class Demo {
	public static void main(String[] args) {
		int a[] = {7,2,4,1,5,3}; //{ 4, 2, 5, 1, 3, 0 };
		System.out.println("Array before sorting " + Arrays.toString(a));
		a = insertionSortAlg(a, a.length);
		System.out.println("Array after sorting " + Arrays.toString(a));
	}
	private static int[] insertionSortAlg(int[] a, int n) {
		for (int i = 1; i < n ; i++) {
			for (int j = i; j > 0 && j <= i; j--) {
				if (a[j - 1] > a[j]) {
					int temp = a[j - 1];
					a[j - 1] = a[j];
					a[j] = temp;
				}
			}
			System.out.println("pass "+i+"..."+Arrays.toString(a));
		}
		return a;
	}
output:

Array before sorting [7, 2, 4, 1, 5, 3]
pass 1...[2, 7, 4, 1, 5, 3]
pass 2...[2, 4, 7, 1, 5, 3]
pass 3...[1, 2, 4, 7, 5, 3]
pass 4...[1, 2, 4, 5, 7, 3]
pass 5...[1, 2, 3, 4, 5, 7]
Array after sorting [1, 2, 3, 4, 5, 7]
Merge Sort:

Quick Sort

Sorting algorithms in java - Java2Blog
Sorting Algorithms - YouTube

Conclusion:
1)Insertion Sort(Next element is compared with previous element).

Array before sorting [7, 2, 4, 1, 5, 3]
pass 1...[2, 7, 4, 1, 5, 3]
pass 2...[2, 4, 7, 1, 5, 3]
pass 3...[1, 2, 4, 7, 5, 3]
pass 4...[1, 2, 4, 5, 7, 3]
pass 5...[1, 2, 3, 4, 5, 7]
Array after sorting [1, 2, 3, 4, 5, 7]
2)Selection Sort(the First element is replaced with the lowest element in an array).

Array before sorting [4, 2, 5, 1, 3, 0]
Pass...0...[0, 2, 5, 1, 3, 4]
Pass...1...[0, 1, 5, 2, 3, 4]
Pass...2...[0, 1, 2, 5, 3, 4]
Pass...3...[0, 1, 2, 3, 5, 4]
Pass...4...[0, 1, 2, 3, 4, 5]
Array after sorting [0, 1, 2, 3, 4, 5]
3)Bubble Sort(First element is compared with adjacent if not in order, then swap it)

Before sorting...[7, 2, 4, 1, 5, 3]
[2, 4, 1, 5, 3, 7]
[2, 1, 4, 3, 5, 7]
[1, 2, 3, 4, 5, 7]
[1, 2, 3, 4, 5, 7]
[1, 2, 3, 4, 5, 7]
Before sorting...[1, 2, 3, 4, 5, 7]

java.util.Arrays class has a overloaded static sort method. This can be used to sort an array of primitives or objects. There is also a parallelSort method.

Sorting an array of primitives

int [] intArr = {10, 4, 45, 6, -11, 9870, 99};
Arrays.sort(intArr);
System.out.println(Arrays.toString(intArr));
The output: [-11, 4, 6, 10, 45, 99, 9870]

Note the sorting order is ascending, by default.

All primitives (byte, int, float, char, etc.) and Java objects which implement java.lang.Comparable (String, Date, File, LocalDate, Integer, etc.) can use this version of the method. An example:


What are different ways to sort an array? (irrespective of platform)
What are different ways to ‘X’ sort in java? (Where X maybe insertion sort, selection, bubble sort…..)
The answer for Q.1

Insertion Sort
Quick Sort
Merge Sort
Heap Sort
Shell Sort
Bubble sort.
The answer for Q.2

I will take Bubble sort to explain this

1.

void swap(int *xp, int *yp)

{

 int temp = *xp;

 *xp = *yp;

 *yp = temp;

}

void bubbleSort(int arr[], int n)

{

 int i, j;

 for (i = 0; i < n-1; i++)  

 for (j = 0; j < n-i-1; j++) 

 if (arr[j] > arr[j+1])

 swap(&arr[j], &arr[j+1]);

}
*

## Searching
*Linear Search
Binary Search
Knuth Morris Pratt Pattern Search
Jump Search
Interpolation Search
Exponential Search
Fibonacci Search
Java Collections API
Linear Search
Linear or Sequential Search is the simplest of search algorithms. While it most certainly is the simplest, it's most definitely not the most common, due to its inefficiency. It's a brute-force algorithm. Very rarely is it used in production, and in most cases, it's outperformed by other algorithms.

Linear Search has no pre-requisites for the state of the underlying data structure.

Explanation
Linear Search involves sequential searching for an element in the given data structure until either the element is found or the end of the structure is reached.

If the element is found, we usually just return its position in the data structure. If not, we usually return -1.

Implementation
Now let's see how to implement Linear Search in Java:

public static int linearSearch(int arr[], int elementToSearch) {

    for (int index = 0; index < arr.length; index++) {
        if (arr[index] == elementToSearch)
            return index;
    }
    return -1;
}
To test it, we'll use a simple Array of integers:

int index = linearSearch(new int[]{89, 57, 91, 47, 95, 3, 27, 22, 67, 99}, 67);
print(67, index);
With a simple helper method to print the result:

public static void print(int elementToSearch, int index) {
    if (index == -1){
        System.out.println(elementToSearch + " not found.");
    }
    else {
        System.out.println(elementToSearch + " found at index: " + index);
    }
}
Output:

67 found at index: 8
Time Complexity
Here we are iterating through the entire set of N elements sequentially to get the location of the element being searched. The worst case for this algorithm will be if the element we are searching for is the last element in the array.

In this case, we will iterate N times before we find the element.

Hence, the Time Complexity of Linear search is O(N).

Space Complexity
This type of search requires only a single unit of memory to store the element being searched. This is not relevant to the size of the input Array.

Hence, the Space Complexity of Linear Search is O(1).

Applications
Linear Search can be used for searching in a small and unsorted set of data which is guaranteed not to increase in size by much.

It is a very basic search algorithm but due to its linear increase in time complexity, it does not find application in many production systems.

Binary Search
Binary or Logarithmic Search is one of the most commonly used search algorithms primarily due to its quick search time.

Explanation
This kind of search uses the Divide and Conquer methodology and requires the data set to be sorted beforehand.

It divides the input collection into equal halves, and with each iteration compares the goal element with the element in the middle.

If the element is found, the search ends. Else, we continue looking for the element by dividing and selecting the appropriate partition of the array, based on if the goal element is smaller or bigger than the middle element.

This is why it's important to have a sorted collection for Binary Search.

The search terminates when the firstIndex (our pointer) goes past lastIndex (last element), which implies we have searched the whole array and the element is not present.

There are two ways to implement this algorithm - iterative and recursive.

There shouldn't be a difference regarding time and space complexity between these two implementations, though this doesn't hold true to all languages.

Implementation
Iterative
Let's first take a look at the iterative approach:

public static int binarySearch(int arr[], int elementToSearch) {

    int firstIndex = 0;
    int lastIndex = arr.length - 1;

    // termination condition (element isn't present)
    while(firstIndex <= lastIndex) {
        int middleIndex = (firstIndex + lastIndex) / 2;
        // if the middle element is our goal element, return its index
        if (arr[middleIndex] == elementToSearch) {
            return middleIndex;
        }

        // if the middle element is smaller
        // point our index to the middle+1, taking the first half out of consideration
        else if (arr[middleIndex] < elementToSearch)
            firstIndex = middleIndex + 1;

        // if the middle element is bigger
        // point our index to the middle-1, taking the second half out of consideration
        else if (arr[middleIndex] > elementToSearch)
            lastIndex = middleIndex - 1;

    }
    return -1;
}
We can use the algorithm like this:

int index = binarySearch(new int[]{89, 57, 91, 47, 95, 3, 27, 22, 67, 99}, 67);
print(67, index);
Output:

67 found at index: 5
Recursive
And now let's take a look at the recursive implementation:

public static int recursiveBinarySearch(int arr[], int firstElement, int lastElement, int elementToSearch) {

    // termination condition
    if (lastElement >= firstElement) {
        int mid = firstElement + (lastElement - firstElement) / 2;

        // if the middle element is our goal element, return its index
        if (arr[mid] == elementToSearch)
            return mid;

        // if the middle element is bigger than the goal element
        // recursively call the method with narrowed data
        if (arr[mid] > elementToSearch)
            return recursiveBinarySearch(arr, firstElement, mid - 1, elementToSearch);

        // else, recursively call the method with narrowed data
        return recursiveBinarySearch(arr, mid + 1, lastElement, elementToSearch);
    }

    return -1;
}
The difference in the recursive approach is that we invoke the method itself once we get the new partition. In the iterative approach, whenever we determined the new partition we modified the first and last elements and repeated the process in the same loop.

Another difference here is that recursive calls are pushed on the method call-stack and they occupy one unit of space per recursive call.

We can use this algorithm like this:

int index = binarySearch(new int[]{3, 22, 27, 47, 57, 67, 89, 91, 95, 99}, 0, 10, 67);
print(67, index);
Output:

67 found at index: 5
Time Complexity
Since Binary Search divides the array into half each time its time complexity is O(log(N)). This time complexity is a marked improvement on the O(N) time complexity of Linear Search.

Space Complexity
This search requires only one unit of space to store the element to be searched. Hence, its space complexity is O(1).

If Binary Search is implemented recursively, it needs to store the call to the method on a stack. This may require O(log(N)) space in the worst case scenario.

Applications
It is the most commonly used search algorithm in most of the libraries for searching. The Binary Search tree is used by many data structures as well which store sorted data.

Binary Search is also implemented in Java APIs in the Arrays.binarySearch method.

Knuth Morris Pratt Pattern Search
As the name indicates, it is an algorithm for finding a pattern in the given text. This algorithm was developed by Donald Knuth, Vaughan Pratt, and James Morris, hence the name.

Explanation
In this search, the given pattern is first compiled. By compiling it, we try to find the prefix and suffix of the pattern string. This helps us when a mismatch happens - we will not start looking for the next match from the beginning of the index.

Instead, we skip the part of text string which we have already compared and start comparing beyond that part. We determine this part by knowing the prefix and suffix so we are sure what part is already compared and can be safely skipped.

As a result of this skip, we can save a lot of comparisons and KMP performs faster than a naive brute-force algorithm.

Implementation
Let's create the compilePatternArray() method, which will be used later by the KMP search algorithm:

public static int[] compilePatternArray(String pattern) {
    int patternLength = pattern.length();
    int len = 0;
    int i = 1;
    int[] compliedPatternArray = new int[patternLength];
    compliedPatternArray[0] = 0;

    while (i < patternLength) {
        if (pattern.charAt(i) == pattern.charAt(len)) {
            len++;
            compliedPatternArray[i] = len;
            i++;
        } else {
            if (len != 0) {
                len = compliedPatternArray[len - 1];
            } else {
                compliedPatternArray[i] = len;
                i++;
            }
        }
    }
    System.out.println("Compiled Pattern Array " + Arrays.toString(compliedPatternArray));
    return compliedPatternArray;
}
The compiled pattern array can be thought of as an array storing the pattern of characters in the pattern array. The main aim behind creating this array is to find the prefix and suffix in the pattern. If we know these elements in the pattern, we can avoid comparing from the start of the text and just compare next character after the mismatch has occurred.

The compiled array stores the index position of previous occurrence of the current character in the pattern array.

Let's implement the algorithm itself:

public static List<Integer> performKMPSearch(String text, String pattern) {
    int[] compliedPatternArray = compilePatternArray(pattern);

    int textIndex = 0;
    int patternIndex = 0;

    List<Integer> foundIndexes = new ArrayList<>();

    while (textIndex < text.length()) {
        if (pattern.charAt(patternIndex) == text.charAt(textIndex)) {
            patternIndex++;
            textIndex++;
        }
        if (patternIndex == pattern.length()) {
            foundIndexes.add(textIndex - patternIndex);
            patternIndex = compliedPatternArray[patternIndex - 1];
        }

        else if (textIndex < text.length() && pattern.charAt(patternIndex) != text.charAt(textIndex)) {
            if (patternIndex != 0)
                patternIndex = compliedPatternArray[patternIndex - 1];
            else
                textIndex = textIndex + 1;
        }
    }
    return foundIndexes;
}
Here we start by comparing the characters in the pattern and text array sequentially. We keep moving forward until we keep getting a match of pattern and text arrays. This way, if we reach the end of the pattern array while matching it means we have found an occurrence of the pattern in the text.

However, if we find a mismatch when comparing the two arrays, we move the pattern character array index to the value in the compiledPatternArray() and also move to the next character in the text array. This is where the KMP search beats the brute-force approach, as it doesn't compare the text characters more than once if there is a mismatch.

Let's try running the algorithm:

String pattern = "AAABAAA";
String text = "ASBNSAAAAAABAAAAABAAAAAGAHUHDJKDDKSHAAJF";

List<Integer> foundIndexes = KnuthMorrisPrathPatternSearch.performKMPSearch(text, pattern);

if (foundIndexes.isEmpty()) {
    System.out.println("Pattern not found in the given text String");
} else {
    System.out.println("Pattern found in the given text String at positions: " + .stream().map(Object::toString).collect(Collectors.joining(", ")));
}
In the pattern text AAABAAA, the following pattern is observed and encoded in the pattern array:

The pattern A (Single A) is repeating in index 1 and again at 4.
The pattern AA (Double A) is repeating in index 2 and again at index 5.
The pattern AAA (3 A's) is repeating at index 6.
Let's see the output to validate our discussion so far:

Compiled Pattern Array [0, 1, 2, 0, 1, 2, 3]
Pattern found in the given text String at positions: 8, 14
The pattern we described is clearly shown to us in the complied pattern array in the output.

With the help of this compiled array, the KMP search algorithm can search for the given pattern in the text without moving back in the text array.

Time Complexity
This algorithm needs to compare all the elements in the given text to find the pattern. The time required for that is O(N) . For compiling the pattern string we need to visit each of the character in the pattern and that is another O(M) iterations.

So the total time this algorithm takes will be O(M+N).

Space Complexity
We need O(M) space to store the compiled pattern for a given pattern of size M

Applications
This algorithm is particularly employed in text tools for finding patterns in text files.

Jump Search
Explanation
This search is similar to Binary Search but instead of jumping both forward and backward - we will only jump forward. Keep in mind that Jump Search also requires for the collection to be sorted.

In Jump Search, we jump in the interval sqrt(arraylength) ahead until we reach an element greater than current element or end of the array. On every jump, the previous step is recorded.

If we encounter an element greater than the element we are searching for, we stop jumping. Then, we run a Linear Search between the previous step and the current step.

This makes the search space a lot smaller for Linear Search, and thus it becomes a viable option.

Implementation
public static int jumpSearch(int[] integers, int elementToSearch) {

    int arrayLength = integers.length;
    int jumpStep = (int) Math.sqrt(integers.length);
    int previousStep = 0;

    while (integers[Math.min(jumpStep, arrayLength) - 1] < elementToSearch) {
        previousStep = jumpStep;
        jumpStep += (int)(Math.sqrt(arrayLength));
        if (previousStep >= arrayLength)
            return -1;
    }
    while (integers[previousStep] < elementToSearch) {
        previousStep++;
        if (previousStep == Math.min(jumpStep, arrayLength))
            return -1;
    }

    if (integers[previousStep] == elementToSearch)
        return previousStep;
    return -1;
}
We start with the jumpstep of size square-root of the length of array and keep jumping forward with this same size until we find an element which is same or greater than the element we are searching for.

So we first visit element at integers[jumpStep], then integers[2jumpStep], integers[3jumpStep] and so on. We also store the previous element visited in the previousStep variable.

Once we find a value such that integers[previousStep] < elementToSearch < integers[jumpStep], we perform a linear search between integers[previousStep] and integers[jumpStep] or an element greater than elementToSearch.

We can use the algorithm like this:

int index = jumpSearch(new int[]{3, 22, 27, 47, 57, 67, 89, 91, 95, 99}, 67);
print(67, index);
Output:

67 found at Index 5
Time Complexity
Since we jump sqrt(arraylength) steps in each iteration, the time complexity for this search is O(sqrt(N)).

Space Complexity
The space complexity for this search is O(1) as it requires only one unit of space to store the element to be searched.

Application
This search is used over Binary Search when jumping back is costly. This constraint is faced when we use spinning medium like drives when seeking forward is easy but jumping in changed direction multiple times is costly.

Interpolation Search
Explanation
Interpolation Search is used to search elements in a sorted array. This search is particularly useful if we know the data in the underlying structure is uniformly distributed.

If the data is uniformly spread out, taking a guess about the location of an element can be more precise, opposed to Binary Search where we always try to find the element in the middle of the array.

Interpolation Search uses interpolation formulae to find the best probable place where the element can be found in the array. However, for this formulae to be effective the search array should be large otherwise it performs like Linear Search:

Implementation
public static int interpolationSearch(int[] integers, int elementToSearch) {

    int startIndex = 0;
    int lastIndex = (integers.length - 1);

    while ((startIndex <= lastIndex) && (elementToSearch >= integers[startIndex]) &&
           (elementToSearch <= integers[lastIndex])) {
        // using interpolation formulae to find the best probable position for this element to exist
        int pos = startIndex + (((lastIndex-startIndex) /
          (integers[lastIndex]-integers[startIndex]))*
                        (elementToSearch - integers[startIndex]));

        if (integers[pos] == elementToSearch)
            return pos;

        if (integers[pos] < elementToSearch)
            startIndex = pos + 1;

        else
            lastIndex = pos - 1;
    }
    return -1;
}
We can use this algorithm like this:

int index = interpolationSearch(new int[]{1,2,3,4,5,6,7,8}, 6);
print(67, index);
Output:

6 found at Index 5
Let's take a look at how the interpolation formulae works its magic to look for 6:

startIndex = 0
lastIndex = 7
integers[lastIndex] = 8
integers[startIndex] = 1
elementToSearch = 6
Now let's apply this values to the formulae to estimate the index of search Element:

i
n
d
e
x
=
0
+
(
7
−
0
)
/
(
8
−
1
)
∗
(
6
−
1
)
=
5
The element at integers[5] is 6 which is the element we were looking for. As we can see here, the index for the element is calculated in just one step since the data is uniformly spread.

Time Complexity
The best case time complexity for this algorithm is O(log log N) but in the worst case, i.e. when the elements are not uniformly distributed, it is comparable to linear search time complexity which is O(N).

Space Complexity
This algorithm also requires only one unit of space to store the element to be searched. Hence its space complexity is O(1).

Application
This search is useful when the data is uniformly distributed like Phone Numbers in a directory.

Exponential Search
Explanation
Exponential Search is used to search elements by jumping in exponential positions i.e. in powers of 2.

In this search we are basically trying to find a comparatively smaller range in which we can search the element using other bounded searches algorithms like Binary Search.

Needless to say, the collection should be sorted for this to work.

Implementation
public static int exponentialSearch(int[] integers, int elementToSearch) {

    if (integers[0] == elementToSearch)
        return 0;
    if (integers[integers.length - 1] == elementToSearch)
        return integers.length;

    int range = 1;

    while (range < integers.length && integers[range] <= elementToSearch) {
        range = range * 2;
    }

    return Arrays.binarySearch(integers, range / 2, Math.min(range, integers.length), elementToSearch);
}
We can use this algorithm like this:

int index = exponentialSearch(new int[]{3, 22, 27, 47, 57, 67, 89, 91, 95, 99}, 67);
print(67, index);
This is how the algorithm works:

We try to find an element which is greater than the element we are searching. We do this to minimise the range of elements we are looking for. We increase the range by multiplying it with 2 and check again if we reached an element greater than element we are searching or the end of array. Once either of this is achieved, we break out of the loop. Then we perform binary search with startIndex as range/2 and lastIndex as range.

In our case, this range value is achieved at 8 and the element at integers[8] is 95. So, the range where we perform binary search is:

startIndex = range/2 = 4

lastIndex = range = 8
With this the binary search call becomes:

Arrays.binarySearch(integers, 4, 8, 6);
Output:

67 found at Index 5
A important thing to note here we can speedup the multiplication by 2 by using the left shift operator range << 1instead of * operator.

Time Complexity
The worst-case time complexity for this type of search is O(log(N)).

Space Complexity
This algorithm requires O(1) space to store the element being searched if the underlying Binary Search algorithm is iterative.

If the underlying Binary Search algorithm is recursive, the space complexity becomes O(log(N)).

Applications
Exponential search is used when we have a huge or unbounded array. Applying Binary Search on the entire dataset may prove to be costly. Exponential Search can reduce this data into smaller, easily searchable partitions.

Fibonacci Search
Explanation
Fibonacci search employs divide and conquer approach wherein we unequally split element as per the Fibonacci series. This search requires the array to be sorted.

Unlike in Binary Search where we divide the elements into equal halves to reduce the array range - In Fibonacci search we try to use addition or subtraction to get a smaller range.

Remember the formula for Fibonacci series is:

F
i
b
o
(
N
)
=
F
i
b
o
(
N
−
1
)
+
F
i
b
o
(
N
−
2
)
The first two numbers in this series are Fibo(0) = 0 and Fibo(1) = 1. So as per this formula, the series looks like this 0, 1, 1, 2, 3, 5, 8, 13, 21... Interesting observations to note here is that:

Fibo(N-2) is approximately 1/3rd of Fibo(N)

Fibo(N-1) is approximately 2/3rd of Fibo(N)

So when we use fibonacci series numbers to partition the range it gets split in the same ratio as above.

Implementation
Let's take a look at the implementation to get a clearer idea:

public static int fibonacciSearch(int[] integers, int elementToSearch) {

    int fibonacciMinus2 = 0;
    int fibonacciMinus1 = 1;
    int fibonacciNumber = fibonacciMinus2 + fibonacciMinus1;
    int arrayLength = integers.length;

    while (fibonacciNumber < arrayLength) {
        fibonacciMinus2 = fibonacciMinus1;
        fibonacciMinus1 = fibonacciNumber;
        fibonacciNumber = fibonacciMinus2 + fibonacciMinus1;
    }

    int offset = -1;

    while (fibonacciNumber > 1) {
        int i = Math.min(offset+fibonacciMinus2, arrayLength-1);

        if (integers[i] < elementToSearch) {
            fibonacciNumber = fibonacciMinus1;
            fibonacciMinus1 = fibonacciMinus2;
            fibonacciMinus2 = fibonacciNumber - fibonacciMinus1;
            offset = i;
        }

        else if (integers[i] > elementToSearch) {
            fibonacciNumber = fibonacciMinus2;
            fibonacciMinus1 = fibonacciMinus1 - fibonacciMinus2;
            fibonacciMinus2 = fibonacciNumber - fibonacciMinus1;
        }

        else return i;
    }

    if (fibonacciMinus1 == 1 && integers[offset+1] == elementToSearch)
        return offset+1;

    return -1;
}
We can run this algorithm like this:

int index = fibonacciSearch(new int[]{3, 22, 27, 47, 57, 67, 89, 91, 95, 99}, 67);
print(67, index);
This is how the algorithm works:

It starts by first finding the number in the Fibonacci series closest to but more than the length of array. This happens when fibonacciNumber is at 13 which is just more than array length - 10.

Next, we compare the elements of the array and on the basis of that comparison , we take one of the below actions:

Compare the element to be searched with the element at fibonacciMinus2 and return the index if the value matches.
If the elementToSearch is greater than the current element, we move one step back in the fibonacci series and change the values of fibonacciNumber, fibonacciMinus1 & fibonacciMinus2 accordingly. The offset is reset to the current Index.
If the elementToSearch is smaller than the current element, we move two steps back in the fibonacci series and change the values of fibonacciNumber, fibonacciMinus1 & fibonacciMinus2 accordingly.
Output:

67 found at Index 5
Time Complexity
The worst-case time complexity for this search is O(log(N)).

Space Complexity
While we need to save the three numbers in Fibonacci series and the element to be searched we need four extra units of space.

This requirement of space does not increase with the size of the input array. Hence, we can say that the space complexity for Fibonacci search is O(1).

Applications
This search is used when the division is a costly operation for the CPU to perform. Algorithms like Binary Search tend to fare poorly as they use division to divide the array.

Another benefit of this search is when elements of the input array cannot fit into the RAM. In such situations, a localized scope of operation that this algorithm performs helps it to run much faster.

Java Collections API
Now that we have seen the implementation of multiple algorithms in Java, let's also take a brief look at the way searching is performed in different Java Collections.

Arrays
Arrays in Java can be searched using one of the java.util.BinarySearch methods. The binary Search in the Open JDK version uses the iterative form of the search.

Let's take a quick look at how we can use this method:

int[] integers = {3, 22, 27, 47, 57, 67, 89, 91, 95, 99};

int elementToSearch = 67;

int index = java.util.Arrays.binarySearch(integers, elementToSearch);
Output:

67 found at Index 5
The List Interface
The List Interface has primarily two methods which can be used for searching: indexOf() and contains().

The indexOf() method returns the index of the element if it exists in the list or -1 if it doesn't exist.

The contains() method returns true or false depending upon the existence of the element. It internally calls the indexOf() method.

The List interface uses Sequential Search to perform the index lookup and hence its time complexity is O(N).

Let's try out a search operation on a List:

java.util.List<Integer> integers = new java.util.ArrayList<>();
integers.add(3);
integers.add(22);
integers.add(27);
integers.add(47);
integers.add(57);
integers.add(67);
integers.add(89);
integers.add(91);
integers.add(95);
integers.add(99);

int elementToSearch = 67;

int index = integers.indexOf(elementToSearch);
Output:

67 found at Index 5
Similarly, if we are not interested in the index but only want to know if the element exists in the List or not we can use the contains() method:

integers.contains(67)
Output:

true
The Map Interface
The Map is a key-value pair data structure. The Map interface in Java uses HashBased searching as well as the Binary Search Tree.

The java.util.HashMap class uses a hash-value of the key to store the elements in the Map. Retrieving the element from the Map using right keys to hash and a good Hashing algorithm (such that no collisions occur) is O(1).

Another implementation of the Map interface is the java.util.TreeMap, which internally uses Red-Black Tree which is a type of self-balancing binary search tree. The elements added to this tree are automatically stored in the sorted fashion by the tree.

The time complexity of searching a Binary Tree is O(log(N)).

Let's see how we can search an element in a Map:

java.util.Map<Integer, String> integers = new java.util.HashMap<>();
integers.put(3,"three");
integers.put(22,"twentytwo");
integers.put(27,"twentyseven");
integers.put(47,"fortyseven");
integers.put(57,"fiftyseven");
integers.put(67,"sixtyseven");
integers.put(89,"eightynine");
integers.put(91,"ninetyone");
integers.put(95,"ninetyfive");
integers.put(99,"ninetynine");

String value = integers.get(67);

System.out.println("the value at key 67 is: " + value);
We have created a map with a key as an Integer and the value as that Integer in words. We then search for a key and get the Integer as words in the output.

An important thing to note here is that the map will not store duplicate keys. If we try to insert a duplicate value it will overwrite the existing key and value with the new one.

Output:

the value at key 67 is: sixtyseven
Map interface also contains the containsKey() method which can be used to determine if a given key exists or not:

integers.containsKey(67);
The Set Interface
The Set data-structure is used to store unique elements. The Set interface is essentially a wrapper over the Map interface described above storing elements in the Key of the Map.

As with the Map interface it uses the Binary and Hash-based search.

java.util.Set<Integer> integers = new java.util.HashSet<>();
integers.add(3);
integers.add(22);
integers.add(27);
integers.add(47);
integers.add(57);
integers.add(67);
integers.add(89);
integers.add(91);
integers.add(95);
integers.add(99);

int elementToSearch = 67;

boolean isNumberExists = integers.contains(elementToSearch);

if (isNumberExists)
    System.out.println(elementToSearch + " exists in the set");
else
    System.out.println(elementToSearch + " does not exist in the set");
There is no index in the Set interface and as such the search operation contains() returns true or false depending upon the existence of the element being searched.

In this case, since the element exists in the set we get the below output:

67 exists in the set
Search Algorithm Time Comparison
That being said, it's often useful to run all of these algorithms a few times to get an idea of how they perform.

Let's search for the element 573400 in a sorted array that's populated with a million integers.

Here are the results of the algorithms:

time(ns)	Linear	Binary (Iterative)	Binary (Recursive)	Jump	Interpolation	Exponential	Fibonacci
First Run	5 229 901	23 014	14 928	125 647	18 661	49 762	13 373
Second Run	8 436 389	24 570	14 306	329 046	18 349	206 820	21 770
Third Run	7 207 909	24 569	23 326	585 005	19 593	106 054	23 325
Fourth Run	5 888 615	33 589	27 057	218 327	23 015	111 341	25 813
Fifth Run	3 002 466	20 216	46 962	132 800	15 861	65 311	20 216
Sixth Run	6 896 901	12 440	26 124	212 107	7 465	106 054	38 254
Seventh Run	6 916 495	59 714	13 373	210 241	15 240	126 891	13 684
Eight Run	6 781 828	22 393	46 962	159 235	10 575	83 972	26 436
Ninth Run	6 917 116	11 507	18 660	265 911	28 302	130 002	12 751
Tenth Run	3 811 085	41 053	89 259	302 922	26 436	183 184	25 192
It's easy to see that Linear Search takes significantly longer than any other algorithm to search for this element, since it evaluated each and every element before the one we're searching for. If we were searching for the first element, Linear Search would be the most efficient one here.

It's also easy to see the Binary, Interpolation and Fibonacci Search show the best results for this particular array.

Conclusion
Every system has its own unique set of constraints and requirements. A correctly used search algorithm, based on those constraints, can go a long way in determining the performance of the system.
*

## String Techniques

## Two Pointer Technique

## Linked Lists

## Stacks and Queues

## Binary Trees

## Binary Search Trees

## Recursion

## Backtracking

## Dynamic Programming

## Greedy Algorithms

## Graphs

## 








### The README: Let us know which topics you'd like listed here in the issues tab



### List of helpful code websites to practice


1. *Hackerrank*  `www.hackerrank.com` 
   
2. *CodeSignal* -- 

3. *CodeBat* --

4. *Codewars* -- 

5. *Leetcode* 

6. *Pramp* 








## Bonus: websites that are helpful



- https://javadocs.com


## Bonus: The Java open source Checklist

A helpful checklist to gauge how your learning is coming along:

- [ ] OOP topics understood?
- [ ] Algorithms mastered? Brute-force and Optimized solutions understood?
- [ ] APIs built? SpringBoot framework?
- [ ] Read a few books on Java? Deittel Java objects, and Effective Java are good starting points.
- [ ] Built a CRUD app with Java? SQL database? 
- [ ] Java flashcards? 



## The authors

I'm [Zach Beecher](https://github.com/ziggity/). 


This little project began back in July 2020

## Further Reading





## Footnotes

1. <a name="footnote-1"></a>Thanks,


## Credits




   